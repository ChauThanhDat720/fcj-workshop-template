---
title: "Blog 3"
date: 2026-07-04
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}


# [SERVERLESS PATTERNS] Stop Choosing Between Single-Purpose and Lambda-lith: What's the Deal with Read-Write Separation (CQRS Prelude)?

Today I read a very deep analysis on the AWS Compute Blog by two Principal Solutions Architects regarding Serverless Microservices design strategies. Seeing that the article addresses exactly the pain point that we Serverless engineers often encounter when deciding on AWS Lambda architectures, I summarized and dissected it with an additional technical perspective here for us to discuss.

When designing a RESTful API with AWS Lambda and API Gateway, the most classic question is always: **How granular should we split our Lambdas?**

In reality, we often get stuck between two extremes:

## 1. Single Responsibility Lambda (One Function Per Endpoint)
**Approach:** Splitting down to the very end (Fine-grained). Each HTTP route + method (`GET /users`, `POST /users`, `DELETE /users/{id}`) maps to a separate Lambda function.

**Pros:**
- Codebase isolation, extremely small bundle size which optimizes the Init Phase time (reduces Cold Starts).
- Fully applies the Least Privilege IAM principle. The GET function only has `dynamodb:GetItem` permission, while the POST function has `dynamodb:PutItem`.
- Independent Memory/Timeout configurations (heavy compute functions get 1024MB RAM, lightweight functions only need 128MB).

**Cons:**
- Infrastructure as Code (IaC) management becomes extremely tedious. If using AWS CloudFormation, you can easily hit the hard limit (500 resources/stack).
- Infrequently called functions (like DELETE) will constantly have their Execution Context reclaimed, leading to a very high Cold Start rate for end-users.
- Code repetition (DRY violation) in database connection pooling or middlewares.

## 2. The Lambda-lith (All-in-one)
**Approach:** Pushing all API routes of a service into a single function (Monolithic Lambda). Typically uses adapters like `aws-serverless-express` to run Express/NestJS (Node.js) or Spring Boot (Java) inside Lambda. API Gateway acts merely as a `{proxy+}`.

**Pros:**
- Centralized code, making it easy to share DTOs, Entities, and Database Connections.
- Warm Start rate approaches 100% because the function continuously receives traffic, keeping the environment (container) alive.

**Cons:**
- **Bloated Deployment Package:** Very easy to hit the 250MB unzipped limit. This leads to dreadful Cold Starts, especially when having to initialize heavy framework contexts (like NestJS's DI container or Spring Boot's JVM startup).
- **Wasted GB-seconds:** You are using Lambda's compute time (paid per ms) just to handle routing – a task API Gateway can do for free/much cheaper.
- **Bloated IAM Policy:** This function must have Read/Write permissions to all Tables/S3 Buckets that the service touches, increasing security risks (large Blast radius).

## The Pragmatic Middle Ground: Read and Write Separation
The two AWS authors proposed a third design, perfectly neutralizing the two extremes by splitting based on Behavior. Instead of splitting too fine or grouping too large, we split a Bounded Context into exactly 2 Lambda Functions:

1. **Write Lambda (Command/Write Operations):** Groups requests that change system states (POST, PUT, DELETE, PATCH).
   - *Technical insight:* Write operations often share complex validation libraries, ORM mappings, and transaction logic. Grouping them optimizes bundle size reasonably, while less frequently used functions (like DELETE) can "piggyback" on the warm Execution Context of higher traffic POST functions.
   
2. **Read Lambda (Query/Read Operations):** Handles pure GET flows.
   - *Technical insight:* Read logic is usually very light, mainly querying the DB and mapping responses. No need to load body validation libraries (like Joi, Zod, or class-validator). Small bundle size, fast Init phase, helping API latency for end-users reach its absolute optimum.

## Evolutionary Architecture towards CQRS
The most valuable aspect of this pattern is that it creates a perfect stepping stone for the system to evolve into CQRS (Command Query Responsibility Segregation) and Event-Driven architecture when scaling:

- **Decouple the Write flow:** Instead of API Gateway directly calling the Write Lambda (Synchronous), you can easily switch to Asynchronous by sandwiching Amazon SQS in between. API Gateway immediately returns `HTTP 202 Accepted`. The Write Lambda pulls messages from SQS via Event Source Mapping and processes them using Batching, combined with a Dead Letter Queue (DLQ) for retries. This prevents the database (like RDS or MongoDB) from being overwhelmed with connections during traffic spikes.
- **Scale the Read flow:** On the Read side, because the logic is completely decoupled, you are free to attach ElastiCache (Redis) using the Cache-Aside pattern, or point the Read Lambda directly to a Read Replica Database without fearing that side-effects might break the Write flow.

## Real-world Perspective from the EdTech Domain
Imagine building a School Management System; inherently, the read and write traffic is completely asymmetrical. Incoming requests for Reading (students viewing schedules, checking grades, downloading notices) can generate thousands of RPS. Meanwhile, the Write flow (lecturers taking attendance, academic departments entering grades) is much lower but requires extremely high data integrity (ACID).

Applying this Read-Write Separation pattern allows us to aggressively scale memory and concurrency for the Read flow during peak exam periods, while keeping the Write flow operating stably, isolating risks, and optimizing AWS infrastructure costs.

## Conclusion
In Serverless, no architecture is a Silver Bullet. Choosing which pattern depends on the business context for you to trade-off between: Developer Experience (DevX), Cost, Security (IAM), and Performance (Cold Start).

*Facebook Post: [Link to AWS Study Group FB](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203819477049679/?rdid=ZuOE5xSl9R071zJb#)*

![Image](/images/blog3/image1.png)

![Image](/images/blog3/image2.png)
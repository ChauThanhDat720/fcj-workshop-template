---
title: "Week 10 Worklog"
date: 2026-04-17
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Learn Amazon Cognito: user pools, identity pools, and authentication flows.
* Integrate Cognito with the Next.js web application for secure access control.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Amazon Cognito overview: User Pools vs Identity Pools <br> - Authentication flows: SRP, custom auth, hosted UI | 17/06/2026 | 17/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Cognito User Pool configuration: password policy, MFA, email verification <br> - App clients and OAuth 2.0 scopes | 18/06/2026 | 18/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Practice:** <br>&emsp; + Create Cognito User Pool <br>&emsp; + Configure app client with OAuth settings <br>&emsp; + Test sign-up and sign-in flows | 19/06/2026 | 19/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Integrating Cognito with API Gateway authorizer <br> - Protected routes in Next.js using Cognito JWT tokens | 20/06/2026 | 20/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Add Cognito JWT authorizer to API Gateway <br>&emsp; + Implement login/logout in Next.js <br>&emsp; + Restrict dashboard access to authenticated users | 21/06/2026 | 21/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Rookwork Project — Phase 4: React Frontend Development & Deploy to S3 + CloudFront + WAF**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Develop React 19 UI: Login, Dashboard, Workspace, and Task Board pages <br> - Configure React Router and global state management | 17/06/2026 | 21/06/2026 | |
| 3 | - Build production bundle of the React app <br> - Create Amazon S3 bucket (FE Static): configure static website hosting and upload build files | 17/06/2026 | 21/06/2026 | |
| 4 | - Configure Amazon CloudFront distribution: S3 origin, cache behaviors, HTTPS <br> - Integrate AWS WAF with CloudFront to protect against web exploits | 17/06/2026 | 21/06/2026 | |
| 5 | - Link CloudFront to Route 53 custom domain <br> - Configure CORS on Spring Boot Backend to accept requests from the CloudFront domain | 17/06/2026 | 21/06/2026 | |
| 6 | - **Review & test Phase 4:** <br>&emsp; + Test full flow: Login & CRUD from Frontend → ALB → EC2 → RDS <br>&emsp; + Verify WAF blocks malicious requests <br>&emsp; + Plan File Storage & SES integration (Phase 5) | 17/06/2026 | 21/06/2026 | |

### Week 10 Achievements:

* Successfully completed: Amazon Cognito overview: User Pools vs Identity Pools

* Successfully completed: Authentication flows: SRP, custom auth, hosted UI

* Successfully completed: Cognito User Pool configuration: password policy, MFA, email verification

* Successfully completed: App clients and OAuth 2.0 scopes

* Successfully completed: Create Cognito User Pool

* Successfully completed: Configure app client with OAuth settings

* Successfully completed: Test sign-up and sign-in flows

* Successfully completed: Integrating Cognito with API Gateway authorizer

* Successfully completed: Protected routes in Next.js using Cognito JWT tokens

* Successfully completed: Add Cognito JWT authorizer to API Gateway

* Successfully completed: Implement login/logout in Next.js

* Successfully completed: Restrict dashboard access to authenticated users

* **[Rookwork]** Develop React 19 UI: Login, Dashboard, Workspace, and Task Board pages

* **[Rookwork]** Configure React Router and global state management

* **[Rookwork]** Build production bundle of the React app

* **[Rookwork]** Create Amazon S3 bucket (FE Static): configure static website hosting and upload build files

* **[Rookwork]** Configure Amazon CloudFront distribution: S3 origin, cache behaviors, HTTPS

* **[Rookwork]** Integrate AWS WAF with CloudFront to protect against web exploits

* **[Rookwork]** Link CloudFront to Route 53 custom domain

* **[Rookwork]** Configure CORS on Spring Boot Backend to accept requests from the CloudFront domain

* **[Rookwork]** Test full flow: Login & CRUD from Frontend → ALB → EC2 → RDS

* **[Rookwork]** Verify WAF blocks malicious requests

* **[Rookwork]** Plan File Storage & SES integration (Phase 5)


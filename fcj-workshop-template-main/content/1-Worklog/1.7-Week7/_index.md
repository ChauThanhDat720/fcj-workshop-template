---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Learn AWS IoT Core: device connection, MQTT protocol, topics, and rules.
* Understand how to ingest sensor data from edge devices into the AWS cloud.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ----------------------------------------- |
| 2   | - AWS IoT Core overview: device registry, message broker, rules engine <br> - MQTT protocol: topics, QoS levels, retain messages | 22/09/2025 | 22/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - IoT Core Thing creation and certificates <br> - Device policies for secure MQTT connection | 23/09/2025 | 23/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Practice:** <br>&emsp; + Create IoT Thing with certificate <br>&emsp; + Simulate device publishing MQTT messages <br>&emsp; + Subscribe to topics in MQTT test client | 24/09/2025 | 24/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - IoT Rules Engine: SQL-like rule queries <br> - Route messages to S3, Lambda, DynamoDB | 25/09/2025 | 25/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Practice:** <br>&emsp; + Create IoT rule to forward data to S3 <br>&emsp; + Trigger Lambda from IoT rule <br>&emsp; + End-to-end data ingestion test | 26/09/2025 | 26/09/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 7 Achievements:

* Understood the AWS IoT Core architecture and how edge devices securely communicate with the cloud via MQTT.

* Created IoT Things with X.509 certificates and configured device policies.

* Simulated sensor data publishing to IoT topics using the MQTT test client.

* Built IoT Rules to automatically route incoming messages to S3 and Lambda.

* Completed an end-to-end data ingestion pipeline from simulated device to cloud storage.

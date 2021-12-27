### Overview

- AmazonMQ is an AWS implementation of Apache ActiveMQ
- Open-source message broker
    - **JMS API** - open standard protocols such as **JMS, AMQP, MQTT, OpenWire and STOMP**
- Provides **QUEUES** and **TOPICS**
- <span style="color:orange;font-weight:bold">Many ORGs already use topics and queues</span>
- One-to-One or One-to-Many
- **Single Instance** (Test, Dev, Cheap), or **HA Pair** (Active/Standby)
- VPC service - <span style="color:orange;font-weight:bold">NOT A PUBLIC SERVICE - PRIVATE networking required</span>
- NO AWS native integration
    - delivers activeMQ product which you manage

![active-mq](./images/active-mq.png)

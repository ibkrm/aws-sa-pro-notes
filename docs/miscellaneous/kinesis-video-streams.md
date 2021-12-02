### Overview
- Ingest <span style="color:orange;font-weight:bold">ingest live video from producers</span>
- **Devices** like 
    - security cameras, smartphones, cars, drones
    - time-serialised audio, thermal and RADAR data
- Once data is ingested to AWS, consumers can access the data frame by frame .. **or as needed**
- Can **persist** and **encrypt** (both in rest and transit)
- <span style="color:red;font-weight:bold">cannot ingest data directly.. only via API</span>
- Integrates with other AWS services like **Rekognition** and **Connect**

![kinesis-video-streams](kinesis-video-streams.png)
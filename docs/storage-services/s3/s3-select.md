S3 and Glacier Select allow you to use a SQL-Like statement to retrieve partial objects from S3 and Glacier.

- S3 can store HUGE objects (upto  5TB)
- You often want to retrieve the **entire object**
- Retrieving a 5TB object .. **takes time, uses 5TB**

### S3 Select 
- S3/Glacier select let you use **SQL-like statements**
- Part of the object is **pre-filtered by S3**
- Suports **CSV, JSON and Parquet**
    - <span style="color:orange;font-weight:bold">BZIP2 compression for CSV and JSON</span>
- <span style="color:green;font-weight:bold">Cheaper and faster because S3 is pre-filtering the results before sending it to the client</span>

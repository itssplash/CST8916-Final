# Real-Time Stock Data Processing with Azure Event Hubs and Stream Analytics

This project demonstrates the creation of a real-time streaming data pipeline using Azure Event Hubs and Stream Analytics. The pipeline filters stock data with prices over $30 and stores the results in Azure Blob Storage.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Setup Steps](#setup-steps)
3. [Stream Analytics Query](#stream-analytics-query)
4. [Verification](#verification)
   - [Event Hub Configuration](#event-hub-configuration)
   - [Stream Analytics Job Configuration](#stream-analytics-job-configuration)
   - [Blob Storage Output](#blob-storage-output)
5. [Screenshots](#screenshots)

---

## Introduction
The goal of this project is to process stock market data in real time. Using Azure Event Hubs to ingest data and Azure Stream Analytics to process it, stock prices greater than $30 are filtered and stored in Azure Blob Storage.

---

## Setup Steps

### 1. **Azure Event Hub Configuration**
   - Created an Event Hub namespace and an Event Hub named `stockdata`.
   - Used the **Data Explorer** in Event Hub to send sample stock data in JSON format:
     ```json
     {
       "symbol": "NNCY",
       "price": {
         "currency": "USD",
         "value": 54.37
       }
     }
     ```

### 2. **Azure Stream Analytics Job**
   - Configured the **input** to connect to the Event Hub (`stockdata`).
   - Wrote the query to filter stock data where `price.value > 30`.
   - Configured the **output** to store results in Azure Blob Storage.

---

## Stream Analytics Query
```sql
SELECT
    symbol,
    price.value AS price,
    price.currency AS currency
INTO
    stockcontainer
FROM
    stocksdata
WHERE
    price.value > 30
```

## Updated Stream Analytics Query for next question
```
SELECT
    symbol AS Symbol,
    price.value AS Price,
    high - low AS TradeRange,
    volume AS Volume,
    market_Cap.value AS MarketCapValue,
    EventEnqueuedUtcTime AS EventTime
INTO
    stockcontainer
FROM
    stocksdata
WHERE
    price.value > 20
```


## Verification
### Event Hub Configuration
- Successfully created the Event Hub named stockdata.
- Sent sample data using the Data Explorer feature.
- Stream Analytics Job Configuration
- Configured the input as "stocksdata" from Event Hub.
- Used the provided SQL query to filter data.
- Configured the output as "stockcontainer" in Azure Blob Storage.

### Blob Storage Output
- Verified the filtered data is stored in the Blob Storage container.
- The output folder structure and at least one JSON file are visible.

# All the screenshots are attached below and in sepearte .md as well
# Event Hubs Sending Data
![Screenshot (734)](https://github.com/user-attachments/assets/292ab6a2-f4de-4723-b2a1-e5c302a218a8)
![Screenshot (1484)](https://github.com/user-attachments/assets/afaf18ea-9ccd-41d1-9af5-8d5e11b263f9)
![Screenshot (1485)](https://github.com/user-attachments/assets/8f234865-35c8-4029-bed0-f10b2d21daf4)
![Screenshot (366)](https://github.com/user-attachments/assets/273911dc-3a21-4574-9f4f-fad2f31fc747)
# INPUT
![image](https://github.com/user-attachments/assets/883146c9-c74a-493c-bfb7-4755bdbb1c5f)
![image](https://github.com/user-attachments/assets/d357efd3-e534-482d-a7d7-3cfccf12c333)
# Output
![image](https://github.com/user-attachments/assets/242fa012-c9c1-4303-a25d-0af7c695d757)
![image](https://github.com/user-attachments/assets/697c5d76-fd3b-44f4-99a2-cd31bbdf7e03)

# Query
![image](https://github.com/user-attachments/assets/bbf09905-3bc3-45df-a539-468b4f04a66e)

# Container Screenshots , getting JSON data in the output structured Folder
![image](https://github.com/user-attachments/assets/0dbfae13-0813-40c2-8af6-fcf00c488b9b)
![image](https://github.com/user-attachments/assets/3b930f1c-7a38-4dcf-8910-93308da800be)
![image](https://github.com/user-attachments/assets/b5750a4e-905f-43fe-8203-e9f50b300f0c)
![image](https://github.com/user-attachments/assets/fb014d37-022a-4505-844c-7252e6d306af)
## JSON FILE
![image](https://github.com/user-attachments/assets/c12014ef-de16-4f67-a9af-7dc1292c7490)



## Screenshots of Question 9
![image](https://github.com/user-attachments/assets/08b32000-9fab-4616-97b0-031c227ea650)

![image](https://github.com/user-attachments/assets/ba54f679-6644-4199-924b-e893a6e044b6)
![image](https://github.com/user-attachments/assets/3b4cd052-3fbf-4eb1-b74d-ca7d6bccbe1b)

![image](https://github.com/user-attachments/assets/90465dd2-540b-4b37-a4cc-6c3015f811de)

## As you can see the results showing the rows where price > 30 only
![image](https://github.com/user-attachments/assets/bfc04e2f-0a22-496e-8063-022883b83cbb)

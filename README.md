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
    stockOutput
FROM
    stockInput
WHERE
    price.value > 30
```


Here’s the content reformatted correctly in Markdown (.md) format:

markdown
Copy code
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
    stockOutput
FROM
    stockInput
WHERE
    price.value > 30
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

All the screenshots are attached below and in sepearte .md as well

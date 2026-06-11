# Hospital Patient Monitoring using Spark Structured Streaming

## Overview

This project implements a real-time hospital patient monitoring system using Apache Spark Structured Streaming.

The system monitors patient heart rates and generates alerts when the average heart rate exceeds 100 bpm over a 2-minute tumbling window.

---

## Technologies

- Python
- PySpark
- Apache Spark Structured Streaming
- Google Colab

---

## Dataset

IoMT Hospital Patient Monitoring Dataset from Kaggle.

---

## How to Run

1. Install PySpark.
2. Upload the dataset.
3. Run all notebook cells.
4. The notebook simulates streaming by feeding CSV batches.
5. Spark reads data using readStream.
6. Watermark and tumbling windows are applied.
7. Alerts are generated when average heart rate exceeds 100 bpm.

---

## Why a 2-minute Tumbling Window?

A 2-minute tumbling window groups patient heart-rate measurements into fixed non-overlapping intervals. This helps detect sustained abnormal heart rates instead of isolated spikes and simplifies real-time aggregation.

---

## Where does the pipeline require state?

Spark maintains state while aggregating heart-rate values within each 2-minute window. The withWatermark() function allows Spark to manage late-arriving data and remove old state automatically.

---

## Alert Condition

Average heart rate > 100 bpm.

---

## Output

The Spark Structured Streaming pipeline displays alert batches containing:

- Patient ID
- Window interval
- Average heart rate

A screenshot of the alert output is included in this repository.

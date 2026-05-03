# 🚕 Real-Time Taxi Streaming Pipeline

This project demonstrates a **real-time data engineering pipeline** that streams NYC taxi trip data through a modern streaming architecture using Python, Redpanda (Kafka-compatible), Apache Flink, and PostgreSQL.

The pipeline simulates real-time ingestion, processes streaming data using Flink, and stores results for downstream analytics.

---

## 🏗️ Architecture

NYC Taxi Data → Python Producer → Redpanda/Kafka Topic → Apache Flink Job → PostgreSQL → Analytics

---

## ⚙️ Tech Stack

- **Python** – Data ingestion and processing
- **Redpanda (Kafka-compatible)** – Streaming message broker
- **Apache Flink** – Stream processing engine
- **PostgreSQL** – Data storage for processed results
- **Docker & Docker Compose** – Containerized environment
- **Makefile** – Simplified command execution

---

## 📂 Project Structure

real-time-taxi-streaming-pipeline/
│
├── src/
│   ├── producers/        # Publishes taxi trip data to Kafka/Redpanda
│   │   ├── producer.py
│   │   └── producer_realtime.py
│   │
│   ├── consumers/        # Consumes streaming data
│   │   ├── consumer.py
│   │   └── consumer_postgres.py
│   │
│   ├── job/              # Apache Flink streaming jobs
│   │   ├── pass_through_job.py
│   │   ├── aggregation_job.py
│   │   └── aggregation_job_demo.py
│   │
│   └── models.py         # Shared schema and data models
│
├── docker-compose.yml    # Services: Redpanda, Flink, PostgreSQL
├── Dockerfile.flink      # Flink container setup
├── flink-config.yaml     # Flink configuration
├── Makefile              # Helper commands
├── pyproject.toml        # Python dependencies
└── README.md

---

## 🚀 How to Run

### 1. Start all services

```bash
docker compose up -d

This will start:
	•	Redpanda (Kafka broker)
	•	Apache Flink
	•	PostgreSQL

⸻

2. Run Producer (Data Ingestion)

python src/producers/producer.py

Or simulate real-time streaming:

python src/producers/producer_realtime.py


⸻

3. Run Consumer (Optional - Debugging)

python src/consumers/consumer.py


⸻

4. Run Flink Streaming Job

python src/job/pass_through_job.py

Or aggregation job:

python src/job/aggregation_job.py


⸻

5. Store Data in PostgreSQL

python src/consumers/consumer_postgres.py


⸻

📊 Key Features
	•	Real-time data ingestion using Kafka-compatible Redpanda
	•	Stream processing with Apache Flink
	•	Modular architecture (producers, consumers, processing jobs)
	•	Containerized setup using Docker Compose
	•	Scalable and production-style pipeline design

⸻

🎯 Learning Outcomes
	•	Designed and implemented a real-time streaming pipeline
	•	Integrated Kafka-compatible messaging system (Redpanda)
	•	Built stream processing jobs using Apache Flink
	•	Managed containerized infrastructure using Docker
	•	Structured a production-style data engineering project

⸻

🔮 Future Improvements
	•	Add Airflow orchestration for pipeline scheduling
	•	Integrate data quality checks (Great Expectations)
	•	Build a real-time dashboard (Streamlit / Power BI)
	•	Deploy on cloud (AWS / GCP)

⸻

🙏 Acknowledgment

This project is inspired by the
DataTalksClub Data Engineering Zoomcamp (Streaming Module)
and adapted into a standalone portfolio project.

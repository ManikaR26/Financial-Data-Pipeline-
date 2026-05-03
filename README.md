Real-Time Event Data Processing Pipeline

This project implements a real-time data processing system designed to ingest, transform, store, and visualize financial market data. It leverages Apache Kafka for streaming, Apache Spark for real-time processing, MySQL for storage, and Grafana for monitoring and visualization. The entire pipeline is containerized using Docker to ensure scalability and easy deployment.

Project Objectives
Build a real-time data ingestion pipeline using Apache Kafka
Perform streaming data processing using Apache Spark
Store processed data efficiently in a MySQL database
Create interactive dashboards for data visualization using Grafana
Containerize and orchestrate all services using Docker
System Architecture

The pipeline is composed of the following components:

Data Producer: A Python-based service that retrieves live stock market data from an external API and streams it to Kafka topics
Apache Kafka: Acts as the messaging layer, handling real-time data ingestion and buffering
Apache Spark: Consumes streaming data from Kafka, performs transformations, and prepares it for storage
MySQL Database: Stores the processed and structured financial data
Grafana Dashboard: Provides real-time insights through interactive visualizations and monitoring panels

Dependencies for the producer and processing modules are managed via requirements.txt and installed within their respective Docker containers.

Prerequisites
Python (v3.12 or later)
Docker and Docker Compose installed
API key from Financial Modeling Prep
Setup Instructions
Clone the repository:
git clone https://github.com/hawa1222/real-time-data-processing.git
Navigate to the project directory:
cd real-time-data-processing
Configure the environment:
Make the setup script executable:
chmod +x setup_environment.sh
Run the setup script:
./setup_environment.sh
Create a .env file in the root directory and add the required environment variables as specified in .env_template.
Running the Application

Start all services using Docker:

docker-compose up --build

This will initialize and run all components including Kafka, Spark, MySQL, and Grafana.

Alternatively, individual services can be executed manually by activating the virtual environment and running:

Kafka Producer:
python kafka/kafka_producer.py
Spark Processor:
python spark/process_data.py
Accessing the Dashboard

Open your browser and navigate to:

http://localhost:3000
Log in using the credentials defined in the .env file
The MySQL data source is pre-configured
A default dashboard for stock data visualization is automatically loaded
Customization
Modify the .env file to update database configurations
Edit stock_data_dashboard.json to customize Grafana dashboards
License

This project is distributed under the MIT License. Refer to the LICENSE file for more details.

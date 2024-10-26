# ETL Pipeline Deployment with Astro, Apache Airflow

## Project Overview

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline, leveraging modern data engineering tools for robust data processing and management. The pipeline integrates Astro for streamlined setup, Apache Airflow for orchestration, PostgreSQL as the data storage solution, and DBeaver for efficient database management.

## Table of Contents
- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Pipeline Components](#pipeline-components)
- [Usage Guide](#usage-guide)
- [Contribution](#contribution)
- [License](#license)

## Architecture

**Pipeline Components**:
1. **Astro**: Simplifies the deployment and management of Apache Airflow.
2. **Apache Airflow**: Orchestrates the ETL process by managing task scheduling and execution.
3. **PostgreSQL**: Serves as the primary data storage for ingested and transformed data.
4. **DBeaver**: Provides a user-friendly database interface for visualization and data interaction.

## Features
- **Automated Data Pipeline**: Fully automated ETL with modular, reusable components.
- **Containerization**: Ensures consistency and portability with Docker containers.
- **Database Management**: Seamlessly interact with and monitor data in PostgreSQL using DBeaver.
  
## Requirements

The following tools should be installed locally:
- **Docker & Docker Compose**: For container orchestration.
- **DBeaver**: Optional but recommended for database visualization.
- **Astro CLI**: For efficient local deployment and management of Airflow.

## Installation

1. **Clone the Repository**:
    ```bash
    git clone <repository-url>
    cd <project-directory>
    ```

2. **Launch Services**:
    Run the following to initiate PostgreSQL and Airflow in Docker containers:
    ```bash
    docker-compose up -d
    ```

3. **Configure Database Access in DBeaver**:
    - Open DBeaver and establish a new connection to PostgreSQL using:
        - Host: `localhost`
        - Port: `5432`
        - Database: `<database-name>`
        - User: `<user>`
        - Password: `<password>`

## Pipeline Components

- **DAGs (Directed Acyclic Graphs)**: Located in the `dags/` directory, each DAG orchestrates data extraction, transformation, and loading processes.
- **PostgreSQL Database**: Hosted in a Docker container, PostgreSQL serves as the ETL storage endpoint.
- **Astro**: Handles Airflow deployment, providing a streamlined development and orchestration environment.

### DAG Workflow Outline

1. **Extract**: Retrieves raw data from specified sources.
2. **Transform**: Cleanses, normalizes, and prepares data for analysis.
3. **Load**: Stores transformed data in PostgreSQL for persistent storage.

## Usage Guide

1. **Start Airflow with Astro**:
    - Use the following command to start Astro's local development environment and run Airflow:
      ```bash
      astro dev start
      ```
    - To stop the environment, use:
      ```bash
      astro dev stop
      ```
    - To restart the environment, use:
      ```bash
      astro dev restart
      ```

2. **Deploy and Monitor DAGs**:
    - Navigate to the Airflow UI, where you can trigger the DAGs manually or set a schedule.
    - Track and manage ETL job runs, view logs, and monitor progress within the UI.

3. **Query Data in PostgreSQL**:
    - Use DBeaver or a SQL client to validate and analyze the stored data in PostgreSQL.

## Contribution

Contributions to enhance the project are welcome. Please open an issue or submit a pull request for review.

## License

This project is licensed under the MIT License. See the LICENSE file for more information.

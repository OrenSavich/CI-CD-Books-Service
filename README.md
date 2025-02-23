# CI/CD Pipeline for Books Service

## 📚 Overview

This project implements a **Continuous Integration / Continuous Deployment (CI/CD) pipeline** for the Books Service using **GitHub Actions** and **Docker**. The pipeline includes **automated build, testing, and query execution** using MongoDB as the database.

## 🛠️ Features

- **Automated CI/CD pipeline** triggered by GitHub push events.
- **Containerized Books Service** built with Docker.
- **Automated Unit Tests** using **pytest**.
- **Integration with MongoDB** for data persistence.
- **Query Execution Job** for automated testing.
- **Logs and Artifacts Upload** after every workflow run.

## 🎯 System Workflow

The CI/CD pipeline consists of three jobs:

### **1️⃣ Build Job**

- Builds a Docker image for the Books Service.
- Pushes the image to the local environment.
- Ensures the service is ready for testing.

### **2️⃣ Test Job**

- Runs **Books Service** and **MongoDB** containers using **Docker Compose**.
- Executes unit tests using `pytest`.
- Stores test results in `assn3_test_results.txt`.

### **3️⃣ Query Job**

- Runs both **Books Service** and **MongoDB** containers.
- Executes six **POST requests** to add books.
- Reads queries from `query.txt`, executes them, and logs responses.
- Saves query results in `response.txt`.

## 📌 API Endpoints

### **Books Service**

- `POST /books` - Add a new book (returns `{"ID": <string-ID>}`)
- `DELETE /books/{id}` - Remove a book (returns `{ "ID": <string-ID> }`)
- `GET /books` - Fetch all books
- `GET /books/{id}` - Fetch details of a specific book

## 🔧 Setup & Deployment

### **Prerequisites**

- **Docker & Docker Compose** installed.
- **GitHub Actions configured** in the repository.
- **MongoDB instance** available for testing.

### **Installation Steps**

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/OrenSavich/ci-cd-books-service.git
   cd ci-cd-books-service
   ```
2. **Start the Application**:
   ```bash
   docker-compose up --build -d
   ```
3. **Verify Running Containers**:
   ```bash
   docker ps
   ```
4. **Trigger a GitHub Action Run**:
   - Push any changes to the repo to trigger CI/CD.

## 🏗️ Workflow Artifacts

After each run, the workflow uploads these files to GitHub:

1. **log.txt** - Execution log file.
2. **assn3\_test\_results.txt** - Test results from pytest.
3. **response.txt** - Results of query execution job.

## 📌 Authors

- **Oren Savich**


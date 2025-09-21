# 📚 Course, Student, Media & Frontend

This repository contains a microservices-based application developed for the Enterprise Cloud Applications assignment.
It includes three backend services (Course Service, Student Service, Media Service) built with Spring Boot, and a frontend application that consumes these APIs to perform CRUD operations and demonstrate integration.

---

## 🚀 Features
- RESTful CRUD APIs for managing courses,students, and media
- Built with **Spring Boot** and **Java 17+**
- Uses **Maven** for dependency management
- **MySQL** database for persistent storage
- **Dockerized** for easy deployment
- Deployed on **Google Cloud Run**
- Secure connection to **Cloud SQL** using the **Cloud SQL Socket Factory**
- Frontend built with **React** to interact with backend services

---

## 🛠️ How to Use This Repository

### 1. Clone the repository
```bash
git clone https://github.com/weerapperuma/cloud-enabled-deployment-in-action-with-aws.git
cd cloud-enabled-deployment-in-action-with-aws
```

### 2. Backend – Run locally
Make sure you have **Java 17+** and **Maven** installed.

```bash
mvn clean package -DskipTests
java -jar target/course-service-1.0.0.jar
```

The service will be available at:  
👉 `http://localhost:8080/api/courses`

---

### 3. Backend – Run with Docker
Build and run the Docker image:

```bash
docker build -t course-service .
docker run -p 8080:8080 course-service
```

---

### 4. Backend – Deploy to Google Cloud Run
```bash
gcloud builds submit --tag gcr.io/<project-id>/course-service
gcloud run deploy course-service \
  --image=gcr.io/<project-id>/course-service \
  --region=asia-south1 \
  --add-cloudsql-instances=<project-id>:asia-south1:eca-mysql \
  --set-env-vars CLOUD_SQL_CONNECTION_NAME=<project-id>:asia-south1:eca-mysql,DB_USER=eca_user,DB_PASSWORD=MySql123!
```

---

### 5. Frontend – Run locally
Update your frontend `.env` or config file with the deployed Cloud Run URL:

```
REACT_APP_COURSE_SERVICE_URL=https://course-service-xxxxxx-as.a.run.app
```

Then start the frontend:
```bash
npm install
npm run dev
```

---

### 6. Database
- Database: `eca_courses`
- User: `eca_user`
- Connection configured in `application-gcp.properties`

---

## 🎥 Video Demonstration
👉 [Watch the demo video here](https://drive.google.com/file/d/1a48DksMv64mDFH_AzX9ifqEwuMFd3Ry3/view?usp=drive_link)

---

---

## 📜 License
This project is licensed under the [MIT License](LICENSE).

---

## 👨‍💻 Author
- Name: *Sahiru Deshan (2301682048)*
- email: *weerapperumasahiru@gmail.com*
- contact: *0784320108*
- Course: *Enterprise Cloud Applications*
- Assignment: *Microservices Deployment with GCP*

---

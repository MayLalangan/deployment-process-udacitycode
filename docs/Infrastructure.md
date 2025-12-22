# Infrastructure Description

This project is deployed using Amazon Web Services (AWS) using the following components:

## 1. Frontend (Client)
- **Service**: AWS S3 (Simple Storage Service)
- **Configuration**: Static Website Hosting
- **Bucket Name**: `bucket-udacity-app` (example)
- **Access**: Publicly accessible via the S3 website URL.
- **Build Artifact**: Angular compiled code (`www` folder).

## 2. Backend (API)
- **Service**: AWS Elastic Beanstalk
- **Environment**: `Demo-app-env` (Node.js Platform)
- **Server**: Node.js v14/v16 running Express.
- **Port**: 8080 (Mapped via Elastic Beanstalk Proxy to 80).

## 3. Database
- **Service**: AWS RDS (Relational Database Service)
- **Engine**: PostgreSQL
- **Connection**: Backend connects via TCP port 5432 using credentials securely stored in environment variables.

## 4. File Storage
- **Service**: AWS S3
- **Usage**: Storing user-uploaded images from the specific API routes.

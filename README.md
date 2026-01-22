# AWS 3-Tier Web Application Deployment

⚠️ This repository focuses on AWS 3-tier architecture and deployment design.
The source code is used to simulate a production AWS environment locally.
The primary goal of this project is to demonstrate cloud architecture, networking,
security, and scalability — not application logic.

---

## Architecture Overview

This project follows a standard AWS 3-tier architecture:

Web Tier
- React-based frontend
- Deployed in public subnets
- Served via Application Load Balancer
- Runs locally on localhost:3000

Application Tier
- Node.js backend REST APIs
- Deployed in private subnets
- Communicates securely with database tier
- Runs locally on localhost:4000

Database Tier
- MySQL database (Amazon RDS in AWS)
- Fully isolated in private subnets
- Accessible only from application tier

---

## AWS Architecture Diagram

The diagram below represents the intended AWS production deployment:

architecture-diagram.png

---

## Repository Structure

application-code/
├── web-tier/        React frontend (Web Tier)
├── app-tier/        Node.js backend (Application Tier)
├── nginx.conf       Nginx configuration for AWS EC2
├── nginx-without-ssl.conf

---

## Technologies Used

- React.js
- Node.js
- Express.js
- MySQL
- Amazon Web Services (VPC, EC2, ALB, RDS, Auto Scaling)
- Nginx
- Git and GitHub

---

## Running the Project Locally

Start Application Tier (Backend)

cd application-code/app-tier
npm install
node index.js

Backend runs on:
http://localhost:4000

---

Start Web Tier (Frontend)

cd application-code/web-tier
npm install
npm start

Frontend runs on:
http://localhost:3000

---

## AWS Deployment Design

In AWS, this project is designed using:
- Custom VPC with public and private subnets
- Application Load Balancer
- Auto Scaling Groups
- Bastion Host
- NAT Gateway
- Security Groups
- Amazon RDS (MySQL)

The local setup simulates this architecture without provisioning AWS resources.

---

## Important Note

This is not a code-focused project.

The frontend and backend code serve as deployment artifacts to represent services
running on AWS infrastructure. The main focus of this project is cloud architecture,
security best practices, scalability, and DevOps principles.

---

## Key Learnings

- AWS 3-tier architecture design
- Separation of concerns between web, application, and database layers
- Cloud networking and security concepts
- Load balancing and high availability
- Real-world production deployment patterns

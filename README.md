# Secure Cloud Infrastructure Project – AWS, Docker, and EC2

This project demonstrates how to design and deploy a secure cloud-based system for managing and storing user-uploaded images using **AWS services**. It highlights practical aspects of **secure cloud architecture**, **automation**, and **role-based access control**, aligning with modern **cloud engineering and cybersecurity** practices.

---

## 🏗️ Architecture Overview

The application is hosted on **Amazon EC2** and integrates with **AWS S3** and **RDS** for image storage and database management. Security and automation are handled using **IAM roles**, **Docker**, and the **AWS SDK (S3Client)**.

![Architecture Diagram](https://github.com/NikhilAgrawal12/AwsJavaProject/blob/c0e5b5e948d13a3013222f9847442ada7f69e203/Image1.png)

### Key Flow

1. **EC2 Role Authorization:** The EC2 instance uses an IAM role (`aws-elasticbeanstalk-ec2-role`) that grants permission to upload images securely to S3 without hardcoded credentials.
2. **Image Upload via S3Client:** The backend uploads images to S3 at the path `/images/user-id/image-id` using the AWS SDK for Java.
3. **Metadata Storage in RDS:** Each uploaded image’s metadata and ID are stored in an **Amazon RDS** database, associated with the respective customer.
4. **Local Testing:** Used **IntelliJ IDEA** and a local mock S3 setup to test the upload and retrieval flow before deployment.
5. **Dockerized Deployment:** The backend API is containerized using Docker for portability and consistent runtime environments.

![Application Flow](https://github.com/NikhilAgrawal12/AwsJavaProject/blob/f4589b3debe72f4908df1a90de67e980ba83ca7e/Image2.png)

---

## ☁️ Technologies Used

* **AWS** – EC2, S3, RDS, IAM
* **Docker** – Containerization and deployment
* **Java (Spring Boot)** – Backend API implementation
* **AWS SDK (S3Client)** – Secure upload and data interaction
* **PostgreSQL** – Managed through Amazon RDS
* **IntelliJ IDEA** – Development and local testing

![System Components](https://github.com/NikhilAgrawal12/AwsJavaProject/blob/a564dfc0f930bc03ab028af45b5be9b493c3f885/Image3.png)

---

## 🔐 Security Highlights

* **IAM Role-Based Access Control:** EC2 interacts with S3 using IAM roles, removing the need for credentials in the code.
* **Network Security:** Communication between EC2, S3, and RDS is restricted to authorized network paths.
* **Data Protection:** Image data in S3 is private, and metadata in RDS is encrypted at rest.
* **Local Mock Testing:** Testing with a fake S3 service minimizes cloud exposure during development.
* **Container Isolation:** Each app instance runs securely inside a Docker container.

---

## 🧩 Future Enhancements

* Integrate **CI/CD pipeline** using GitHub Actions or AWS CodePipeline.
* Add **CloudWatch monitoring** for better visibility into API performance and errors.
* Implement **AWS KMS** for advanced encryption key management.

---

## 📎 Author

**Nikhil Agrawal**
Software & Cloud Engineer | Cybersecurity Enthusiast

---

This project combines cloud architecture, automation, and cybersecurity principles to build a secure, scalable application on AWS.






# StreamingApp
Collaborative Streaming application

## Backend

### AuthService
`.env` file for the Authentication Service.

```sh
PORT=3001
MONGO_URI="yourMongoDB_URIwithDatabaseName"
JWT_SECRET="writesomerandomsecrets"
```

## Capstone -- Problem Statement 

 Project: DevOps Pipeline for MERN Stack Streaming Application

 Problem Statement:
The objective is to develop a robust DevOps pipeline for a streaming application built on the MERN stack (MongoDB, Express.js, React, Node.js), where videos are uploaded to an AWS S3 bucket. This project encompasses the creation of a multi-stage Docker image for the application, ensuring scalability, security, monitoring, and efficient deployment strategies including blue-green deployments. The infrastructure automation will be managed using Terraform, while the database will be configured to run on-premise (locally on the learner's laptop). The project will also implement GitOps practices for continuous deployment, maintaining separate environments for staging, development, and production.

 Goals and Deliverables:

1. Infrastructure as Code (IaC):
   - Use Terraform to provision and manage AWS cloud resources, including S3 buckets for video storage, EC2 instances for hosting the application, and necessary networking components.
   - Document the Terraform scripts and configurations for easy replication and deployment.

2. Dockerization and CI/CD Pipeline:
   - Develop a multi-stage Dockerfile for building lightweight, efficient images of the MERN stack application.
   - Set up Jenkins or GitHub Actions for continuous integration and delivery, automating the build, test, and deployment process across development, staging, and production environments.
   - Implement GitOps practices, using tools like ArgoCD or Flux for continuous deployment based on git repository changes.

3. Database Configuration:
   - Configure MongoDB to run locally on the learner's laptop, ensuring secure access and integration with the cloud-hosted application components.
   - Provide detailed setup and configuration instructions, including data backup and recovery procedures.

4. Security and Monitoring:
   - Implement security best practices, including the use of AWS IAM for access control, encryption of data in transit and at rest, and regular security audits.
   - Use Prometheus and Grafana for monitoring the application's performance and infrastructure health.
   - Configure alerts for any performance issues or security threats.

5. Deployment Strategy:
   - Implement a blue-green deployment strategy to minimize downtime and risk by maintaining two production environments.
   - Automate the switch-over process between blue and green environments, ensuring seamless deployment of new application versions.

6. Scalability and Backups:
   - Ensure the application is scalable, utilizing AWS Auto Scaling Groups to handle varying loads.
   - Automate the backup process for the S3 bucket and on-premise MongoDB database, including periodic backups and secure storage of backup data.


## Sample - Conceptual Architecture 

Scalable , Highly Secure and Highly available , Region Specific access of content provided by Streaming App ---

#Architecture Overview:   ( W. I . P )
  Key Elements Involved -- 
1.	Client-side (React.js):
•	The user interface where users interact with the streaming app.
2.	Server-side (Node.js with Express.js):
•	Handles user authentication, authorization, and serves as the backend API for the streaming service.
3.	Database (MongoDB):
•	Stores user data, content metadata, access control lists, etc.
4.	Storage (Amazon S3):
•	Stores the actual streaming content (videos, images, etc.).
5.	Content Delivery Network (Amazon CloudFront):
•	Distributes content globally with low latency and high transfer speeds.
6.	Authentication & Authorization (Amazon Cognito):
•	Manages user authentication, provides secure user directories, and integrates with social identity providers.
7.	Compute (Amazon EC2, AWS Lambda):
•	EC2 instances can be used to host the Node.js server.
•	AWS Lambda can be used for serverless functions, such as thumbnail generation, data processing, etc.
8.	Load Balancing (Amazon Elastic Load Balancing):
•	Distributes incoming application or network traffic across multiple targets (such as EC2 instances) to ensure scalability and high availability.
9.	Database Management (Amazon DocumentDB or Amazon DynamoDB):
•	Depending on your requirements, you can choose between DocumentDB (MongoDB-compatible managed database service) or DynamoDB (fully managed NoSQL database service).
10.	Monitoring & Logging (Amazon CloudWatch, AWS X-Ray):
•	CloudWatch monitors your AWS resources and applications, while X-Ray helps in analyzing and debugging production applications.
11.	Security (AWS IAM, AWS WAF, AWS Shield):
•	IAM manages access to AWS services and resources securely.
•	AWS WAF (Web Application Firewall) protects your web applications from common web exploits.
•	AWS Shield provides DDoS (Distributed Denial of Service) protection.
12.	Region-based Access Control:
•	Use Geo Blocking and Geo IP Filtering to intercept user reuests and the IP location and able to provide the allowed content to the users.

  #Steps to Implement: 
1.	Design the Database Schema: Define schemas for users, content, access control lists, etc.
2.	Implement Authentication & Authorization: Use Amazon Cognito for user authentication and manage access control.
3.	Develop Backend API: Implement RESTful APIs using Node.js with Express.js to handle CRUD operations for users, content, etc.
4.	Integrate with AWS Services: Utilize S3 for storing content, CloudFront for content delivery, and other AWS services as per your requirements.
5.	Implement Region-based Access Control: Use Lambda@Edge to intercept requests and enforce access control based on user's region.
6.	Ensure Scalability & High Availability: Utilize auto-scaling, load balancing, and distributed architecture to handle varying loads and ensure availability.
7.	Implement Security Measures: Set up IAM roles, configure WAF rules, and enable Shield to protect against security threats.
8.	Monitor & Optimize Performance: Set up CloudWatch alarms / Prometheus and Grafana for monitoring, analyze performance metrics, and optimize the architecture for better performance.





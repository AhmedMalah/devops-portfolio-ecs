
# DevOps Portfolio App on AWS ECS

This is a simple Flask-based web application deployed on AWS ECS using Docker and Fargate.  
It serves as a DevOps portfolio showcasing basic infrastructure skills including containerization, cloud deployment, and CI/CD.

---

## 🔧 Tech Stack

- Python (Flask)
- Docker
- AWS ECS (Fargate)
- GitHub Actions (CI/CD)

---

## 🚀 Features

- Containerized Flask app
- Deployed on AWS ECS using Fargate
- CI/CD pipeline with GitHub Actions
- Infrastructure-as-Code (optional in future)

---

## 📁 Project Structure

devops-portfolio-ecs/
│
├── app.py                # Flask application code
├── requirements.txt      # Python dependencies
├── Dockerfile            # Instructions to build Docker image
├── README.md             # Project description and documentation

---

## 📦 How to Run Locally

```bash
# Build the Docker image
docker build -t devops-portfolio .

# Run the container
docker run -p 5000:5000 devops-portfolio
```

---

## ☁️ Deployment on AWS ECS (Fargate)

This application is deployed on **Amazon ECS using Fargate**, which allows running containers without managing servers.

### Deployment Steps:

1. **Docker Image Creation & Push to ECR**
   - The Flask app is containerized using a `Dockerfile`.
   - The image is pushed to **Amazon Elastic Container Registry (ECR)**.

2. **ECS Cluster Configuration**
   - An ECS cluster is created using the **Fargate launch type**.
   - A task definition is created with the ECR image and resource settings.
   - A service is configured to run the task and expose the app via an **Application Load Balancer (ALB)**.

3. **Networking Setup**
   - The service is deployed in a **VPC** with public subnets.
   - Security groups are configured to allow HTTP traffic on port 80.

---

## 🔄 CI/CD Pipeline with GitHub Actions

A GitHub Actions workflow automates the build and deployment process to AWS ECS.

### Workflow Overview:

- **Trigger**: On every push to the `main` branch.
- **Steps**:
  1. Checkout the repository.
  2. Authenticate with AWS using GitHub secrets.
  3. Build and tag the Docker image.
  4. Push the image to Amazon ECR.
  5. Update the ECS service with the new image.

This ensures that every code change is automatically deployed to the live environment.

---

## 📌 Future Enhancements

- Add **Infrastructure-as-Code** using Terraform or AWS CloudFormation.
- Integrate **monitoring and logging** with Amazon CloudWatch.
- Enable **HTTPS** using AWS Certificate Manager (ACM).
- Implement **Auto Scaling** based on traffic and resource usage.

---

## 📎 Useful Links

- [Amazon ECS Documentation](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Docker Documentation](https://docs.docker.com/)
- [Flask Documentation](https://flask.palletsprojects.com/)

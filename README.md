# AWS Manual CI/CD Pipeline Demo 🚀

This project demonstrates a **complete end-to-end CI/CD pipeline on AWS** using **GitHub, AWS CodePipeline, AWS CodeBuild, and AWS Elastic Beanstalk** to deploy a **Node.js application**.

The pipeline is fully automated — **any push to the GitHub repository triggers a rebuild and redeployment**.

---

## 🧩 Architecture Overview

```

GitHub Repository
↓
AWS CodePipeline
↓
AWS CodeBuild (CI)
↓
AWS Elastic Beanstalk (CD)
↓
Live Node.js Application

```

---

## 🛠️ AWS Services Used

- **GitHub** – Source code repository
- **AWS CodePipeline** – CI/CD orchestration
- **AWS CodeBuild** – Build & dependency installation
- **AWS Elastic Beanstalk** – Managed deployment platform (Node.js)
- **AWS IAM** – Role-based permissions
- **Amazon S3** – Artifact storage (managed by CodePipeline)

---

## 📁 Project Structure

```

aws-manual-pipeline-demo/
│
├── buildspec.yml          # CodeBuild instructions
├── package.json           # Node.js dependencies & start script
├── package-lock.json
├── index.js               # Application entry point
└── README.md

```

---

## 🔧 buildspec.yml (CI Configuration)

CodeBuild uses the following build phases:

- **Install**: Installs Node.js dependencies
- **Build**: Packages the application
- **Artifacts**: Sends build output to CodePipeline

---

## 🚀 CI/CD Workflow

1. Developer pushes code to the `main` branch
2. GitHub App webhook triggers AWS CodePipeline
3. CodePipeline pulls source code
4. CodeBuild runs `npm install` and prepares artifacts
5. Elastic Beanstalk creates a new application version
6. Environment updates automatically
7. Application is live on Elastic Beanstalk URL

---

## 🔁 Automatic Deployment

✔️ **Enabled**

Any commit pushed to the `main` branch automatically:
- Triggers the pipeline
- Rebuilds the application
- Redeploys to Elastic Beanstalk

No manual steps required.

---

## 🌍 Deployment Region

- **AWS Region:** `ap-south-1`

(All services are deployed in the same region to avoid cross-region issues.)

---

## 🔐 IAM Permissions

The CodePipeline service role includes:
- `AWSElasticBeanstalkFullAccess`
- Required permissions to create application versions and update environments

---

## ✅ Successful Deployment Verification

- Pipeline stages: **Source → Build → Deploy**
- Elastic Beanstalk environment status: **Green**
- Application accessible via Elastic Beanstalk domain

---

## 🧠 Key Learnings

- Implemented a real-world AWS CI/CD pipeline
- Integrated GitHub using GitHub App (secure method)
- Used CodeBuild for continuous integration
- Used Elastic Beanstalk for continuous deployment
- Understood IAM role requirements for deployments

---

## 🔜 Future Enhancements

- Add **Manual Approval** stage
- Add **Unit Tests** in CodeBuild
- Implement **Blue-Green deployments**
- Rebuild using **CloudFormation**
- Rebuild using **Terraform**
- Replace Elastic Beanstalk with **ECS Fargate**

---

## 📌 Author

**Chinmay K**  
GitHub: https://github.com/chinnmayK
```

---

## ✅ What You Should Do Now

1. Paste this into `README.md`
2. Commit and push:

```bash
git add README.md
git commit -m "Add project README"
git push origin main
```

This will **again trigger the pipeline** (expected behavior).

---

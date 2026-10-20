<div align="center">

# ☁️ AWS 3-Tier Architecture

### Secure by Design · Distributed Across Availability Zones · Validated End to End

**Designed and implemented a three-tier AWS application architecture with isolated networking, load-balanced web and application services, and private MySQL database integration.**

![AWS](https://img.shields.io/badge/AWS-Cloud_Infrastructure-10212B?style=for-the-badge&logo=amazonwebservices&logoColor=FF9900)
![EC2](https://img.shields.io/badge/Amazon-EC2-10212B?style=for-the-badge&logo=amazonec2&logoColor=FF9900)
![RDS](https://img.shields.io/badge/Amazon-RDS-10212B?style=for-the-badge&logo=amazonrds&logoColor=00D9C5)
![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-10212B?style=for-the-badge&logo=nginx&logoColor=00D9C5)
![Python](https://img.shields.io/badge/Python-Flask-10212B?style=for-the-badge&logo=python&logoColor=FFDE57)

</div>

---

## 🏗️ Infrastructure at a Glance

| 🌐 Networking | 🖥️ Compute | ⚖️ Load Balancing | 🗄️ Database |
|:---:|:---:|:---:|:---:|
| **6 Subnets** | **4 EC2 Instances** | **2 ALBs** | **RDS MySQL** |
| 2 Availability Zones | 2 Web + 2 Application | Public + Internal | Private Database Tier |

## 🧭 Architecture Blueprint

![AWS Three-Tier Architecture](./3%20Tier%20Architecture%20Diagram.jpg)

**Application request flow**

`Internet` → `Public ALB` → `Nginx Web Tier` → `Internal ALB` → `Flask Application Tier` → `RDS MySQL`

## 🧩 Application Architecture

| Layer | Technology | Purpose |
|---|---|---|
| **Web Tier** | Nginx | Serves web traffic and forwards requests to the application tier |
| **Application Tier** | Python + Flask | Processes application requests and communicates with the database |
| **Database Tier** | Amazon RDS MySQL | Provides persistent storage for application feedback records |

## ⚙️ Engineering Implementation

- 🌐 **Network Architecture** — Built a custom VPC with six subnets across two Availability Zones, including Internet Gateway, NAT Gateway, and route-table configuration.
- 🔐 **Security & Isolation** — Separated public and private workloads, applied tier-specific security groups, and used AWS Systems Manager to administer private application instances.
- 🚀 **Application Delivery** — Configured internet-facing and internal Application Load Balancers, Nginx reverse proxy routing, and Flask backend services.
- 🗄️ **Database Integration** — Connected the application tier to private RDS MySQL and verified persistent feedback records through SQL queries.
- 📈 **Scaling Configuration** — Created custom AMIs, Launch Templates, Auto Scaling Groups, and CPU-based target-tracking policies.

## 📊 Verified Deployment Results

| Validation | Result |
|---|---|
| 🌐 Web ALB | **2/2 Healthy Targets** |
| ⚙️ Application ALB | **2/2 Healthy Targets** |
| 🔀 Nginx Reverse Proxy | **HTTP 200 OK** |
| 🐍 Flask Application | **Health Response Verified** |
| 🗄️ RDS MySQL | **Feedback Records Confirmed** |
| 🔗 End-to-End Application | **Successfully Validated** |

> **Engineering note:** Auto Scaling was configured for both application layers, but additional EC2 launches were blocked by the AWS account's vCPU service quota. Successful scale-out was not demonstrated.

---

## 📚 Technical Documentation

### 📄 [Explore the Complete Project Documentation →](./Project%20Documentation.pdf)

*Infrastructure configuration · Deployment screenshots · Security controls · Health checks · API routing · Database validation · Troubleshooting*


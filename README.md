# 🚀 Task 3: Infrastructure as Code (IaC) with Terraform + Docker

This project demonstrates how to provision and manage a Docker container using **Terraform** as Infrastructure as Code (IaC), running inside a **Vagrant-based Ubuntu virtual machine**. 
The task involves deploying an **NGINX web server** container and exposing it to the host machine via port forwarding.

---

## 📦 Tools & Technologies Used

- **Terraform** – for Infrastructure as Code
- **Docker** – to run the container
- **Vagrant** – to create an isolated VM environment
- **Ubuntu (Vagrant Box)** – as the OS for Docker and Terraform setup

---

## 🎯 Objective

- Provision an NGINX container using Terraform
- Use Docker provider in Terraform
- Run and verify the container
- Destroy the container with Terraform

---

## 🛠️ Steps Performed

1. **Created a Vagrant VM (Ubuntu)**
   - Configured port forwarding from `8080` guest to host
2. **Installed Docker and Terraform** inside the VM
3. **Wrote a Terraform configuration** (`main.tf`) to:
   - Pull the `nginx:latest` image
   - Create a container named `nginx-tf`
   - Expose container port 80 to host via 8080
4. **Executed Terraform commands**:
   - `terraform init`
   - `terraform plan`
   - `terraform apply -auto-approve`
5. **Verified Setup**:
   - Checked running containers using `docker ps`
   - Used `curl localhost:8080` to fetch the NGINX welcome HTML
   - Opened `http://localhost:8080` in browser to confirm web access
6. **Destroyed infrastructure** using `terraform destroy`

---

## 📁 Files Included

| File          | Description                                      |
|---------------|--------------------------------------------------|
| `main.tf`     | Terraform configuration file for Docker setup   |
| `README.md`   | This documentation                               |
| `screenshots/`| Folder with screenshots from execution steps     |

---

## 📸 Screenshots

| Description                         | Preview                         |
|-------------------------------------|----------------------------------|
| `terraform apply` output            | ![Terraform Apply](screenshots/terraform-apply.png) |
| Running Docker container (`ps`)     | ![Docker PS](screenshots/docker-ps.png)             |
| `curl localhost:8080` (inside VM)   | ![Curl](screenshots/curl-localhost.png)            |
| NGINX in Browser (`localhost:8080`) | ![Browser](screenshots/browser-nginx.png)          |
| `terraform destroy` output          | ![Destroy](screenshots/terraform-destroy.png)      |

---

## 🤔 Interview Questions Covered

1. **What is IaC?**  
   Infrastructure as Code allows provisioning using configuration files instead of manual setup.

2. **How does Terraform work?**  
   Terraform uses `.tf` files to define infrastructure and deploys it through providers like Docker.

3. **What is a state file in Terraform?**  
   The `terraform.tfstate` file tracks current infrastructure deployed and its mapping to code.

4. **Difference between `terraform plan` and `apply`?**  
   - `plan`: previews changes
   - `apply`: executes the changes

5. **What are Terraform providers?**  
   Plugins that let Terraform interact with services (e.g., Docker, AWS, Azure).

6. **What is resource dependency?**  
   Terraform understands dependencies between resources and applies them in order.

7. **How are secrets handled in Terraform?**  
   Secrets should be stored securely using `.tfvars`, environment variables, or secret managers.

8. **Benefits of Terraform**  
   - Infrastructure version control  
   - Automation and repeatability  
   - Works across multiple platforms (cloud, local)

---

## ✅ Outcome

Successfully provisioned, verified, and destroyed a Docker container using Terraform inside a Vagrant environment — fully demonstrating IaC in action.

---


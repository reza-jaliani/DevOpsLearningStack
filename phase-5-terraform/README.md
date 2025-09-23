# Phase 5 - Terraform with EFK Stack

In this phase of my DevOps learning journey, I started working with **Terraform** to manage infrastructure as code.  
Instead of relying only on Docker Compose or Ansible, Terraform helps to define and provision resources in a more structured, reusable, and scalable way.

For practice, I chose to build a minimal **EFK stack (Elasticsearch, Fluentd, Kibana)** using Terraform with the Docker provider.  
The goal of this setup is:

- Run **Elasticsearch** for storing logs.  
- Use **Fluentd** as a log collector and shipper.  
- Visualize data with **Kibana** dashboards.  

This project is mainly designed to:
- Get familiar with Terraform basics (providers, resources, state, variables).  
- Compare Terraform with Docker Compose and understand when to use each tool.  
- Prepare for more advanced use cases (multi-environment, cloud deployments, modules).

---

Next steps: extend this stack with more advanced Terraform features (remote state, modules, cloud providers).

---

# Terraform Installation Guide

To get started with this phase, we first need to install Terraform on our system. Below is a straightforward step-by-step process to install Terraform on Ubuntu/Debian-based systems.

1. Update system packages

        sudo apt-get update && sudo apt-get upgrade -y

2. Install required dependencies

        sudo apt-get install -y wget curl unzip gnupg software-properties-common

3. Add HashiCorp GPG key

        wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

4. Add HashiCorp official repository

        echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
        https://apt.releases.hashicorp.com $(lsb_release -cs) main" \
        | sudo tee /etc/apt/sources.list.d/hashicorp.list

5. Install Terraform

        sudo apt-get update
        sudo apt-get install -y terraform

6. Verify installation

        terraform -version


If everything is set up correctly, you should see the installed version of Terraform.

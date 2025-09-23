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

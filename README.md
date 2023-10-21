# ELK Stack Deployment with Ansible

This repository contains an Ansible playbook for deploying the ELK (Elasticsearch, Logstash, Kibana) stack along with Filebeat, Metricbeat, and Heartbeat. The playbook automates the deployment process and ensures consistency across different Linux distributions such as CentOS, Ubuntu, and Debian-based systems.

## Prerequisites

Before running the playbook, ensure that the following requirements are met on the target host:

- Docker and Docker Compose are installed
- Access to the internet to download the required Docker images
- Sufficient resources (RAM, CPU) on the host machine
- HTTP proxy settings, if applicable

## Usage

1. Clone this repository to your local machine:

   ```shell
   git clone https://github.com/your-username/your-repo.git
2. Navigate to the repository directory:
   ```shell
   cd ELK_Docker_Ansible_/
   ```
3. Update the **inventories/hosts.yml** file with the target host information.
4. Modify the playbook variables in vars.yml according to your requirements. Include any necessary proxy settings if applicable.
5. Run the playbook using the following command:
   ```shell 
   ansible-playbook -i inventories/hosts.yml start.yml
   ```
   The playbook will deploy the ELK stack along with the specified components on the target host.

## Repository Structure

- inventory/all.yml: Contains the inventory information for the target hosts.
- inventory/group_vars/all.yml: Defines the variables used in the playbook.
- start.yml: The main Ansible playbook that deploys the ELK stack.
- roles/: Directory containing Ansible roles
- roles/docker-install: Install Docker and Docker Compose on the target host.
- roles/elastic-install: Deploys the ELK stack.
- templates/: Configures any necessary settings for the ELK stack components using the Docker Compose file from the [docker-elk](https://github.com/deviantony/docker-elk) repository.

## Configuration
The playbook supports customizing the ELK stack configuration by modifying the appropriate variables in **templates/docker-elk/[elasticsearch,logstash,kibana]/config/[elasticsearch,logstash,kibana].yml**. You can specify authentication settings in **templates/docker-elk/.env**, advanced configurations for Elasticsearch, Kibana, Logstash, and other extension like **filebeat,heartbeat,metricbeat,...** based on your requirements.

## Contribution
Contributions to this repository are welcome. If you encounter any issues or have suggestions for improvements, please create a new issue or submit a pull request.


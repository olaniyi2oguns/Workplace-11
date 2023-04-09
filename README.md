# ANSIBLE CONFIGURATION MANAGEMENT

**AIM OF THIS PROJECT:**

*The aim of this project is to automate routine tasks and appreciate DevOps tools by using Ansible Configuration Management to set up virtual servers, install and configure software, and deploy a web application. The project also focuses on writing code using YAML declarative language. The project introduces the concept of a Jump Server, also known as a Bastion Host, as an intermediary server to provide access to the internal network, where the web servers are located within a secured network that cannot be reached directly from the internet. The project divides the Virtual Private Network (VPC) into two subnets, a Public subnet with public IP addresses and a Private subnet that is only reachable by private IP addresses.*

**Architecture of the Solution**
![architecture](./image/Architecture.jpg)

Step 1: Install Ansible on Jenkins server

Make you use of the same server used for jenkins in [project 9](https://github.com/olaniyi2oguns/workplace-9.git).

`sudo apt update`

`sudo apt install -y ansible`

check the version of your ansible with `sudo ansible --version`

![architecture2](./image/Architecture2.jpg)
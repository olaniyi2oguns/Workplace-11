# ANSIBLE CONFIGURATION MANAGEMENT

**AIM OF THIS PROJECT:**

*The aim of this project is to automate routine tasks and appreciate DevOps tools by using Ansible Configuration Management to set up virtual servers, install and configure software, and deploy a web application. The project also focuses on writing code using YAML declarative language. The project introduces the concept of a Jump Server, also known as a Bastion Host, as an intermediary server to provide access to the internal network, where the web servers are located within a secured network that cannot be reached directly from the internet. The project divides the Virtual Private Network (VPC) into two subnets, a Public subnet with public IP addresses and a Private subnet that is only reachable by private IP addresses.*

**Architecture of the Solution**
![architecture](./image/Architecture.jpg)

**Step 1:** Install Ansible on Jenkins server

Make you use of the same server used for jenkins in [workplace-9](https://github.com/olaniyi2oguns/workplace-9.git).

`sudo apt update`

`sudo apt install -y ansible`

check the version of your ansible with `sudo ansible --version`

[version](./image/Ansible-version.jpg)

**Step 2:** Building a new job in jenkins

Create a new repository for this project on your [github](https://github.com) and name it "**Ansible-config-mgt**".

Create a new Freestyle job "**Ansible**" in Jenkins and connect it to your "ansible-config-mgt" repository.

Configure webhook in your "ansible-config-mgt" repository to trigger a new build in your Ansible job in Jenkins. Check [workplace-9](https://github.com/olaniyi2oguns/workplace-9.git) to learn how to configure your webhook.

On your Ansible job in Jenkins, configure a Post-build job to save all (**) files. Check [workplace-9](https://github.com/olaniyi2oguns/workplace-9.git).

From a remote client in which your "**Ansible-config-mgt**" has been cloned, make some changes to your README.MD file in main branch and commit it to your git repository. Then, check your "**Ansible**" job on Jenkins to see if a new build has been triggered automatically. 
On your jenkins server, check the artifacts to see if the changes you made is saved with command

`ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/` 

**NOTE:** Trigger Jenkins build only from main branch on your repo.

As soon as you successfully connect your Ansible job on you jenkins server, your solution will looks like the image below:

![architecture2](./image/Architecture2.jpg)

**Step 3:** Prepare your development environment using Visual Studio Code

To write some codes as a DevOps Engineer, you need tools such as the [Integrated developemt Environment (IDE)](https://en.wikipedia.org/wiki/Integrated_development_environment) or [source-code Editor](https://en.wikipedia.org/wiki/Source-code_editor) so that you can easily create a development environment that could easily be connected to your repository. 

For this project, I will recommend [Visual Studio Code (VSC)](https://en.wikipedia.org/wiki/Visual_Studio_Code) and you can get it [Here](https://code.visualstudio.com/download). However, you are free to use any other source-code Editor of your choice. 

After installation of VSC is done, configure it to connect to your git repository. [You can watch this video](https://www.youtube.com/watch?v=mR9jhYD3bnI&pp=ygUzaG93IHRvIGluc3RhbGwgYW5kIGNvbm5lY3QgdnNjIHRvIGdpdGh1YiByZXBvc2l0b3J5) to learn more on how to install and connect VSC to github repository. 

Clone your Ansible-config-mgt to your VSC using your terminal by running the command 

`git clone <ansible-config-mgt repository link>`. See image below for guide on how to get your repository link.

![repo-link](./image/git-clone.jpg)

**Step 4:** Ansible Development

After your git repository has been brought down to your local machine through VSC, create a new branch called "ANS-1" or you can give it any unique name of your choice by running command 

`git checkout -b <name of branch>`

To confirm that you are now in the console of the new branch you created, look at the left hand bottom corner of your VSC and you will find the name of the branch you are using

![git-branch](./image/branch-git.jpg)

In the new branch you created, create the following directories:

Playbooks 

Inventory.

Inside playbooks directory, create a playbook file called "common.yaml"

Within inventory directory, create file for Development, staging, testing, and production environment as dev.yaml, staging.yaml, uat.yaml, and prod.yaml respectively





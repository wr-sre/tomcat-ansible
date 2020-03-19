## Role info

> Ansible Role to Install Tomcat 9 on CentOS and Ubuntu Linux.


## Tested on the following operating systems

- CentOS 7
- Ubuntu 18.04


## 

This repo contains tasks to:

- ansible role to install tomcat
- Jenkinsfile that will run this role

## How to use this project

- Create a Jenkinspipe with this repo as SCM
- In Jenkins job, following variables are required to run this successfully.

 - USER : username with passwordless sudo access
 - HOSTS: host IP where tomcat needs to be installed
 - UI_MANAGER_USER: username for tomcat management
 - UI_MANAGER_PASS: password for tomcat management
 - UI_ADMIN_USERNAME: tomcat admin username
 - UI_ADMIN_PASS: tomcat admin password
 
 ## Jenkins worker
 - Please update the node label in Jenkinsfile as per your environment
 

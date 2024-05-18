# Ansible Automate Project
## Purpose of this project is to automate the configuration of 2 Webservers, 1 DB Server, 1 NFS Server and 1 LB Server using Ansible and Jenkins![alt text](./img/github_repo.jpg)

### Required Steps:
## a. Create a new repo named ansible-config-mgt
## b. Create an EC2 server named"Jenkins-Ansible" and Install and configure with ansible and jenkins,![alt text](./img/install_ansible.jpg) and use Elastic Ip addressing to avoid change in IPs when you shut down instance.

## c. Create a freestyle project named "ansible" on Jenkins![alt text](./img/Dashboard_Jenkins.jpg)

## d. Create a webhook link from Github repo to "Jenkins-ansible" server.![alt text](./img/webhooks.jpg)

## e. Allow and test Automatic job build to "Jenkins-ansible" server on main branch from your repo.![alt text](./img/github_main.jpg). The set up will look like the following![alt tesxt](./img/github_repo.jpg)

### Navigate to the terminal to update![alt text](./img/update.jpg) and install Ansible![alt text](./img/install_ansible.jpg) Also check the Ansible version if it's running![alt text](./img/ansible-version.jpg)

### Remember each you stop/start the Jenkins Ansible server- you have to reconfigure Github Webhookto a new IP address,it makes sense to to allocate an Elastic IP to the Jenkins Ansible.

## Prepare the development environment using Visual Studio Code
### Configure the VSCode to connect to the newly created Github repository.Clone down the ansible-config-mgt repo th the Jenkins-Ansible instance![alt text](./img/git-clone.jpg)![alt text](./img/clone_link.jpg)

### 1. In the ansible-config-mgt Github repository, create a new branch that will be used for development of a new feature.
### 2.Checkout the newly created feature branch to the local machine and start building the code and directory structure.
### 3.Create a directory and name it Playbooks- it will be use to store all the playbooks files.
### 4.Create another directory name it inventory- it will use to keep the hosts organised.
### 5. Within the playbooks folder,create the first playbook and name it 'common.yml'.
### 6. Within the inventory folder,create an inventory file for each environment(Development,Staging Testing and Production) respectively.These inventory files use .ini languages style to configure Ansible hosts.![alt text](./img/host-key.jpg) then to know the content of my host![alt text](./img/cat-ansible-host.jpg)
## Set up Ansible Inventory
### Ansible uses TCP port 22 by default,which means it needs to ssh into target servers from Jenkins-Ansible host![alt text](./img/port%2022.jpg) implement the ssh -agent and import your key into it.Then confirm the key has been added.ssh into the Jenkins-Ansible server using ssh agent ![alt text](./img/ssh_vsc.jpg)
### Updating the inventory/dev.yml file![alt text](./img/inventory-web01.jpg)
## Create a common playbook
### In common.yml playbook you will write configuration for repeatable,reusable.and multi-machine tasks that is common to systems within the infrastructure. Updating the playbooks with following code ![alt.text](./img/common.jpg)

### Commit the code into Github:
#### Use git add,commitand push the branch to Github![alt text](./img/Branches.jpg).Once the code changes appear in master branch-Jenkins will do its job and save all the files(build artifacts)to![alt text](./img/files.jpg).

## Run first ansible test
### Firstly, I install Remote devlopment![alt text](./img/Remote%20Development.jpg) in order to configure the ssh![alt text](./img/configuration.jpg) Now, it is time to execute ansible- playbook command and verify if your playbook actually works:
### Set up the VSCode to connect to the instance .Now run the playbook using the following command![alt text](./img/ansible_playbook.jpg).Installing of wireshark![alt text](./img/install_wireshark.jpg) and check if its running![alt text](./img/wireshark.jpg).
### Updating with Ansible architecture now look like this:![alt.text](./img/ansible_architecture.jpg)
### Finally, I have automated my routine task by implementing my first Ansible project![alt text](./img/Great%20ending.jpg)



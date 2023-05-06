# Vagrant CI Project 

Project Requirement <br>
Using Ansible; setup a Continuous Integration server of your choosing on a Vagrant Box. You are not required to setup Vagrant or its requirements on the host machine.

Here is what is completed 
- setup Vagrant configuration for deployment of an EC2
- setup Credentials and Security Group on AWS
- Using Vagrant 
1. configured an Ansible Job
2. able to tailor target(s) with playbooks
3. able to manage the server with Vagrant

How to Test 
1. setup with credentials 
2. git clone repo 
3. login to AWS console 
    - in EC2 Console create security group
    - export "these vars" 
    - create key pair of named credentials 
    - 

4. vagrant 

![alt text](img/basicFlow.png)



Persons in this repo are here to share and support each other to make greatness in "self world" and bring comfort in our small world of kindness to each other.  The items we are studying for focus in our employment are:

An open test platform to connect, manage, and secure microservices.

=======
<br> o AWS/GCP/Azure/Digital Ocean/Linode
<br> o Jenkins / Terraform build outs 
<br> o Packer / Ansible configured Images 
<br> o Vault / (certification pending)
<br> o Kubernetes; running all containers; there is nothing else!
<br> o Itsio Service Mesh

# Itsio Service Mesh

In this README:

- [Introduction](#introduction)
- [Repositories](#repositories)
- [Issue management](#issue-management)

git clone /vagrant-ansible-
cd vagrant-ansible-aws/
vagrant up --provider=aws
apt install vagrant 
sudo apt install vagrant 
vagrant plugin install vagrant-aws

mkdir vagrant-aws
cd vagrant-aws
vagrant init
cd .vagrant.d
cd vagrant-aws/
vagrant plugin list
vagrant up --provider virtualbox
vi vagrant_praveen.pem
chmod 400 vagrant_praveen.pem
vi vagrant-aws/


vagrant ssh
cd work/vagrant-ansible-aws/
vagrant halt


cat vagrant_ansible_inventory 
vagrant plugin install vagrant-env
history | grep vagrant
vagrant down --provider=aws
vagrant destroy --provider=aws
vagrant destroy -f --provider=aws
vagrant destroy --force --provider=aws
vagrant
vagrant status
vagrant destroy
vagrant ?
vagrant destory ?
vagrant destroy ?
vagrant destroy -q
vagrant destroy -g
vagrant destroy -g -f
vagrant up
vagrant status -full
vagrant destroy -g -f && vagrant up --provider=aws
cd vagrant-ansible-aws/vagrant-ansible-aws/
mv vagrant-ansible-aws/ work
vagrant destroy -f



## Main Products in Project
![alt text](img/products.png)

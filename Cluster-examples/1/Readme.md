Ansible-based Kubernetes cluster example
--------------------------------------
This is an example Kubernetes cluster built and managed with Ansible. The example is explained in more detail in Chapter 13 of Ansible for DevOps.

Quick Start Guide
1 - Install dependencies (VirtualBox, Vagrant, Ansible)
Download and install VirtualBox.
Download and install Vagrant.
[Mac/Linux only] Install Ansible.
Note for Windows users: This guide assumes you're on a Mac or Linux host. Windows hosts are unsupported at this time.

2 - Build the Virtual Machine
Download this project and put it wherever you want.
Open Terminal, cd to this directory (containing the Vagrantfile and this README file).
Run ansible-galaxy install -r requirements.yml -p ./roles to install required Ansible roles.
Type in vagrant up, and let Vagrant do its magic.
Note: If there are any errors during the course of running vagrant up, and it drops you back to your command prompt, just run vagrant provision to continue building the VM from where you left off. If there are still errors after doing this a few times, post an issue to this project's issue queue on GitHub with the error.

3 - Configure your host machine to access the VM.
Edit your hosts file, adding the line 192.168.56.3  cluster.k8s.test so you can connect to the VM.
4 - Deploy applications to the Kubernetes cluster
For details on how to deploy all these examples, please refer to chapter 14 in Ansible for DevOps. One quick example you can test locally:

cd into the 'examples' directory, and run the k8s-module.yml playbook, which creates an Nginx deployment and service on the cluster: ansible-playbook -i ../inventory k8s-module.yml
Copy the nodePort from the final task output in that playbook; this is the port on which Nginx is accessible.
Open your browser and access http://cluster.k8s.test:32474/ (assuming nodePort is 32474).
Notes
To shut down the virtual machine, enter vagrant halt in the Terminal in the same folder that has the Vagrantfile. To destroy it completely (if you want to save a little disk space, or want to rebuild it from scratch with vagrant up again), type in vagrant destroy.
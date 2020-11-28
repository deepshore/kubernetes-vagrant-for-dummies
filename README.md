# kubernetes-vagrant-for-dummies

Setting up Kubernetes using Vagrant, Ansible and VirtualBox without knowing anything about Vagrant and Ansible

## Preliminary notes

This project is dedicated to users who have no experience with Ansible.
Therefore, I have avoided the use of roles and dependencies in order to reduce the complexity from a beginner's point of view.

Special thanks go to Javier from [IT Wonder Lab](https://www.itwonderlab.com/), whose work and explanations are partly the basis for this project.
Please check out his great [tutorial](https://www.itwonderlab.com/en/ansible-kubernetes-vagrant-tutorial/) and the corresponding [repository](https://github.com/itwonderlab/ansible-vbox-vagrant-kubernetes) on this topic.

## Requirements

The following requirements are considered to be given:
- *nix
- Python 3
- Vagrant
- VirtualBox
- kubectl

## Installation 

### Get the code

Clone the code like this:

```bash
git clone https://github.com/grothesk/kubernetes-vagrant-for-dummies.git
```

### Create and activate a virtual environment

Create a venv like this:

```bash
python3 -m venv venv
```

Activate the venv like this:

```bash
source venv/bin/activate
```

### Install Ansible

Installing Ansible via the requirements.txt goes like this:

```bash
pip install -r requirements.txt
```

### Configure and run the Vagrantfile

Configure the file according to the available system resources.
Run vagrant from the vagrant directory:

```bash
vagrant up
```

### Configure kubectl

Change to the base folder of this project and configure kubectl to make use of  the created kubeconfig file:

```bash
export KUBECONFIG="$(pwd)/kubeconfig"
```

Do not forget to unset KUBECONFIG when you are done!

### Check status of cluster nodes

Check the status of the cluster nodes like this:

```bash
kubectl get nodes 
```
y
### Shutdown VMs

Change to the vagrant folder and shutdown the nodes like this:

```bash
vagrant halt
```

## Deinstallation

You can remove the VMs like this:

```bash
vagrant destroy
```

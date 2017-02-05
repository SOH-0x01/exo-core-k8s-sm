exo-core-k8s-sm
=======

A set of Ansible playbooks to deploy a single master kubernetes cluster on Exoscale.

[Kubernetes](https://kubernetes.io/) is an open-source system for automating deployment, scaling, and management of containerized applications.

- [Exoscale](https://www.exoscale.ch/) is a Switzerland cloud provider for the digital native based on the Apache Cloudstack API.

- [Ansible](https://www.ansible.com/) is the simplest way to automate apps and infrastructure, the DevOps way.

- [CoreOS](https://coreos.com/) is an open-source lightweight operating system based on the Linux kernel and designed for providing infrastructure to clustered deployments, while focusing on automation, ease of application deployment, security, reliability and scalability

**Note:** This cluster implementation is mostly for testing your service. In production, you would like to implement a proper encrypted communication and have multiple masters for high-availability.


Getting Started
=======

First copy or create your cloudstack.ini with your exoscale credentials.

```
$ cat ./cloudstack.ini
[cloudstack]
endpoint = https://api.exoscale.ch/compute
key = cloudstack api key
secret = cloudstack api secret
method = post
```

Run the setup script to make sure the dependencies are met.
```
$ ./setup.sh
```

The script will do the following for you:
- Install or update Ansible, python module ansible
- Install or update your python cloudstack API, python module cs

Run the playbook to create the instance.
```
$ ansible-playbook create-cluster.yaml
```

Feel free to adapt *group_vars/all.yaml* and the playbooks to modify the parameters to your liking.


Authors
=======
Marc Guillen (marc.guillen@datsci.farm)

Licence
=======
GNU
Click on the [Link](COPYING) to see the full text.

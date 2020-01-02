# Study case of Minikube

Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows.

Minikube’s primary goals are to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit.

Minikube runs the latest stable release of Kubernetes, with support for standard Kubernetes features like:

- LoadBalancer - using minikube tunnel
- Multi-cluster - using minikube start -p <name>
- NodePorts - using minikube service
- Persistent Volumes
- Ingress
- RBAC
- Dashboard - minikube dashboard
- Container runtimes - start --container-runtime
- Configure apiserver and kubelet options via command-line flags

## Requirements

- **Disable Secure Boot before start**
- ```sudo apt-get -y install linux-headers-generic```

### VirtualBox 6.0^

```
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb http://download.virtualbox.org/virtualbox/debian bionic contrib"
```
- Install VirtualBox on Ubuntu 18.04 ~ 19.04 ```sudo apt install virtualbox-6.0```
- (or VirtualBox for AMD chipsets ) ```sudo apt install virtualbox-qt```
- Reboot the machine

## Install

- Download and install minikube ```curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_1.6.2.deb && sudo dpkg -i minikube_1.6.2.deb```
- Start a cluster using the virtualbox driver ```sudo minikube start --vm-driver=virtualbox```
- To make virtualbox the default driver ```sudo minikube config set vm-driver virtualbox```
- Install `kubectl` 

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
```

- (optional) Enabling shell autocompletion adding following to your `~/.zshrc` by adding `kubectl` to your plug-in list.

## References

- https://minikube.sigs.k8s.io/docs/overview/
- https://www.tecrobust.com/install-virtualbox-6-0-on-ubuntu-18-04-19-04/
- https://www.virtualbox.org/wiki/Linux_Downloads
- https://kubernetes.io/docs/tasks/tools/install-kubectl/#enabling-shell-autocompletion

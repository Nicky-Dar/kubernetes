Install:

sudo snap install microk8s --classic
Check the status while Kubernetes starts

microk8s status --wait-ready
Auto sudo:

sudo usermod -a -G microk8s $USER
sudo chown -f -R $USER ~/.kube
kubectl command for microk8s:

echo "alias kubectl='microk8s.kubectl'" >> ~/.bashrc
Install CoreDNS and Other Common Service in Kubernetes

microk8s enable dns registry istio
Additional service for dashboard and ingress

microk8s enable dashboard
microk8s enable ingress
Access the Kubernetes dashboard

microk8s dashboard-proxy
Kubernetes is a collection of system services that talk to each other all the time. If you don’t need them running in the background then you will save battery by stopping them. microk8s start and microk8s stop will do the work for you.

Verify Cluster Installation

microk8s kubectl get all --all-namespaces
microk8s inspect
To add Node

microk8s add-node
That command will out put a command that needs to put on the Node you want to add.

For Example :

From the node you wish to join to this cluster, run the following:

microk8s join 192.168.1.230:25000/92b2db237428470dc4fcfc4ebbd9dc81/2c0cb3284b05

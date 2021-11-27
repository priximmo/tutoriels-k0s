%title: K0S
%author: xavki


# K0S : Installation Manuelle


Site : https://k0sproject.io

<br>

curl -sSLf https://get.k0s.sh | sudo sh

<br>

mkdir -p /etc/k0s

<br>

k0s default-config > /etc/k0s/k0s.yaml

<br>

k0s install controller -c /etc/k0s/k0s.yaml

---------------------------------------------------------------------

# K0S : Installation Manuelle

<br>

k0s start

<br>

k0s status

<br>

k0s kubectl get nodes

<br>

k0s token create --role=worker --expiry=100h > token-file

<br>

k0s install worker --token-file token.txt --kubelet-extra-args="--node-ip=192.168.15.111 --address=0.0.0.0"

Note vagrant : /var/lib/k0s/kubelet-bootstrap.conf

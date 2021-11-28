%title: K0S
%author: xavki


# K0S : k0sctl - installer et manager


Site : https://k0sproject.io

<br>

* installation de k0sctl

```
wget https://github.com/k0sproject/k0sctl/releases/download/v0.11.4/k0sctl-linux-x64 -P /usr/local/bin/
mv /usr/local/bin/k0sctl-linux-x64 /usr/local/bin/k0sctl
chmod +x /usr/local/bin/k0sctl
```

-----------------------------------------------------------

# K0S : k0sctl - installer et manager


<br>

```
k0sctl init > k0sctl.yaml
```

<br>

```
apiVersion: k0sctl.k0sproject.io/v1beta1
kind: Cluster
metadata:
  name: k0s-cluster
spec:
  hosts:
  - ssh:
      address: 192.168.15.120
      user: vagrant
      port: 22
      keyPath: ~/.ssh/mke
    role: controller
    privateInterface: enp0s8
```

```
k0sctl apply --config k0sctl.yaml
```

-----------------------------------------------------------

# K0S : k0sctl - installer et manager


<br>

* ajout de kubectl

```
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
apt-get update -qq 2>&1 >/dev/null
apt-get install -qq -y kubectl 2>&1 >/dev/null
mkdir -p /home/vagrant/.kube
chown -R vagrant /home/vagrant/.kube
k0sctl kubeconfig > /home/vagrant/.kube/config
kubectl get pods --kubeconfig kubeconfig -A
```

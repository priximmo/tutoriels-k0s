%title: K0S
%author: xavki


# K0S : Installation Rapide


Site : https://k0sproject.io

<br>

curl -sSLf https://get.k0s.sh | sudo sh

<br>

mkdir -p /etc/k0s

<br>

k0s default-config > /etc/k0s/k0s.yaml

<br>

k0s install controller --single


%title: K0S
%author: xavki


# K0S : k0sctl - installer et manager


Site : https://k0sproject.io

  k0s:
    config:
      spec:
        extensions:
          helm:
            repositories:
            - name: bitnami
              url: https://charts.bitnami.com/bitnami
            charts:
            - name: metallb
              chartname: bitnami/metallb
              version: "1.0.1"
              namespace: default
              values: |2
                configInline:
                  address-pools:
                  - name: generic-cluster-pool
                    protocol: layer2
                    addresses:
                    - 192.168.15.130-192.168.15.150

kubectl --kubeconfig kubeconfig expose pod mynginx --port=8888 --target-port=80 --type=LoadBalancer

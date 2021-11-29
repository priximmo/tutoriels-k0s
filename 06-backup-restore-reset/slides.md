%title: K0S
%author: xavki


# K0S : sauvegarde & restauration


Site : https://k0sproject.io

<br>


	*  certificates (the content of the <data-dir>/pki directory)

  *  etcd snapshot, if the etcd datastore is used

  *  Kine/SQLite snapshot, if the Kine/SQLite datastore is used

  *  k0s.yaml

  *  any custom defined manifests under the <data-dir>/manifests

  *  any image bundles located under the <data-dir>/images

  *  any helm configuration

-------------------------------------------------------------

# K0S : sauvegarde & restauration


<br>

* backup :

```
k0s backup --save-path=<directory>
```

```
k0sctl backup
```

<br>

* resturation :

```
k0s restore /tmp/k0s_backup_2021-04-26T19_51_57_000Z.tar.gz
```

```
k0sctl apply --restore-from /path/to/backup_file.tar.gz
```

-------------------------------------------------------------

# K0S : sauvegarde & restauration

<br>

* uninstall cluster

```
k0s stop
k0sctl reset --config k0sctl.yaml
```

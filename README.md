# CSSHNATOR

cssh for terminator to manager a cluster of nodes through ssh connections
launches multiple splits with ssh connections to each node

## Requirements

Only for Terminator 0.98+

Ubuntu can get from this PPA
https://launchpad.net/~gnome-terminator/+archive/ubuntu/ppa

```bash
sudo apt-add-repository ppa:gnome-terminator/ppa
```

## Usage

To use it, just pass all hostnames as arguments on command line, like that:
```bash
csshnator -l user host1 host2 host3
```

You can also create a config file with all the clusters listed in
$HOME/.csshnatorrc

```
cluster1 = 10.10.100.209 10.10.100.210 10.10.100.211
```

Cluster name followed by space separated list of nodenames/IPs

```bash
ccshnator -l <user> -c <clustername>
```

For more usage information you can consult the help:

```
./csshnator --help

usage: csshnator [-h] [-l LOGIN] [-c CLUSTER_NAME]
                 [cluster_nodes [cluster_nodes ...]]

Open ClusterSSH-like session on Terminator

positional arguments:
  cluster_nodes         Hostnames or user@hostname to connect to, separated by
                        space

optional arguments:
  -h, --help            show this help message and exit
  -l LOGIN, --login LOGIN
                        Login username to pass to all hosts used.
  -c CLUSTER_NAME, --cluster-name CLUSTER_NAME
                        Cluster name is a collection of hosts available on
                        ~/.csshnatorrc file
```

hadoop-single-node-cluster
=======================

This will install a single node hadoop cluster on a machine with single command.  This is intended as use for a dev setup or simple testing.

- This is part of [NeverwinterDP the Data Pipeline for Hadoop](https://github.com/DemandCube/NeverwinterDP)

## Help WANTED - Looking for help with
- [Support Arguments to list and configure which services to install #9](https://github.com/DemandCube/hadoop-single-node-cluster/issues/9)
- [Support for help functionality and also delete services #17](https://github.com/DemandCube/hadoop-single-node-cluster/issues/17)
- [Add command line args change which blueprint template to use #22](https://github.com/DemandCube/hadoop-single-node-cluster/issues/22)
- [Add command line argument to config params to the blueprint #23](https://github.com/DemandCube/hadoop-single-node-cluster/issues/23)
- [Add ubuntu support #24](https://github.com/DemandCube/hadoop-single-node-cluster/issues/24)
- [Document minimum set of services needed to test a Yarn application #25](https://github.com/DemandCube/hadoop-single-node-cluster/issues/25)
- [Document minimum set of configs changes need for Yarn dev setup to reduce container size #26](https://github.com/DemandCube/hadoop-single-node-cluster/issues/26)
- [Test minimal config for Yarn and if works add commandline arg #28](https://github.com/DemandCube/hadoop-single-node-cluster/issues/28)
- [Make all warnings print before exiting #27](https://github.com/DemandCube/hadoop-single-node-cluster/issues/27)


## Installation
- Two Methods
   - Remote - One liner from Github
   - Local - From local copy of the repo

# Remote - One liner  
```
  curl -sSL https://raw.githubusercontent.com/DemandCube/hadoop-single-node-cluster/master/INSTALL-HADOOP | bash -s -- -r
```

# Local - Run from local repo
```
git clone https://github.com/DemandCube/hadoop-single-node-cluster.git
cd hadoop-single-node-cluster
sudo ./INSTALL-HADOOP
```
NOTE: Meant to be run as root/super user

#Minimal Installation (Installs just HDFS, YARN, Zookeeper, MapReduce2, and Tez)
```
git clone https://github.com/DemandCube/hadoop-single-node-cluster.git
cd hadoop-single-node-cluster
sudo ./INSTALL-HADOOP -y
```

#To specify your own custom blueprint file (Not recommended)
```
git clone https://github.com/DemandCube/hadoop-single-node-cluster.git
cd hadoop-single-node-cluster
sudo ./INSTALL-HADOOP -b my-custom-blueprint.json
```

# Services with their components.

## Available components to configure blueprint.json

## What is blueprint?
   A blueprint defines the logical structure of a cluster, without needing informations about the actual infrastructure. Therefore you can use the same blueprint for different amount of nodes, different IPs and different domain names.
   
   The component names are Ambari specific, for convenience you can find the HDP-2.1 services with their components below.
   
- HDFS - DATANODE, HDFS_CLIENT, JOURNALNODE, NAMENODE, SECONDARY_NAMENODE, ZKFC
- YARN - APP_TIMELINE_SERVER, NODEMANAGER, RESOURCEMANAGER, YARN_CLIENT
- MAPREDUCE2 - HISTORYSERVER, MAPREDUCE2_CLIENT
- GANGLIA - GANGLIA_MONITOR, GANGLIA_SERVER
- HBASE - HBASE_CLIENT, HBASE_MASTER, HBASE_REGIONSERVER
- HIVE - HIVE_CLIENT, HIVE_METASTORE, HIVE_SERVER, MYSQL_SERVER
- HCATALOG - HCAT
- WEBHCAT - WEBHCAT_SERVER
- NAGIOS - NAGIOS_SERVER
- OOZIE - OOZIE_CLIENT, OOZIE_SERVER
- PIG - PIG
- SQOOP - SQOOP
- STORM - DRPC_SERVER, NIMBUS, STORM_REST_API, STORM_UI_SERVER, SUPERVISOR
- TEZ - TEZ_CLIENT
- FALCON - FALCON_CLIENT, FALCON_SERVER
- ZOOKEEPER - ZOOKEEPER_CLIENT, ZOOKEEPER_SERVER



# Compatibility

OS
=======
* CentOS 6.5
```
Should be good on RED-HAT Family of Distros
```
ENVIRONMENTS (Been tested on)
- vagrant (centos 6.4,6.5 x86_64)
- ec2 (centos 6.4,6.5 x86_64)
- digitalocean (centos 6.4,6.5 x86_64)

# Usage


* * *
## INSTALL-HADOOP
```
Usage: INSTALL-HADOOP [-rfyb]
This will
    
    -y,                              (Optional) MINIMAL   - Installs a minimal installation - just HDFS, Yarn, MapReduce, Tez, and Zookeeper
    -b [blueprint file],             (Optional) BLUEPRINT - Specify your own custom blueprint file
    -r,                              (Optional) REMOTE    - Pulls all templates as remote 
    -f,                              (Optional) FORCE     - Forces in install if less them 4 gigs of ram
```

* * *

## Contributing

See the [NeverwinterDP Guide to Contributing] (https://github.com/DemandCube/NeverwinterDP#how-to-contribute)



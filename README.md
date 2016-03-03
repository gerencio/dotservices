# dotservices
Systemd services for running  mesos-veronica images from docker.



How to use

* clone our repo in your system with systemd service.
* put dockerdata in your favorite path
* modify every .service when marked with "<>" tag and complete with your info 

example:


```bash
Environment=VERONICA_DOCKER_VERSION=0.1
Environment=CLUSTER=<YOUR CLUSTER NAME> 
Environment=ZOOKEEPER_ENDPOINT=zk://<YOUR-DOMAIN>:2181
Environment=HOSTNAME=<YOUR-DOMAIN>
Environment=MOUNTPOINT=<WHERE YOU PUT "dockerdata" FILE>
```

change for this:

```bash
Environment=VERONICA_DOCKER_VERSION=0.1
Environment=CLUSTER=my-power-super-cluster
Environment=ZOOKEEPER_ENDPOINT=zk://this.mydomain.com:2181
Environment=HOSTNAME=this.mydomain.com
Environment=MOUNTPOINT=/home/core/
```

* in dockerdata/conf directory, change for your password, this is used for mesos stack auth between nodes.
* in dockerdata/nginx/conf.d , change the .config, place your hostname
* in dockerdata/nginx/conf.d, create your .htpassword file. 


* run all services with systemctl , in this order

- zookeeper
- mesos-master
- mesos-slave
- chronos
- nginx


* this repo work with single server conf, but can be expand.





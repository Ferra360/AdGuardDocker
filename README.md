# AdGuardDocker
2 instances of AdGuard on Docker with macvlan

## Prerequisites
Docker and Docker compose installed in your machine

## Initial setup

A docker macvlan should be created in your machine
```
docker network create -d macvlan -o parent=yourNetCardId --subnet=192.168.1.0/24 --gateway=192.168.1.1 mac_net
```
You should change the subnet and gateway to match your actual LAN setup.
That will allow to have multiple instances of AdGuard in the same host without port conflicts.

Then simply run 
```
docker-compose up -d
```

And the 2 containsers for Adguard should be instantiated and ready to be used.

In the Docker-compose.yml file a couple of changes are required to adapt it to your LAN setup, the ipv4 that you would like to assign to each of the 2 instances.

At that point, you can just open your browser and navigate to 

IP_Instance1:3000

and 

IP_Instance2:3000

To start the process to configure the 2 instances.

The process will guide you through the setup of Adguard in your LAN for a single device or multiple, dependings on your choices.

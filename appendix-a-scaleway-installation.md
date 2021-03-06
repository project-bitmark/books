# ![](https://www.scaleway.com/img/scaleway.a5b3.svg)

# Scaleway Installation

Scaleway is an example of a Cloud server well suited to run Bitmark Storage.  Below is a guide to setting up a server on scaleway, and similar steps can be used on other cloud providers.

---

### 1. Instance prep 

**Select A Server**

Scaleway offers a number of servers.  At time of writing it is possible to run a server with unmetered bandwidth, 50 GB of storage and running Ubuntu 16.04 for 2.99 EUR per month.  This is the target used in this guide.

**Log in to the machine**

To log into a scaleway server locate the IP addres and ssh to root@ip-address.  This will log you in as root.

**Create a User**

It is not desirable to run as root, so it is possible to add a user, ubuntu is selected here.

```
useradd -m ubuntu
sudo usermod -a -G sudo ubuntu
passwd ubuntu
```

 You will also want to copy the ssh key into the .ssh directory to allow login via ubuntu@ip-address

```
mkdir /home/ubuntu/.ssh
cp -rp .ssh/* /home/ubuntu/.ssh
chown ubuntu:ubuntu /home/ubuntu/.ssh/*
```

```
chsh -s /bin/bash ubuntu
```

 Is useful to change the shell to bash

**Open ports**

It will be necessary to open port 443 on the scaleway interface

---

### 2. Installation

**Install pre requisites**

As per Installation chapter

```
sudo apt-get install git haproxy letsencrypt npm
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo ln -s /usr/bin/nodejs /usr/bin/node
sudo npm install -g n
sudo n latest
```

**Install bitmark storage**

As per Installation

**Run bitmark storage**

Optionally under pm2 and haproxy and letsencrypt

---

### 3. Initialization

**Point domain to IP**

Normally you will run under a domain name which can set an "A" record pointing to the IP address of the server

**Create First User**

By pointing at the root of the domain it is possible to create a new user that will work under bitmark storage.  You will be guided to installing your keys and to your bitmark passport located under profile/card

**Creating more Users**

Recommended would be to create users in their own home directory and their own quota.  The path for UI creation is '/api/accounts'.  It is then possible to recieve bitmarks on an OTC basis for provisioning content, and being positively marked.

Congratulations you have now created Bitmark Storage and Bitmark Passport provider!


# Installation

## Audience

Currently aimed at people running their own cloud storage or home storage that are able to understand running a server or follow instructions.

## Pre requisites

* A server with some disk space is required to run bitmark storage.

* nodejs -- _Version 6 or higher_

* git

* \(optional\) having your own domain is an advantage

## Instructions

### Instructions to run bitmark storage

1. Clone the bitmark storage repo

   `git clone https://github.com/project-bitmark/bitmark-storage && cd bitmark-storage`

2. run

   `npm install`

3. run

   `node bin/solid init`

   to generate a config \(or use a pre determined config and keys\)

   to generate keys see the section below : generating keys

   Note: this is the hardest step -- visit slack for help -- see also answering the init questions below

4. install pm2 \( npm install -g pm2 \)

5. run

   `node bin/solid -v start`

\(Optional\)

1. use pm2 to ensure the process restarts automatically

2. \(optional\) forward a port to the outside world if not already

3. \(optional\) if running on your home pc add a dyndns service like noip.com.

4. \(optional\) CNAME a domain to your storage server

5. \(optional\) remove SSL warnings using letsencrypt

#### Answering the init questions:

It is possible to use the defaults for most questions. Some notes:

> Path to the folder you want to serve.

This is where you want to host files. Perhaps use ~/data/

#### Generating keys

There are two ways. 1 is locally

```
openssl genrsa 2048 > ./privkey.pem
openssl req -new -x509 -nodes -sha256 -days 3650 -key ./privkey.pem -subj '/CN=*.localhost' > ./fullchain.pem
```

The second way is to use [letsencrypt](https://letsencrypt.org/)

## Issue tracker

[https://waffle.io/project-bitmark/bitmark-storage](https://waffle.io/project-bitmark/bitmark-storage)


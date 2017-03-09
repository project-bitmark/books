# An ideal way to doCredit System

The following is an example of a credits system that provisions users with 1GB each.  At time of writing the storage is priced roughly at cost at 1 Bitmark per GB / month, equating also to roughly 1 mark for a GB/h.

**Install up Webcredits**

```
sudo npm install -g webcredits
```

**Set up MySql**

```
sudo apt-get install mysql
```

You will need an sql user

```
sudo apt-get install mysql
sudo mysql -u root

CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```

**Creating a Decentralized Wallet**

It helps to create a wallet in order for user to pay funds.  The excellent mneumonic code generator is an excellent way to do this

[https://iancoleman.github.io/bip39/](https://iancoleman.github.io/bip39/)

First create a private seed \(preferably on a secure machine\) and use it to generate a public and private HD key.

Keep the private key safe or on a remote machine.

The public key can be published on your storage system.

**Decentralized Deposits**

From either the public key or the private key user deposit addresses can be generated.  The safest way to do this is using the public key.


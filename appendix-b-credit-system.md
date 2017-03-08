# Credit System

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

https://iancoleman.github.io/bip39/




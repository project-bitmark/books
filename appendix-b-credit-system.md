# Credit System - Example

The following is an example of a credits system that provisions users with 1GB each.  At time of writing the storage is priced roughly at cost at 1 Bitmark per GB / month, equating also to roughly 1 mark for a GB/h.  This builds on the example in the previous chapter of setting bitmark storage up on scaleway.  However it is possible run the same system on any desktop computer.

---

### 1. Instance prep 

**Install Webcredits**

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

---

### 2. **Creating a Decentralized Wallet**

It helps to create a wallet in order for user to pay funds.  This mneumonic code generator is an excellent way to do this

[https://iancoleman.github.io/bip39/](https://iancoleman.github.io/bip39/)

First create a private seed \(preferably on a secure machine\) and use it to generate a public and private HD key.

Keep the private key safe or on a remote machine.

The public key can be published on your storage system.

---

### 3. **Decentralized Deposits**

From either the public key or the private key user deposit addresses can be generated.  The safest way to do this is using the public key.

The suggested mentod is to create a URI for each user, then use that to derive a unique bitmark address from the public key / URI pair.  When that account has deposits, then credits can be added to the system.

The following code can do this:

[https://github.com/quantumpayments/hdwallet/blob/master/lib/util.js](https://github.com/quantumpayments/hdwallet/blob/master/lib/util.js)

webidAndPubKeyToAddress / webidAndPrivKeyToAddress

---

### 4. Managaging Storage Credit

Using [webcredits](http://webcredits.org/) it is then possible add credits to each user's account.

A script could run monthly and charge 1 BTM for each user, assuming they have a balance.  It can also populate an account balance file, and let the user know if they need to top up their credit.

TODO: A and automated reference script example, that runs, say, once per hour, could be released under open source

See Also: How to set a disk quota : [https://www.howtoforge.com/tutorial/linux-quota-ubuntu-debian/](https://www.howtoforge.com/tutorial/linux-quota-ubuntu-debian/)


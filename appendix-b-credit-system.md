# Credits System

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




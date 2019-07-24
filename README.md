# Linux Server Configuration

> A baseline installation of a Linux server and prepare it to host web applications, secure your server from a number of attack vectors, install and configure a database server, and deploy one of your existing web applications onto it.

* IP Address: 54.85.17.85
* Accessible SSH port: 2200
* Application URL: [http://54.85.17.85.xip.io/]()

## Instruction to configure the server

1. **SSH into server**

```
$ ssh -i ~/.ssh/aws_key ubuntu@54.85.17.85
```

2. **Update all packages**

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

3. **Change timezone to UTC**

```
$ sudo dpkg-reconfigure tzdata
```

4. **Create new user named grader**

```
$ sudo adduser grader
```

* To give grader sudo access

```
$ sudo nano /etc/sudoers.d/grader
```

* Add the following text to this file `grader ALL=(ALL:ALL) ALL`

5. **Setup SSH keys for grader**

```
$ sudo su - grader
$ mkdir .ssh
$ touch .ssh/authorized_keys
$ sudo chmod 700 .ssh
$ sudo chmod 600 .ssh/authorized_keys
$ nano .ssh/authorized_keys
```

* Paste the content of Public key (aws_key.pub) created on local machine.

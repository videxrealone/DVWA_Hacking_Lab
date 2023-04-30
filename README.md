# DVWA Hacking Lab

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![image](https://user-images.githubusercontent.com/91763346/235360139-354ff711-3efa-4c40-8510-ad3800523c4a.png)

DVWA is made with PHP and MySQL for security professionals or aspiring security professionals to discover as many issues as possible and exploit some of the most common vulnerabilities of web platforms like SQL injection, Cross Site Scripting (XSS), Cross Site Request Forgery (CSRF), and more.

# DVWA Preconfiguration

**Note**: 
This guide is for beginners. If you’re unable to complete any of the steps or encounter any error message during the installation. I encourage you to use StackOverflow for an answer.

## Prerequisites

* **Hypervisor**: VirtualBox
* **Linux Distro**: Kali Linux (preferably) or any other linux-based distro.

* **IMPORTANT** : 
we need to use a virtual machine and not a connected server because DVWA is really vulnerable and should only be installed on your virtual machine with NAT.

## Upgrading the System
Because DVWA is an open-source project, it's constantly being updated and improved. That's why we need to make sure that our system is up-to-date.
We just need to run the following commands:

```
$ sudo apt-get update && sudo apt upgrade -y
```

## Configuring our Web Server (in our case Apache2)

To install apache2, we just need to run the following command:

```
$ sudo apt install apache2
```
To test it out, we just need to start it.
```
$ sudo systemctl start apache2
```
Now we just need to check our localhost ( 127.0.0.1 ).

![image](https://user-images.githubusercontent.com/91763346/235361216-20262506-209f-4dfe-b150-dfc856cc5669.png)

# Setting up DVWA

In this step we need to get the container from DockerHub.

* **Link** :https://hub.docker.com/r/vulnerables/web-dvwa/

## Installing Docker

The easiest way to get the DVWA working is through a ready-to-use Docker Container and for that we need to have Docker Engine Installed.
We just need to run the following command:

```
$ sudo apt install docker.io -y
```

## Getting the DVWA Docker Container

![image](https://user-images.githubusercontent.com/91763346/235363467-3b54f5bd-e1a4-49a0-9b5e-3f52b6abdbb6.png)

* **Link** : https://hub.docker.com/r/vulnerables/web-dvwa/

We just need to use **docker pull** to get the container.
```
$ docker pull vulnerables/web-dvwa
```





# Creating your Very First Local Ethical Hacking Lab with Damn Vulnerable Web Application

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
$ sudo apt update && sudo apt upgrade -y
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

![image](https://user-images.githubusercontent.com/91763346/235363467-3b54f5bd-e1a4-49a0-9b5e-3f52b6abdbb6.png)

In this step we need to get the container from DockerHub.

* **Link** :https://hub.docker.com/r/vulnerables/web-dvwa/

## Installing Docker

The easiest way to get the DVWA working is through a ready-to-use Docker Container and for that we need to have Docker Engine Installed.
We just need to run the following command:

```
$ sudo apt install docker.io -y
```

## Getting the DVWA Docker Container

We just need to use **docker pull** to get the container.
```
$ docker pull vulnerables/web-dvwa
```
## Running the Docker Image
The best thing when it comes to Docker, is that with just a simple command we can run the container.

![11](https://user-images.githubusercontent.com/91763346/235369541-8f1c433b-e164-4c5c-b7e5-00feffd97eb9.PNG)

```
$ docker run --rm -it -p 80:80 vulnerables/web-dvwa
```
# Accessing the Damn Vulnerable Web Application Platform

Now after running the Docker image, we have a ready-to-use **DVWA Platform** via our **localhost**.
We just have to access **http://localhost/login.php**.

## Accessing the Platform from the Docker Host (in our case the VM)

![image](https://user-images.githubusercontent.com/91763346/235369873-45750806-f3c3-4bf6-9413-f7c934effba7.png)

We just have to access **http://localhost/login.php**.

## Accessing the Platform from the Any Network Host

This is somewhat of the trickiest part in the guide.
We need to make sure that:

* The Virtual Machine's Network mode is on **Bridged** so that it can be accesible from the Host machine.
* Making sure that we're connected to a network so that it can have an IP (even if we don't have Internet)

In our case, our machine's IP is 
* **IP**: 192.168.1.156

We just have to access the **http://192.168.1.156**.

![image](https://user-images.githubusercontent.com/91763346/235370285-2d219104-65d0-4b5a-8985-535760ae494c.png)

# Epilogue

I advise you to take your time with the **Low** difficulty and working your way up from there.
I also found an interesting repo made by @**keewenaw**.
* **Link**: https://github.com/keewenaw/dvwa-guide-2019

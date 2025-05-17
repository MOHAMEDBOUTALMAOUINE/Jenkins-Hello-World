## Pre-requisites

**You should know** `Docker`, `basic CI-CD concept` & `basics of what Jenkins` is used for

**You should have** `Linux OS` like Ubuntu, `Java` (OpenJDK 11) & `Docker` installed

## Description

This project was created to install Jenkins on a local machine (Ubuntu 16.04) and create a basic pipeline with GitHub & Docker

We will be doing is

* Installing Jenkins and running it, on a local machine
* Creating a docker image
* Pushing it to docker hub using Jenkins' pipeline

___

### Installing Jenkins

1. **Add repository** keystream  
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```
You must get a response printed as `OK`

2. Now **add the Debian package** to your `sources.list`  
```
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

3. Now, **update system** 
```
sudo apt update
```

4. Finally, **install Jenkins**
```
sudo apt install jenkins
```

Now, **Jenkins is installed** in your system and is ready to run.


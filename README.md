<<<<<<< HEAD
# AWS Infrastructure Creation using Terraform

Helpful Terraform Links:
- [Terraform Language Documentation](https://www.terraform.io/docs/language/index.html)
- [Resource: aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [Resource: aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance)

## Step 0: Initialize Terraform
```
terraform init
```

## Step 1: Plan Resources
```
terraform plan -var-file="vars/dev-east-2.tfvars"
```

## Step 2: Apply Resources
```
terraform apply -var-file="vars/dev-east-2.tfvars"
```

## Step 3: Commands to get the Jenkins admin password via command line
```
chmod 400 <keypair>
ssh -i <keypair> ec2-user@<public_dns>
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
## Some Useful Commands
```
#To get context information of kubernetes cluster
cat /home/ec2-user/.kube/config 

#To create namespace in kubernetes cluster
kubectl create namespace test

#To get deployments in a namespace in kubernetes cluster
kubectl get deployments --namespace=test 

#To get services in a namespace in kubernetes cluster
kubectl get svc --namespace=test 

#To delete everything in a namespace in kubernetes cluster
kubectl delete all --all -n test 

#To delete unused docker images to cleanup memeory on system 
docker system prune  

#To delete a docker image
docker image rm imagename  

#To Create EKS cluster
eksctl create cluster --name kubernetes-cluster --version 1.31 --region us-east-2 --nodegroup-name linux-nodes --node-type t2.xlarge --nodes 2 

#To Delete EKS cluster
eksctl delete cluster --region=us-east-2 --name=kubernetes-cluster #delete eks cluster
```

## Step 4: Cleanup Terraform Resources
```
terraform destroy -var-file="vars/dev-east-2.tfvars"
=======
[![Build Status](https://travis-ci.org/k-tamura/easybuggy.svg?branch=master)](https://travis-ci.org/k-tamura/easybuggy)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![GitHub release](https://img.shields.io/github/release/k-tamura/easybuggy.svg)](https://github.com/k-tamura/easybuggy/releases/latest)

EasyBuggy Vulnerable Web App Modified:baby_symbol:
=

EasyBuggy is a broken web application in order to understand behavior of bugs and vulnerabilities, for example, [memory leak, deadlock, JVM crash, SQL injection and so on](https://github.com/k-tamura/easybuggy#clock4-easybuggy-can-reproduce).

![logo](https://raw.githubusercontent.com/wiki/k-tamura/easybuggy/images/mov_eb.gif)

:clock4: Quick Start
-

    $ mvn clean install

( or ``` java -jar easybuggy.jar ``` or deploy ROOT.war on your servlet container with [the JVM options](https://github.com/k-tamura/easybuggy/blob/master/pom.xml#L204). )

Access to

    http://localhost:8080

:clock4: Quick Start(Docker)
-

    $ docker build . -t easybuggy:local # Build container image
    $ docker run -p 8080:8080 easybuggy:local # Start easybuggy

Access to

    http://localhost:8080

### To stop:

  Use <kbd>CTRL</kbd>+<kbd>C</kbd> ( or access to: http://localhost:8080/exit )

:clock4: For more detail
-
   
See [the wiki page](https://github.com/k-tamura/easybuggy/wiki).

:clock4: Demo
-

This demo shows: Start up -> Infinite Loop -> LDAP Injection -> UnsatisfiedLinkError -> BufferOverflowException -> Deadlock -> Memory Leak -> JVM Crash (Shut down)

![demo](https://github.com/k-tamura/easybuggy/blob/master/demo_eb.gif)

:clock4: EasyBuggy can reproduce:
-

* Troubles

  * Memory Leak (Java heap space)
  * Memory Leak (PermGen space)
  * Memory Leak (C heap space)
  * Deadlock (Java)
  * Deadlock (SQL)
  * Endless Waiting Process
  * Infinite Loop
  * Redirect Loop
  * Forward Loop
  * JVM Crash
  * Network Socket Leak
  * Database Connection Leak
  * File Descriptor Leak 
  * Thread Leak 
  * Mojibake
  * Integer Overflow
  * Round Off Error
  * Truncation Error
  * Loss of Trailing Digits

* Vulnerabilities

  * XSS (Cross-Site Scripting)
  * SQL Injection
  * LDAP Injection
  * Code Injection
  * OS Command Injection (OGNL Expression Injection)
  * Mail Header Injection
  * Null Byte Injection
  * Extension Unrestricted File Upload
  * Size Unrestricted File Upload
  * Open Redirect
  * Brute-force Attack
  * Session Fixation Attacks
  * Verbose Login Error Messages
  * Dangerous File Inclusion
  * Directory Traversal
  * Unintended File Disclosure
  * CSRF (Cross-Site Request Forgery)
  * XEE (XML Entity Expansion)
  * XXE (XML eXternal Entity)
  * Clickjacking

* Performance Degradation

  * Slow Regular Expression Parsing
  * Delay of creating string due to +(plus) operator
  * Delay due to unnecessary object creation

* Errors

  * AssertionError
  * ExceptionInInitializerError
  * FactoryConfigurationError
  * GenericSignatureFormatError
  * NoClassDefFoundError
  * OutOfMemoryError (Java heap space) 
  * OutOfMemoryError (Requested array size exceeds VM limit)
  * OutOfMemoryError (unable to create new native thread)
  * OutOfMemoryError (GC overhead limit exceeded)
  * OutOfMemoryError (PermGen space)
  * OutOfMemoryError (Direct buffer memory)
  * StackOverflowError
  * TransformerFactoryConfigurationError
  * UnsatisfiedLinkError

:clock4: EasyBuggy clones:
-
* [EasyBuggy Boot](https://github.com/k-tamura/easybuggy4sb)

  EasyBuggy clone build on Spring Boot

  ![logo](https://raw.githubusercontent.com/wiki/k-tamura/easybuggy/images/mov_ebsb.gif)

* [EasyBuggy Bootlin](https://github.com/k-tamura/easybuggy4kt)

  EasyBuggy clone build on Spring Boot and written in Kotlin

  ![logo](https://raw.githubusercontent.com/wiki/k-tamura/easybuggy/images/mov_ebkt.gif)

* [EasyBuggy Django](https://github.com/k-tamura/easybuggy4django)

  EasyBuggy clone build on Django 2 and written in Python

  　![logo](https://github.com/k-tamura/easybuggy4django/blob/master/static/easybuggy.png)
>>>>>>> ce201d7 (my devsecops code)

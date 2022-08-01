# CI/CD AppDeployUsingJenkinsOnGKE

## Introduction
Build a CI/CD Jenkins Pipeline to Deploy a web application on Kuberentes cluster system

## Prerequisites
* First we need to create a Kuberenetes Cluster from any cloud service provider
* Second, Jenkins needs to be installed as Kuberenetes deployment
* Setup the suitable credientals to make the Jenkins deployment authorized kuberenetes admin


You will find all the Prerequisites project in the link below:
### [CI/CD Jenkins Deploy On GKE](https://github.com/AhmedRezk95/CI-CD-JenkinsDeployOnGKE)


## Steps
1- build a dockerfile for your application

![image](https://user-images.githubusercontent.com/30655799/182197961-fa21d0b2-c8ce-4728-a8d3-5a34398dee5a.png)

2- In the GCP architecture we use in [CI/CD Jenkins Deploy On GKE](https://github.com/AhmedRezk95/CI-CD-JenkinsDeployOnGKE), we created a container registery service to host the image for future use

3- tag the dockerfile to gcp container registery service name and push it there
```bash
docker tag <docker-image> <container-registery-service-name>
docker push <container-registery-service-name>
```
Results:

![image](https://user-images.githubusercontent.com/30655799/182199134-ea863f11-602e-4a9e-a9ee-27bc16e48f5d.png)

4- create Jenkinsfile

![image](https://user-images.githubusercontent.com/30655799/182199600-456c4534-f54d-472d-9267-f490ced4311d.png)

5- login to Jenkins, create a new pipeline and set the git repo

![image](https://user-images.githubusercontent.com/30655799/182199674-1ea143b4-33ee-4bea-803b-b053b55f54ee.png)

6- build the pipeline
 
![image](https://user-images.githubusercontent.com/30655799/182199742-111e4063-0bb8-4701-81d1-393d345051ea.png)

## Final Results
* From Jenkins prespective

![image](https://user-images.githubusercontent.com/30655799/182199837-7852e710-1d92-4b51-a478-037af54805ba.png)

* From Kuberenetes prespective:
    - create deployment with image hosted inside  
    - create service (type loadbalancer) in order get the appliaction online

![image](https://user-images.githubusercontent.com/30655799/182200458-20f851f6-dde8-4b6e-9665-61042330ed4a.png)

* From web prespective:

![image](https://user-images.githubusercontent.com/30655799/182201121-fcf0dc86-e639-4e9f-8229-08cb675b8d2d.png)




<!-- $theme: default -->
<center>
<h1>'Bad' Infrastructure</h1>


<img src="https://mandarin-uploads.s3.amazonaws.com/uploads/2016/08/census-fail.png" width="49%" style="display: inline-block"/>
<img src="https://i.imgflip.com/zuxwm.jpg" width="49%" style="display: inline-block"/>
</center>

---

<center>
<h1>Building Web Apps on Google's Infrastrucutre</h1>

<h2>Presented by</h2>

<img src="https://avatars3.githubusercontent.com/u/5687681?v=4&s=460" 
      style="width: 15%; border-radius: 100%"/>
## Eric Jiang

###### _This presentation's code/slides can be found on [https://github.com/lorderikir/googlecloud-techtalk](https://github.com/lorderikir/googlecloud-techtalk)_

<div>
    <img class="custom-footer-1" src="https://www.chef.io/wp-content/uploads/2017/03/google-cloud-platform-1024x246.png" style="bottom: 0; width: 60%"/>
</div>

</center>

---

# Talk Summary

1. Introduction to Google Cloud
2. What is Google App Engine
  a. GAE Environments
  b. What is Scaling and Why is it Important?
3. Deep-Dive
  a. Deploying a simple API to Google App Engine
4. Other Tools

[NOTE]: You can play with Google Cloud Platform off your student accounts

---

# Introduction

## What is Google Cloud Platform?
> Google Cloud Platform lets you build and host applications and websites, store data, and analyze data on Google's scalable infrastructure.

Composes of many applications, such as:
- Google App Engine (GAE)
- Google Container Engine (GCE)
- Google DataStore
- Cloud ML (built off _TensorFlow_)
- and much more

> Did you know that Firebase and API.AI are both on GCP
---
<center>
<img src="https://www.glintech.com/img/30704315/Google%20Cloud%20Platform%20Products%20%281%29.png" width="100%" />
</center>

---

# Google App Engine
- designed around the fact that _Google just can't send everyone into their datacentre(s) and update applications across their many datacenters_
- Built off Remote Deployments

| Language   | Environment     |
|------------|-----------------|
| Java 7  (and Kotlin<sup>1</sup>)   | Standard        |
| Java 8     | Standard (Beta)/Flexible        |
| Node.js    | Flexible        |
| Python 2.7 | Standard        |
| Python 3.5 | Flexible        |

<sup>1</sup> This for you Kotlin fans out there

---


**Standard Environments** run in a specialised envrionment. Though building the application is more constrained then other environments, it means scaling up is faster.

**Flexible Environment** applications run off a Docker container, it is designed for applications that recieve constant traffic. When deployed they are Google Compute Engine VM<sup>2</sup>

<div style="margin-top: 200px">
<sup>2</sup> Because they run off Docker, you can write your own Dockerfile Configuration to deploy
</div>

---

<center>
<img src="https://image.slidesharecdn.com/googleappengineatdockercon2014-140613154831-phpapp02-140801195253-phpapp01/95/docker-on-google-app-engine-7-638.jpg?cb=1407094857" width="100%"/>
</center>

---

<center>
<h1>Horizontal vs Veritcal Scaling</h1>
<h3>Me when I look at Scaling:</h3>
<img src="https://i.imgflip.com/1wqhrk.jpg" style="min-height: 100%"/>
</center>

---

<center>
<img src="https://i.stack.imgur.com/On3tO.png" height="100%" />
</center>

---

## Benefits of Horizontal Scaling
- Dynamic scaling allows spinning up more instances and nodes faster, i.e. if you suddenly get a influx of traffic
- Vertical Scaling is limited to capacity of resources, simply adding more resources

- Just simplying load testing isn't good enough, examples of this include Niantic (PokemonGo) and Australian Census 2016

---

<div style="text-align: center">
<h1>Demo Section</h1>
<img src="https://i.imgflip.com/1w3nb6.jpg" height="450px"/>
</div>

---

# Installing the SDK

1. Install the SDK over https://cloud.google.com/sdk/downloads
2. Authenticate Using `gcloud init` (login using your Monash Student Account)
4. You may need Java (JDK 1.8) and Maven (MVN) Installed if you are using the package provided. 

> If you are interested in developing on the framework provided I strongly suggest for you to read the docs.

**Framework**: http://tinyurl.com/mplan-baseapi

---

# Deploying the App

- Reason's why we are using a Java Environment is that since its developed directly on the Standard Environment, it scales up way faster.
---

# Other Tools Available  on GCP that you play with

- Cloud ML (Google Cloud Machine Learning) which is built off TensorFlow 
- Compute Engine - Google VMs
- Container Engine - built off Kubernetes and allows deployment of custom applications
- Cloud Storage - CDN provider of files (like _Amazon S3_)
- Network Balancer - for Load Balancing of traffic for your applications
- Cloud ML APIs such as Natural Language Processing, Data Loss Prevention, etc.

---

# Questions
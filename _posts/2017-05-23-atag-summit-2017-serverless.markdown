---
layout: post
title:  "ATAG Summit 2017, Serverless Edition"
ref: atag-summit-2017
date: 2017-05-23
lang: en
---

Buenos Aires, Friday May 12th, 6.30 AM local time. I’m waiting in the car at a corner of my neighborhood San Cristóbal to carpool a colleague. Two hours later, after dodging a blocked highway with a hardly working GPS, we arrive at Finca María Cristina to meet with ATAG.

ATAG stands for *Argentina Technology Architecture Group*. It’s an internal community with fewer than 50 talented individuals from different teams within the company, who are passionate about Technology Architecture and meet up regularly to share and capitalize knowledge from their day-to-day experience.

Fellows from Buenos Aires, Rosario and La Plata offices keep arriving at the venue. 9 AM sharp the wait comes to an end, the key-note speaker kicks off our annual *ATAG Summit*.

The two-day agenda was crammed with presentations and hands-on workshops around hot topics in architecture, such as Serverless, DevOps and IoT, and would be run by ATAG members themselves:  
* Transformation to an intelligent enterprise
* AWS DynamoDB
* Cloud computing
* AWS API Gateway
* AWS Lambda
* Hybrid storage solutions
* Introduction to Angular 2 / Architecture patterns on SPA
* AWS IoT
* Cloud vision for the future
* Intigua, Present and future
* AWS CodePipeline

As with AWS CodePipeline, the summit itself felt as if one was being transported through a pipeline. Every workshop was related to the other with a unifying thread, and the artifacts built during an activity served as input for the next one. As a result, at the end of the event some of us had built a complete Serverless Webapp.

In a recursive way, the Webapp built along the workshops allowed us to vote the presentations given during the summit:  
![ATAG Summit 2017 Voting Serverless Webapp]({{ site.url }}/assets/atag-voting-app.png "ATAG Summit 2017 Voting Serverless Webapp")

The Webapp was developed and deployed over a composition of multiple Amazon platform services, following the Serverless computing approach:  
*"Serverless computing, also known as function as a service (FaaS), is a cloud computing code execution model in which the cloud provider fully manages starting and stopping of a function's container platform as a service (PaaS) as necessary to serve requests, and requests are billed by an abstract measure of the resources required to satisfy the request, rather than per virtual machine, per hour"* (Wikipedia).

The pieces that make up the Webapp are the following:  
* AWS S3 Bucket, serving Angular HTML, TypeScript and CSS static files
* AWS API Gateway, exposing a REST API to attend the HTTP requests from Angular
* AWS Lambda function, processing the calls received from the API, using C# (.NET Core)
* AWS DynamoDB table, persisting the presentations and its votes

During the AWS Lambda workshop, the function was coded using Node.JS. However, with the team I was working with we decided to take an alternative path and use .NET Core C# instead. As a follow-up of the summit, I created a GitHub repository where my team continued working along the week following the event. We included the Angular Webapp, the C# Lambda function, the DynamoDB/S3 AWS CLI scripts, and we’ll keep it open in case we come up with any changes:  
<a href="https://github.com/jebarsoba/atag-summit-2017-serverless" target="\_blank">https://github.com/jebarsoba/atag-summit-2017-serverless</a>

One of the takeaways I value the most from the event is that I left with real working software, created with people who share my interests. First ATAG Summit for me. Also, first blog post!

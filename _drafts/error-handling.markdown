---
layout: post
title:  "Sumo Logic, an error handling strategy for Web API"
---

I used to work for a book publishing company. Once a year the firm mounted a huge stand within the most important book fair in the country. I had contributed to the development of an ad-hoc Point of sale system for the checkout lanes. I was there at the opening when the program had a blocking error that prevented the cashiers from serving customers. While we were trying to solve the issue people started to abandon the lanes. The longer the error persisted the longer the lane grew, and so the more money the publisher lost.

At the time of writing I'm working for a technology services firm. I'm in charge of an API that is essential for the systems that support the sales process of the company. Recently we had an issue in Production that left us without database for two hours and affected 10,000 users approximately. How many business opportunities did the company lose during that downtime?

As we can see, *__errors equal money loss__*. Numbers will depend on the size of the organization and its revenue. To illustrate, the average cost of downtime for a Fortune 500 company is $528,800 per hour (add RefME).

That's why it's critical to put in place an error handling strategy. The way I see it, *__an error handling strategy is the prevention and mitigation of errors, whose ultimate goal is to reduce money loss__*.

*__Prevention__* is the set of practices and tools which allow us *__to avoid errors__*.

*__Mitigation__* is the set of practices and tools which allow us *__to respond to errors in a timely manner, to find the root cause faster and to troubleshoot sooner__*.

Prevention includes the following elements:

* **Keepalive health check**: an automated periodic call performed to the application in order to alert us if the system is unavailable.
* **Threshold alerts**: a threshold alert is a warning message triggered after the expected limits for a certain metric are exceeded. For instance, an alert fired after a 75% increase in memory consumption over baseline.
* **Overall application performance dashboard**: a single page real-time user interface that provides an at-a-glance view of the system's KPIs, such as average response time, number of requests per minute and errors in the last hour.

Mitigation consists of the following items:

* **Error alerts**: an error alert is a notification immediately sent when the failure takes place.
* **Log search engine**: a single point of access to perform queries and analyze aggregated log data from multiple servers.

But, How can we bring into play all these set of different tools and practices without dying in the attempt? Here is when *__Log management__* comes to the rescue.

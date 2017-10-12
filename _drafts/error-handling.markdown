---
layout: post
title:  "Sumo Logic, an error handling strategy for ASP.NET Web API"
ref: error-handling
lang: en
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

But, How can we bring into play all these sets of diverse practices and tools without dying in the attempt? Here is when *__Log management__* comes to the rescue.

> Log Management (LM) comprises an approach to dealing with large volumes of computer-generated log messages (add RefME).

*__LM allow us to put into action a successful error handling strategy__*, as it covers the sets of practices and tools needed to prevent and mitigate errors.

Fortunately, there are several products in the market which provide a comprehensive out-of-the-box Log Management solution. For example **Sumo Logic**, an SaaS offering, and **Logstash**, its open-source counterpart.

*__Proper logging in your code is a prerequisite__* to feed the LM tool and let it do its magic. From my experience, at least two points should be considered to get the most from the product:

* **Logging generic information about every request**: keeping track of data such as user, URI, HTTP response code and response time for each request our application receives will enable the *_“Threshold alerts”_* and *_“Overall application performance dashboard”_* prevention tools.
* **Catching all exceptions and logging relevant information about them**: having in place a mechanism to ensure that exceptions, both handled and unhandled, are logged will enable the *_“Error alerts”_* mitigation tool. Registering data such as exception message, stack trace and user will help us to better understand errors and provide a solution rapidly.

Now that we have covered what an error handling strategy is about and what do we need to implement it, *__let’s see how can we leverage Sumo Logic Log Management tool in an ASP.NET Web API REST service__*.

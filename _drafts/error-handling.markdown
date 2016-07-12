---
layout: post
title:  "Web API + Sumo Logic: An Error handling strategy"
---

I used to work for a book publishing company. Once a year the firm mounted a huge stand within the most important book fair in the country. I had contributed to the development of an ad-hoc Point of sale system for the checkout lanes. I was there at the opening when the program had a blocking error that prevented the cashiers from serving customers. While we were trying to solve the issue people started to abandon the lanes. The longer the error persisted the longer the lane grew, and so the more money the publisher lost.

At the time of writing I'm working for a technology services firm. I'm in charge of an API that is essential for the systems that support the sales process of the company. Recently we had an issue in Production that left us without database for two hours and affected 10,000 users approximately. How many business opportunities did the company lose during that downtime?

As we can see, errors equal money loss. Numbers will depend on the size of the organization and its revenue. The cost of downtime for a Fortune 500 company is 8,800 dollars per minute, on average (add RefME).

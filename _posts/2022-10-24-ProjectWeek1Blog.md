---
title: Project Week One Blog
toc: true
comments: true
layout: post
description: Blogging about our experience with creating our Stock API
permalink: /finalproject/weekone
image: /images/Our Wire Frame.png
categories: [week 9]
---

## Our Successes
- We were able to get the Jokes API working on both our backend and frontend
- We successfully created our stock API and got it to communicate with our frontend
- when we type /ap/stocks onto our domain, a list of all our merchendise items appear
- we were able to test/debug and find a solution to a module not found (created Python Path)

## Our Issues 
- as stated above, when we tried testing locally our stock_api was not found, so we googled the issue and figured out a way to use PYTHONPATH to solve the unknown module issue 
- Our frontend isn't working quite as planned: the names of the merchandise items show up as "undefined" and the -1 funtion on quantity does not perform as expected
![]({{site.baseurl}}/images/errorsinfrontend.jpg)
- syntax errors to think about: 
 - merch commisioner will want to be able to input their actual quantity of items (not randomized)
 - what happens if their quanitity goes below 0? (-1 function)
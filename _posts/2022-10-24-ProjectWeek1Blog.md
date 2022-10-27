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
 - Why is the quantity sometimes negative (does our range not work?)?


 # Project Progress
## What's new?

- reasearch new ideas and code from w3schools and put in blog
- a new page on our fastpage for our project
- a first attempt at creating a button for an email draft to pop up on user's screen

## The Plan

- Have a page on our team fastpage that acts as our merchandise website 
- Use parallax scrolling to have a background image of the Del Norte logo
- have text inbetween images each box saying:
    - a button for an email prompt 
    - text linking to stock API
    - an html table that shows customer info 

## Next Steps

- fix API frontend (quantity can't reach below zero, quantity subtratction working, ID defined)
- fix project page (email button, images, adding the other text)

![]({{site.baseurl}}/images/emailbutton.png)

    - start over with something more simple
        - html button first
        - add javascript
        - add popup modal (that contains email text)
        - once these work add background image with parallax scrolling
        - create HTML table with customer info
        - Once this works try and add user input into API and customer info table
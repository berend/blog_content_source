Title: Beautiful Soap - Next step after Beginner Tutorial
Date: 2013-12-16
Category: blog
Tags: beautiful_soap, web crawling
Author: berend
Summary: Things you want to do after the Getting started tutorial from beautiful soap website


** Overview **

For a small personal project I needed to get data from some websites. Easy with python, there are libs for that. I choose beautiful soap, because I always wanted to test some web crawling libs. I have never used bs before, so this is my unfiltered experience from start on.

**Installing and first setup**

Frist you have to choose between beautiful soap Version 3 or 4. I choose 4, because newer is better, right? Next step was setting up a virtualenv with bs4. I started with the tutorial, everything works, easy, simple to read, done.

The next steps were a bit harder. Thats why I decided to write a blog post about it. The data I had to scrape were so nicely formatted like the data from the example. In my experience most of the websites have ugly code. And by ugly I mean ugly for the human and machine. Deep nested <div> and <span> tags, in <table>s with some additional <p> tags.

I choose an example: The website of the Developer Conference here in Hamburg. Lets say, we need all the data for talk:

* title
* speaker
* small description
* tags/track
* time
* room

and speaker:

* name
* bio/ small description
* website/email


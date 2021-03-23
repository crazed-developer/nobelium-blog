---
title: "Content Management System"
date: 2021-03-19T18:38:09+01:00
draft: true
---

Managing content on a website may sound simple, but in actuallity it's a complex task. Creating your own Content Management System (CMS) can sometimes be tempting. And before you know it, it becomes stale, and nothing or very little development is being done on it. Because it ends up fullfilling the absolute minimum requirements needed to get the job done. This is not because you are not a compenent programmer, but because most likely you are **not** in the business of writing CMS systems. You need to manage content because you have a business.

At this stage you are busy with other tasks on the website, business, ERP, or general IT infrastructure. Bacause as said you are not in the business of producing a CMS. While the people using the CMS on a daily basis, they kind of struggle. And probably don't have much functionality available to **serve the business** the website was first intended to. When bugs are uncovered you struggle to keep up. And feature requests are being ignored. 

While this is going on, open source CMS systems are shooting out new versions, created by large teams of developers. with bug fixes, and new features. Which you as a sole developer will never be able to keep up with. And you gotta ask your self if you are doing the right thing, not just for the business you are trying to serve. But also for your self, are you putting yourself in a position where you are slowly loosing agility to do the important stuff.

This post will not give a definitive answer as to what you should do, but it will show my journey. And how I've been opening up to doing things a little different. So what is my journey that brought me to explore alternatives.

When I started doing web development, my first generated webpage was with a cgi written in Delphi (Pascal). I don't even remember which server i ran that cgi on. It's all in the past, and cgi is not even concidered any more by most people. Very early there after I got my feet wet with Microsoft ASP, for a little bit. I felt like this was pretty nice. But as they came out with the .net framework and C# it were obvious to me that ASP was instantly obsolete. I started with .net in the beta stage. And was enjoying webforms, and tried out the later MVC framework too. It was nice!

However I was slowly starting to concider open source more and more, and wanted my platform to be Linux. So I started looking into getting a Linux laptop computer that I could enjoy. Not much success there, so ended up with a MacBook instead. Pretty much the same UNIX experience. Makes me happy with having Mac as a hands on system, and Linux on the backend. Suddenly I found myself on a platform where to me Java would be the obvious choice for a switch. So since that day I've really been enjoying the Java experience. It's my go to language for anything i have to do, small utilities, web etc.

So whats my approach, well to build anything of course I need:
- An application server
  - My go to has been Payara
  - But has been moving to Wildfly.
- A database
  - Mysql is always my choice.
- I typically used JSF as an application framework.
  - I could relatively easy template out pages, pull in data from the database. 
  - Do internationalization, with multiple languages, and formatting of numbers and dates.
  - Facelets (the server side templating) do feel quite stiff
    - If your markup does not strictly conform to XHTML, then it's rejected.
    - Increasingly this was grinding my gears, as I like libraies like Alpine.js, where you put custom properties on your markup. And get functionality without having to write javascript. Facelets reject this, but provide an escape valve where using facelet markup you can add all the properties you wish. But it feels like i'm getting isolated from the basic web platform this way.
- The Jakarta MVC framework is very promising, and I've been using this for a while. Very flexible you can easily select your prefered templating language.
  - Tried Thymeleaf, I like the language. But quickly becomes quite complex.
  - Currently I lean towards  mustache templating, which is restrictive but very simple to understand. And keeps complexity in the view to a minimum.
  - The MVC framework feels much leaner, and closer to the web standard to work with.

  So how to create and manage your content? 
  
  You may start out by just adding html pages to your project, but then you have to redeploy your application to make changes to the content, this feels heavy. And is very static. 
  
  You can also create an object model to represent your data. And persist it using your favorite ORM framework. This is more dynamic, but also more rigid. It is definatly a good way of storing some kinds of data, that fits good with the object model.

  You can also make a system that stores your html pages either in a database, or on the filesystem. And then serve it through your MVC framework, or what else you are using. You can incororate short codes, that makes you able to also serve dynamic content on these pages too. And create a sofisticated management system for the different pages, make it able to handle multiple languages etc. 
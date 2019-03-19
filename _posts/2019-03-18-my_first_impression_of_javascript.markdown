---
layout: post
title:      "My first impression of JavaScript"
date:       2019-03-19 02:05:20 +0000
permalink:  my_first_impression_of_javascript
---


Finishing my Rails with JavaScript Portfolio Project means that it's time to reflect on my introduction to JavaScript. 

**The project **
The initial Rails project had more than ten views involved in creating, viewing and editing wines and wine ratings to meet the Rails project requirements. 

With the JS addition, I was able to pare that down to three views. I render a users list of wines (a user has many wines through ratings) on the user show page. On the Wine index page, I have a list of wines that, when clicked, show the wine details (wines show view) and the wines list of ratings (wine ratings index). In the wine details, I have a link to a modal form to create a new rating. All of these are called or submitted dynamically through jquery. It's a much quicker and more efficient app now. 

**My first impressions of JavaScript**
I went into the first JavaScript lessons excited to learn another language. Ruby and Rails had been so much fun to learn, so I was excited to dig into JavaScript and expand my programming experience, but I quickly learned how much Ruby's syntactic sugar had spoiled me.

My first misstep was going through each lesson and picking out the similarities between JS and Ruby. Finding the similarities gave me a false sense of security that I would be able to grasp the JS core concepts as quickly as I was able to understand Ruby. And with this false sense of security, I rushed through the core concepts of the language way too fast. 

So my first piece of advice to someone looking to get started with JS after learning Ruby is to slow down. Not every concept will click right away, and that's fine, but if you get to the end of a section and think that everything you just read was in ancient Mayan, it might be a good idea to read over them again or look at some of the MDN documentation examples. 

My second piece of advice is to stop searching for similarities in syntax and behavior because these are very different languages. Though bits of them may seem similar, looking for those similarities made it harder to break out of the ruby mindset (`this` and `self` are not interchangeable).

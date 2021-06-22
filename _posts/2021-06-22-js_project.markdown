---
layout: post
title:      "JS Project"
date:       2021-06-22 15:24:50 -0400
permalink:  js_project
---




It’s time for my second to last project to come to an end. For my project I did a super simplified app entitled "Car Favorites". The app allows a user to create a car of their desire, select it with a category, and then create that car. The app also allows the user to delete any of the previous entries. Because of the apps simplicity, it only has one user and does not have a login for separate ones. 

I chose this topic because I have always had an interest in cars since I was a young child. It made perfect sense to do something about one of my interests because it wouldn’t feel like working at all. 

I have to admit that I was not originally a fan of rails API with a JS front-end. I have always thought that Ruby on Rails makes the most sense logically and is really easy to use. I enjoyed the fact that this got me out of my comfort zone and pushed me to learn things that might not be easy at first. 

In the app the delete button had me caught up because I was encountering an error. This error took me many hours of research and debugging. I finally sought out help with open office hours and in a matter of minutes my problem was solved! Every time the user would click on the div that they wanted to delete, a 404 error would pop up. The problem was that the target was only supposed to be activated when the user clicked on the delete button. It was solved with a conditional prior to the fetch/delete in the DOM. The conditional basically further specified the eventlistener to only activate if the button was pressed, instead of the entire div.

I have been speaking with a friend who knows all about React/Redux and I am super exited to see the true power of JS!

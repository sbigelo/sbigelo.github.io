---
layout: post
title:      "Bills Tracker"
date:       2021-10-06 21:08:55 +0000
permalink:  bills_tracker
---



For my final cumulative project at Flatiron, I decided to make an application that keeps track of your bills. It allows for a bill to be created and a bill payer can be added to that bill. It is useful if you have many people in one household and need a better way to organize who is paying what, with a history of it all. 

I chose to do this because it is a simple concept that can still showcase all that I have learned. Regardless of the simplicity, I still ran into a number of obstacles. My first obstacle was displaying the Rails API properly. My main page for that was meant to have the bills and each bill paying member attached to them. It took many hours of tinkering, but finally with the help of office hours, I figured it out. The simple fix was in the Bills Controller backend. I was simply rendering JSON of all of the bills. It was solved by adding in ", include: ['users']" to the end of "@bills = Bill.all       
render json: @bills". It displayed the users in the hash. 

My second snag was in the editing of the bills. The edit form was not displaying the previous state as a placeholder. It was addressed by adding in the props that were sent down from the Bills.js file. These props were put in the starting state so that when it loaded the page, the form was filled out with the current state. 

A third issue I ran into was with rendering the bill editing page properly. I was attempting to pass props down from Bills.js to the BillEdit.js page. It kept giving me the error "TypeError: Cannot read property 'company_name' of undefined". I received help again for this issue and it ended up being a simple fix of adding "bill &&" before the rendering of BillEdit. 

Overall, this has been a great experience of learning and problem solving. I am very pleased to say that I am finally enjoying what I am doing. I was previously a beverage salesman throughout the US, but sure glad I made the leap into this world of coding!



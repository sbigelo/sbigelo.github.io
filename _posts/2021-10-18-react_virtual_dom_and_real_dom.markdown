---
layout: post
title:      "React Virtual DOM and Real DOM"
date:       2021-10-18 18:11:47 -0400
permalink:  react_virtual_dom_and_real_dom
---


Like many, when I first heard about the real DOM, it made sense because it’s something you can see happen on screen. I learned later that the React virtual DOM is an amazing feature and is way more cost efficient. It is hard to imagine something that you are not able to physically see, but I will do my best to explain the details and differences between the two. 

As you may know, real DOM manipulation is a huge part of what makes up the modern interactive web.  It comes with some negative aspects in comparison to the virtual DOM. A lot of JS frameworks are stuck with the updating the DOM more than needs to be. This can lead to issues of performance and slower loading times. The last thing a company wants is for a customer to get frustrated with their slow-loading website. 

One example, let’s say that we have a list of 100 people. If we were to changed one persons name, the real DOM would have to rebuild the whole list over again. Only one name was changed, yet it had to go through the entire process of rebuilding it all. 

Over the years, websites became more complex and required a lot more DOM manipulation. The big number of manipulations led to having slower load times and needed to be a proper solution to speed things up. Reacts' Virtual DOM comes about with a great solution. 

## Virtual DOM
In React, there is both a DOM object and a virtual DOM object. The virtual DOM object is a representation of the DOM object. It is never is displayed onto screen, thus making it light weight. You might be able to think of the virtual DOM as more of thoughts in your head and the real DOM as words that you say out loud. It is quicker and easier to think of something rather than to be able to say all of it out loud. 

## What makes it useful?
Every time a JSX element is rendered, every virtual DOM object is then updated. It doesn’t sound to be the best method, but is a lot less costly because the virtual DOM can be updated quickly. 

Once the virtual DOM is updated, React compares the virtual DOM with a virtual DOM snapshot that was taken right before the update. React is able to figure out the differences between each and determine which virtual DOM objects have changed. This is known as "diffing". 

Now that React knows what the changes were, it will *only* update the changed objects. It does this by displaying them onto the real DOM. In our previous example with the list of people, only that one person object would be changed. The whole list of people would not have to be rebuilt. It basically leaves the rest of the people on the list untouched. This is a great way of avoiding constant rebuilding of entire websites. 


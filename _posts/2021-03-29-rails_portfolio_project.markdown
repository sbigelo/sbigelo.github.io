---
layout: post
title:      "Rails Portfolio Project"
date:       2021-03-29 16:12:02 -0400
permalink:  rails_portfolio_project
---


I am nearing the tail end of my third portfolio project and things are starting to click. I first started this project worrying that I did not retain much of what I had previously learned. This turned out to be completely wrong. I felt like a puppy trying to navigate around and figure out a starting point. This all changed when I was able to follow along with a great starting video provided. It slowly broke down the starting steps and got me to a point of comfortability. This made me realize that sometimes you need to take a deep breath, step back, and take things one step at a time. I learned a lot in this, but a few things stuck out the most to me.

One of those was the class level ActiveRecord scope methods. We were previously taught about the basics of them, but never directly taught how they worked or were implemented. I took the positive route on this and took the time to research it thoroughly. They use SQL in its raw form without using helpers. It allows you to select specific things and display them in a particular order. You declare them as "scope :name_of_scope, -> {SQL method to grab what you want}". They then are added into methods on your controller like "Comment.created_at_order". In my scope method I defined it to list the comments, by content/title, from the first created to the last. I also learned from an instructor that you are able to use them anywhere needed throughout the application.

The second area I had struggled with was the nested routes. Again, I took it step-by-step and saw that it was a much easier process than I had once though. The first main need is to nest it properly into the routes.rb file like so:
' resources :users do 
       resources :reviews, shallow: true
  end'
	This creates routes that look something like this: '   
	reviews#index          user_reviews       GET        /users/:user_id/reviews(.:format)                                                                
  reviews#create                                          POST     /users/:user_id/reviews(.:format)                                                                 
  reviews#new       new_user_review    GET        /users/:user_id/reviews/new(.:format)  '
	As you can see, it only created three nested routes. This is because I had put in the 'shallow: true'. The first column is which view will show up in the folders, the second is the 'nickname/shorthand path', and the third is the URL that will be displayed. It also helps to write a simple message in the .erb file that display what page you are on. This allows you to link things to that page and confirm that you are in fact on or being routed to the correct page. 
	
A third and final thing I learned was about rendering partial's, but with local instance variables. Sometimes its best to not be DRY and render a partial on your view/.erb file. It can get hairy when you need to use a separate instance variable than the one that is in the partial form. The easy solution is to render partial like normal, but then include a ', locals: {object: @review}' at the end of the render partial. This allows the partial form to replace all of the instances of 'object' used in the partial form and replace them with '@review'. This made my life so much easier rather than rendering partial for each one, which would defeat the purpose of DRY. 

Overall, this has been a fun learning experience. It has changed my entire way of thinking about tackling a large project, by just slowing down and taking it piece by piece.

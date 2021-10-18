---
layout: post
title:      "Sorting and Unsorting a List With a State"
date:       2021-10-18 20:49:59 +0000
permalink:  sorting_and_unsorting_a_list_with_a_state
---


It is important to avoid mutating state whenever possible.  The best practice when displaying an array of modified data is to create a new array. This can be accomplished by many methods, but for this particular one, I am using "array.concat([])". Concat merges two or more arrays together. In the example above, I am combining the current array with a blank one. This allows for the manipulation of the data, without mutating. 

For this blog post, I am showing how to have a list of dogs' names put into ascending order after clicking a button.  Once the list is sorted, I want the next button click to put it back to the original order. The list will be alphabetized by the first letter in each name. Here is the data:
![](https://i.ibb.co/xYLDR1g/data.png)



The starter code and what it looks like on the browser: 
![](https://i.ibb.co/JC01Lw8/starting-code.png)

As you can see I simply mapped over the data to display an unordered list of the dogs names (as listed in the order of the data) and displayed them onto the browser. We run into an issue because each child in a list should have a unique "key" prop. To fix this we simply change our code to the following:
![](https://i.ibb.co/M8Tjc57/add-k.png)


The first step is to add a button tag after line 11 with the text of "Re-order". The second step is to create a state to encompass the dog list. We add in the state a key of "dogList" and its value of the dogs array from data. We now can change the "dogs.map(..." to "this.state.dogList.map(...". We next need a method to handle the onClick. Updated code: 

![](https://i.ibb.co/Ykb6ghx/Screen-Shot-2021-10-18-at-2-18-50-PM.png)



We now need a method to determine which state it is in, then have it update state accordingly. This is accomplished by adding a second state of "sortedDogs" that has a boolean value of true or false. It allows for a conditional to check if it is true or false (that it has been sorted or not). We put an if conditional to check if the "this.state.sortedDogs" is true. If it is true, we set the state to the original order and put "sortedDogs" set to false. 

![](https://i.ibb.co/9wqgymJ/next.png)



The final few steps we need to use the concat example from the beginning of this blog post. We first combine an empty array to the dogs array. Next, we need to be able to sort them alphabetically by using the ".sort" method. We are able to use this because we are not mutating the array directly, but instead using the newly combined one.  Luckily for us, there is a simple way of sorting strings into alphabetical order. It is called "localeCompare" as seen below: 

![](https://i.ibb.co/bXy5JCt/Screen-Shot-2021-10-18-at-2-43-55-PM.png)


What it basically does is to compare the selected string "a.name" to "b.name". It returns a number indicating whether a reference string comes before, after, or the same (-1 for before, 1 for after, and 0 for the same). We did it! If you click the button the order that is displayed will go from its original order to the sorted one as much as you would like. 


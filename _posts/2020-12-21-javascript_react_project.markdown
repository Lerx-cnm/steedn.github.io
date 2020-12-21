---
layout: post
title:      "JavaScript: React Project"
date:       2020-12-21 21:53:28 +0000
permalink:  javascript_react_project
---


My React project was one of a kind. React was alot harder on me then all the other projects combined. From the moment I started it I was confounded and confused the entire time, the major three things were these:

1. props & state(especially between components)
2. mapStateToProps and use
3. Redux flow (action => reducer => updated state)

My first problem was figuring out what to do with props and states, and how to use them. I knew what they were, I knew state was a obj that stored info for that component, and I knew props were a way of handing data down to a child component from a parent component. However, I didnt fully understand how to truly utilize these features, I didnt use state to hold important info, and I wasnt using props either. After some studying I realized how important these were and I was able to utilize them into my components. 

Secondly, I didnt understand mapStateToProps at all. It took me alot of studying and exprimenting to figure out exactly what it was doing, and doign So I was able to use it appropiately in my components, especially matched with a `fetch()` request. I was able to receive a fetch request parsed(`.json()`) and then I was able to mapStateToProps which let me use the new state, or return in my props. 

Lastly, and possibly one of the biggest problems for me to learn about was the flow of Redux. I had to turn to more knowleadgeble people in this, for help. they helped me understand why its important to have that structure in an application especially in a big application where we need more efficient code and structuring. 

     action ---> reducer ---> updated state
		 
this is the flow of redux, and very important.

##### Action: 

This is a part of the flow where our code is doing 'something with something' as I like to put it. an example would be to add_counter with a certain object. this allowed us to create actions, and decide what to do with data

##### Reducer: 

The reducer is apart of the flow that takes our action and does what we want with it, its the actuall machine. the reducer usually is a `switch case` statement that has `identifiers` or `actions` so that it can appropiatley manipulate the data.

##### Updated State: 

after all of this, finally our state and info is now updated and different, from here we can access it to display or use. 

All in all this redux flow is very good as it introduces a more streamlined way of dealing with changes in state and data, this helps us write more efficient and quick code. 

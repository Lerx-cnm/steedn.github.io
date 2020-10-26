---
layout: post
title:      "RAILS PROJECT"
date:       2020-10-26 09:48:40 +0000
permalink:  rails_project
---


From the start I was a little unsure of my abilities, I did not even know what I wanted to do for my rails project. Some of the things I was concered about were my knowledge on the following items:

  1. Nested routes
  2. Figuring out how to fashion the correct relationships between models.


With those things in mind I could expand a bit more on what troubles I went through programming my code. I had decided on a user based video game review application. Users could create an account, and post reviews based on a video game from a seeded database (of videogames). When I started programming, I realized that Rails would prove to be difficult, I personally find concepts easier to grasp when explained in detail, however with Rails there was quite a bit of 'Rails Magic' involved. Compared to my Sinatra project, I was going to have to study alot. 

My first step in creating my application was to plan out my models and relationships, as stated above this is where I knew that I would struggle, and that I did. Originally I had planned on using a fourth join-table to help me, but I soon realised that this would become just a cluttered mess, and very unorganized. So from there I had to figure out how to join my User model, to my Game model. After re-studying some material I figured I could make a Review model that could act as my join table in my application. 

Now, I was presented with an entirely new problem, how was I going to control both reviews and games being submitted by users, that also presented an entirely new problem in relationships, I was thinking that if Users could post both games and reviews my model might look like this:

```
class Game < ApplicationRecord
has_many :reviews
has_many :users, through: :reviews
belongs_to :user
```

Obviously, that doesnt make alot of sense and overall doesnt look very good, this is where i began to doubt my ability and my project as a whole, I could not quit seem to jump this hurdle until I discussed my ideas with multiple cohort mates. It wasn't until I was able to rebound ideas off of them, with some possible suggested alterations that I was able to come to the idea of seeding my database with set games that did not belong to a user. This would rid my problem. So from there I created a full `seeds.rb` file with the correct data, and seeded my database. After I solved this problem, my confidence rose and I was able to keep moving.

As I began to fill my application with controllers, controller actions, and views it was significantly easier for me to jump over hurdles and problems until I got to the point where I was trying to authorize users on what they could, and could not edit. I tried many different solutions, and it was also at this point where I realised the importance of validations and other methods that I had at my disposal. With those I was able to create a solution that was secure and also a bit more aesthetically pleasing. 

After I had finished all of that, was the time right before writing this where I checked over the application, by myself, to try and DRY(Dont Repeat Yourself) up my application, as well as clean up any code and see if i was missing anything, or perhaps having some sort of redundancy. and then I made revisions to code, as well as a readme to once again try to make it an overall better experience for the user. 

I do have to say that overall my favourite part of the project, and the part that made me most proud of it, is my edit function, which though nothing particularly special, was as follows

In my index page for reviews,

```
<% @reviews.each do |e| %>
  <h2><%= e.title %></h2>
  <p><%= e.body %></p>
  <% if session[:user_id] == e.user_id %>
  <%= link_to "Edit", edit_game_review_path(e.game_id, e.id) %>
  <% end %>
  <% end %>
```

This particular solution resulted in a check to see if current user mathed the current iteration of a review, and if they matched, then a `edit` button would appear underneath, so that the `edit` button only appeared on your particular reviews. Now obviously, this alone could not deter a very 'troublesome' user. So in my `ReviewsController` I added the following code to help prevent tampering from our more spirited users. 

```
    def edit
      @review = Review.find_by(id: params[:id])
      if current_user.id != @review.user_id
        redirect_to game_reviews_path
      end
    end
```


Overall the whole coding experience was very fun, and mind opening. It helped me learn alot about my self, cohort mates, and Rails. As of now, I definitely look forward to JS, and any other projects and assignments that await. 

-Nathan Steed

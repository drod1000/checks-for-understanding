## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
rails new app_name
2. What do Models generally inherit from in rails?
ActiveRecord::Base
3. What do Controllers generally inherit from in a rails project?
ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
resources :horses, only: [:show]
5. What rake task is useful when looking at routes, and what information does it give you?
rake routes, it gives you the path, the verb, and the method
6. What is an example of a route helper? When would you use them?
horse_path(horse), we usually use these whenever we're using links in our views instead of typing everything
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
path only returns the path relative to our domain while the url returns the entire thing(/horse instead of localhost:3000/horse)
8. What are strong params and why are the necessary?
strong params are when we check the parameters that the user gives us before saving them to the database. they are necessary if we want to protect our applications.
9. What role does `form_for` play in helping us create our forms?
form_for makes it easier for us to create forms by making a few assumptions
10. How does `form_for` know where to submit the user's input?
not too sure about this one but my guess is that it determines where it should go based on what is in @horse(if not in database it'll send to create, otherwise to update)
11. Create a form using a `form_for` helper to create a new `Horse`.
<%= form_for @horse do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  
  <%= f.submit %>
<% end %>
12. Why do we want to validate our models?
so that we only save valid data to our database(no dupes, or missing fields, etc)

## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
ANSWER: rails new project_name

2. What do Models generally inherit from in rails?
ANSWER: ActiveRecord::Base

3. What do Controllers generally inherit from in a rails project?
ANSWER: ApplicationRecord

4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
ANSWER: I would indicate in routes.rb the following: resources :horses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?
ANSWER: rake routes

6. What is an example of a route helper? When would you use them?
ANSWER: Some examples of route helpers are: horses_path to see all the horses and horse_path(horse) to see a specific horse

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
ANSWER: I looked it up and found that _path only returns the url relative to your domain (like '/')while _url
returns the URL address (http://....).

8. What are strong params and why are the necessary?
ANSWER: Strong parameters are an extra layer of protection to your code to prevent that people accidentally update sensistive model attributes.

9. What role does `form_for` play in helping us create our forms?
ANSWER: form_for has many built-in features that makes us easier to make a form and add that information in our database so it goes to the right place (each field is normally an attribute of the object that is being created/updated)

10. How does `form_for` know where to submit the user's input?
ANSWER: Because of the argument/s that we pass after the words form_for plus that the name of the fields match exactly to the attributes that this object has.

11. Create a form using a `form_for` helper to create a new `Horse`. 
ANSWER: <%= form_for @horse do |f| %>
<%= f.label :name %>
<%= f.text_field :name %>
<%= f.submit %>

12. Why do we want to validate our models?
ANSWER: We validate our models to state what attributes are mandatory when user creates a new object. If one or more of the required fields are not filled in, the user should be rendered new or edit view as another opportunity for them to do it right.

## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
ANSWER:
GET, PUT, POST, PATCH, DELETE

2. What is Sinatra?
ANSWER:
It's a framework that understands Ruby and makes easier to build web applications. It allows us to perform different actions and display a different view for each path that we define in the controller. It uses HTTP verbs and a very simplified syntax.

4. What is MVC?
ANSWER:
Models/Viewer/Controller is a convention to structure your code when building a web application. The Models is reponsible for creating the Ruby objects (horse.rb), the Viewer takes care of the views that are rendered to the user for each path and the Controller handles the routes and the actions for each one.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
ANSWER:
We follow conventions when writing code in general for readability, easy maintenance and keep improving it among all the members of the community. 

6. What types of variables are accessible in our view templates without explicitly passing them?
ANSWER:
We can access instance variables that are created in the model (horse.rb) and are declared in the view(index.erb)

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
ANSWER:
Using the <% %> so we can write Ruby inside this tag in an erb file.
  ```ruby
  get '/horses' do
    erb :index
  end
  ```
  
8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
ANSWER:
I would do:
``` ruby
  get '/horses' do
  @horse = "Mr. Ed"
    erb :index
  end
  ```
And then in the index.erb, I'd put <%= @horse %>

9. What's the purpose of ERB?
ANSWER:
Be able to design the view wieh html but also using Ruby to pass certain values that we want to display

10. Why do I need a development AND test database?
ANSWER: I guess that this way if something goes wrong or we do modifications to the database to verify some functionality during the testing the original database is not affected and stays the same.
11. What's responsive design?
ANSWER:
It's a design that adapts to all kinds of screens (laptop, tablet, mobile,...) without losing the style nor the content.
12. What is CRUD and why is it important?
ANSWER:
CRUD stands for Create, Read, Update, Delete. It's important because these are the main actions that we always want to be able to do when working with data.
13. What does HTTP stand for? 
ANSWER:
Hypertext Transfer Protocol
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
ANSWER:
The two ways are using <%= %> that executes the code in Ruby and displays the result and <% %> that only executes but doesn't display the result.
15. What's an ORM?
ANSWER:
ORM stands for Object Relationship Mapper and it's a tool that we use to be able to talk to the database using Ruby or other object-oriented languages. ActiveRecord is an example of ORM.
16. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ANSWER: ActiveRecord
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
ANSWER:
get '/' do => to define what's rendered when user goes to homepage
get '/restaurants => for user to see all restaurants
get '/restaurants/new => for user to add a new restaurant to the database(create a new restaurant, normally with a form)
post '/restaurants => to save the new restaurant to the database
get '/restaurants/:id => for user to see a specific restaurant
get '/restaurants/:id/edit => for user to be able to edit the information of a specific restaurant
put '/restaurants/:id => to update the new info of a restaurant and redirect to restaurants/:id view
18. What's a migration? 
ANSWER:
A migration is the way that you add or changing data of the database. In ActiveRecord we need to create a new migration for every change that we do in the database, the current status of the database is displayed in schema.rb file.
19. When you create a migration, does it automatically modify your database?
ANSWER:
No. In order to modify the database you need to modify the migration file just generated, edit it with the modifications and run db:migrate in the terminal so the changes have been applied in the database. 
20. How does a model relate to a database?
ANSWER:
The model will create new entries of the database(row) and defines the attributes(columns).
21. What's the difference between agile workflow and waterfall method?
ANSWER:
In the waterfall method, the project is defined in detail from the beginning and the team sticks to the plan while building code. The agile method is more flexible and it's when the team creates minimum code for feedback and adapts their process/product to the necessary changes that come from it.
22. What is the difference between `#new` and `#create`?
ANSWER:
When we do horse = Horse.new it's necessary to do horse.save in order to add this data to the database. With Horse.create it automatically saves it in the database for us.

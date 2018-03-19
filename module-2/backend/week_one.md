## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
GET - Retrieve info
POST - Send info to server, generally to create, store, or transfer data
DELETE - Trigger deletion of data
PUT - Update all data
PATCH - Update single data entry

2. What is Sinatra?
It is a ruby web framework to handle routing and view rendering
4. What is MVC?
Model - View - Controller

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
For ease of readability and understanding, especially for people looking at the code for the first time

6. What types of variables are accessible in our view templates without explicitly passing them?
Instance variables

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    erb :index
  end
  ```

add `@count = 1` to the do block

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
add `{locals: {name: 'Mr. Ed'}}` to the erb line

9. What's the purpose of ERB?
Store our views, as well as have dynamic content added by using ruby expressions

10. Why do I need a development AND test database?
Development databases can hold huge amounts of data, even when you're just testing your site. Test databases speed up the testing process by using funcitonally complete, but small databases created and destroyed during the tests to ensure that the input is always the same even with a clean database.

11. What is CRUD and why is it important?
Create, Read, Update, Delete. It is important for our models to be CRUD (sometimes RUD) so that we have complete funcitonality over the data, and don't end up with data being "stuck" in the database.

12. What does HTTP stand for?
Hypertext Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
`<% [code] %>` - Evaluate the code
`<%= [code] %>` - Evaluate the code, and print the raw output to the view

14. What's an ORM?
Object-relational map

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ActiveRecord

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
* GET /restaurants - List all restaurants
* GET /restaurants/:id - Get specific restaurant
* GET /restaurants/new - Add restaurant form
* POST /restaurant/new - Add new restaurant to database
* GET /restaurants/edit/:id - Edit restaurant
* PATCH /restaurants/edit/:id - Update restaurant
* DELETE /restaurants/delete/:id - Remove restaurant from database

17. What's a migration?
A definition for the way that the database/table should be set up. Not schema, but the rules for generating the schema.

18. When you create a migration, does it automatically modify your database?
No, it must be run.

19. How does a model relate to a database?
A model represents a single object or row in the database

20. What is the difference between `#new` and `#create`?
`#new` is just like a standard ruby class. Creates a new instance of the model/object. `#create` creates a new instance of the model, and then adds it to the database with `#save`

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
```
CSV.foreach('films.csv', headers: true, header_converters: :symbol) do |film|
  Film.create(film)
end
```

22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores']
}
```
How would I add 'granola bar' to things you should have when hiking?
```
activities[:hiking][:supplies].push('granola bar');
```

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
* Encapsulation - Only let classes/objects know enough to complete their task
* Single responsibility principle - Each method should perform one and only one task
* Open/Closed - Classes should be designed such that they require as little (preferably no) modification as possible to add new functionality.
*

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel confident about the content presented this week

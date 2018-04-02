## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
`rails new ProjectName . . . `

2. What do Models generally inherit from in rails?
`ApplicationRecord`

3. What do Controllers generally inherit from in a rails project?
`ApplicationController`

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
`resources :horses. only: :show`

5. What rake task is useful when looking at routes, and what information does it give you?
`rails routes` / `rake routes`
Tells you the name, prefix, method, and associated controller method. In addition to URL parameters

6. What is an example of a route helper? When would you use them?
`user_path` - Dynamically generate paths, so you don't have to rememebr or interpolate them

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
`_url` gives you the absolute path, but `_path` is relative

8. What are strong params and why are they necessary?
Strong params allow you to filter out unwanted form data, to mitigate injection attacks.

9. What role does `form_for` play in helping us create our forms?
`form_for` allows us to generate a form set up for a specific model on the fly. Rails figures out the method based on context

10. How does `form_for` know where to submit the user's input?
Rails magic. Depends on what route it was called on (new does POST to /whatever, update does PUT/PATCH to /whatever)

11. Create a form using a `form_for` helper to create a new `Horse`.
```ruby
<%= form_for @horse do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  . . .\
  <%= f.submit %>
<% end %>
```

12. Why do we want to validate our models?
Models should be validated so that we aren't storing nil data in the SQL server

13. What are the steps of the DNS lookup?
  * Lookup in tables on computer
  * If not, go to router
  * If not, go to ISP node
  * If not, go to node further up the tree
  * If not, go to DNS server


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
`prance`

15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?
To return true do `furnitue[:purchased]`, to return 3 do `furniture[:table][:height]`

16. What is inheritance?
Inheritance is the ability of another class to use methods and variables from another parent class, extending the functionality.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel confident about the content presented this week

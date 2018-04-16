### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
  - Add a `flash[:class] = 'Whatever'` before the page is rendered
  - Add a code block like so in the application.html.erb
    - ```ruby
      flash.each do |class, message|
        <%= content_tag :div, message, class: class %>
      end
      ```

2. Where is cart information/temporary information usually stored?
  - In the session

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
  - Extra data to store, and unless the user expects to see their cart attached to their account across multiple days or devices, there's no real need to use the computing time to make database calls.

4. What is the purpose of the asset pipeline?
  - Allow for precompilation of files, and force caching of files.

5. Why do we precompile our assets?
  - So we can write in higher level languages like Coffeescript, Typescript, SASS, LESS, etc.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
# Adds all the stylesheets from the application.css manifest file

<%= javascript_include_tag "application" %>
# Adds all the javascript from the application.js manifest file

<%= image_tag "rails.png" %>
# Adds an image tag with the properly formatted URL for the asset
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
  - Setup, dependencies, instructors for basic use
  - Solid readmes make the project easy to understand, especially if a developer wants to implement/build it themselves. It gives them a starting point that is simpler than pure documentation.

8. What are the top four accessibility issues that we as developers should be aware of?
  - Alt text for images
  - Readability
  - Simplistic design
  -

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
   - Callback hooks
   - These are generally found in the model

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```
  - `scope :is_active, where(active: true)`

11. What is the difference between a scope and a class method?
  - Effectively the same, just different syntax


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
    - `hash[:cart]["48"] = 4`
  12b. How would you increase the quantity of item 29?  
    - `hash[:cart]["29"] += 1`
  12c. How would you find out how many items your user is thinking about purchasing?   
    - `hash[:cart].values.sum`

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  
  - Polymorphism is the ability for one class to relate to another class, and take on its attributes or methods. It relates to duck-typing in that since the same methods exist, you can treat the object at least partially as though it is that other class.
  - ActiveRecord collections function almost exactly like arrays, with some added bonuses
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
  - `string.gsub(/[^0-9\s]/, '').gsub(/\s/, '.')`


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week

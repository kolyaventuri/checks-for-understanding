## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
  * A cookie is a small piece of data for a specific site stored on the users computer (client

2. What’s the difference between a session and a cookie?
  * Cookies are saved on the client, whereas sessions are saved on the server

3. What’s a flash and when do you want to use flashes?
  * A flash is a notification on a page, which typically appears as a confirmation of an action, a warning, or an error to display to the end user

4. Why do people say “HTTP is stateless”?
  * HTTP has no way of knowing that one request followed the next and that it was the same person. That logic has to be handled client side to give the requests a state.

5. What’s authentication? Explain.
* Authentication is the action of determining if an end user has an account on the server.

6. What’s the difference between authentication and authorization?
    * Authentication is "who are you" and authorization is "what can you access"

7. What’s a before filter?
  * A before filter allows us to run a ruby method before each router/controller endpoint, allowing us to filter out users that do not have authorization to a specific page or subset of pages.

8. How do we keep track of a user once they’ve logged in?
  * we keep track of users by setting a session ID on the client side, and storing that same session id in the users cookies. That session ID is sent back to the server each time for lookup.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
  * Namespacing allows us to have endpoints under a specific path, such as `/admin/users/new` rather than just `/users/new` and handle them differently
  * Nesting allows us to have endpoints that require more than one model to function. Such as a users posts might be `/users/:user_id/post/:id`
  * We would want to use namespacing to scope pages for either specificity or authorization, and nesting when we need two models to interact

10. At a high level, what tools can you use to implement authorization? How would you use them?
  * We can use encryption tools to securely store users passwords on the server when they sign up, such that they are not stored in plain text
  * We can use Rails built in `session` and `cookie` objects to determine which user is accessing the site, to look up their `User` model, and determine privilages

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
  * An enum is an easy way to create simple objects to reference by name. For instance, `role.ADMIN` or `role.DEFAULT` rather than simple integers like `1` or `0`. Enums correspond to integer datatypes, so if using a database, you must have an integer type of some kind for that field. You declare enums in the model

12. What are some strategies you can use to keep your views DRY?
  * Keep logic (aside from **basic** if/else conditions) in the controllers or models
  * Don't call model code from views, instead pass in as an object from the controller


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  

```ruby
list = hash.map { |item| item.holiday.name }
puts list.sort
```

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
```ruby
  cleaned = incoming.gsub(/[^0-9\.]/,'').to_i
```

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few
  * For the regex expression

Choose One:
* I feel confident about the content presented this week

## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  * Interact with your database at a high level, regardless of the type of underlying relational database. Very simple to use CRUD functionality on your models.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
* Create
* Update
* Find
* Destroy
* etc. all access because it inherits from ActiveRecord

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

```ruby
team = Team.find(4)
owner = Owner.find(team.owner_id)
```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

```ruby
owner = Team.find(4).owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

![schema layout](https://i.imgur.com/937qtW1.png)

6. Define foreign key, primary key, and schema.
  * Foreign key - A reference to a key in another table
  * Primary key - The primary indexed key of a table
  * Schema - The structure of a databse or table
7. Describe the relationship between a foreign key on one table and a primary key on another table.
  * Having a foregin key on one table allows reference to another table by pulling that key and performing a lookup on the other table
8. What are the parts of an HTTP response?
  * Header (contains response codes and various header options such as content type)
  * Body (string containing all of the response data, such as HTML or JSON)


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  * Model#create! - Create with hard failure if there is an error
  * Model#find_by - Find all records with a specific key
  * Model#save - Save any changes to the record
  * Model#joins - Join the data of two tables
  * Model#group - Group the data by a specific attribute
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
  * Drop - Destroy the database
  * Migrate - Set up the database as per migrations
  * Seed - Runs db/seed.rb to fill database
3. What two columns does `t.timestamps null: false` create in our database?
  * Adds created_on and updated_on columns on the data
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
  * Students have one teacher
  * Teachers have many students
  * Arguably, in some cases, you could design a many to many where both students and teachers have many of the other. Depends on the school.
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
  * ![schema layout](https://i.imgur.com/937qtW1.png)
  * ![schema layout](https://i.imgur.com/0baGptg.png)
6. Give an example of when you might want to store information besides ids on a join table.
  * Shared data between tables
7. Describe and diagram the relationship between patients and doctors.
  * Patients have one doctor
  * Doctors have many patients
  * ![doctor patients](https://i.imgur.com/wN1g4Z0.png)
8. Describe and diagram the relationship between museums and original_paintings.
  * Museums have many original paintings
  * Original paintings have one museum
  * ![museum paintings](https://i.imgur.com/i2UYp9d.png)

9. What could you see in your code that would make you think you might want to create a partial?
  * Navigation
  * Reused information (similar tables)

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week

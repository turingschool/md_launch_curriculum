## Lab Objectives
* Add to your library database, create a many-to-many relationship between Books and Authors

We are going to continue building on our Library database by adding a many-to-many relationship between books and authors. This relationship should be many-to-many because a book can have many authors and an author can write many books.

<!-- ** Instructor Note **  For this lab we again use the library lab groups of 3/4 established during the intro to databases lesson. This will let folks build off of the databases they already created.

Some students may already have a one to many relationship between books and authors, hopefully this will lead to good discussions about how it's harder to change your database structure, and thinking first is very good. Would be great to have a groups that had to drop their old author column share what they did! -->

## Practice
### Drawing Your Own Data Relationships

<!-- Students take some of the examples from earlier, determine if one-to-one, one-to-many, or many-to-many and then draw ERD to represent the relationship -->

Minimum one of each, including the many to many of books and authors. Make clear this is different than songs and artists, that's one to many, this is many to many.

Send your screenshots to a thread in slack as checkpoint before implementing the many-to-many books and authors.

<!-- Thought, we should probably introduce some sort of drawing technology for students to use early in the course, but also very ok with them using pen and paper and taking a picture. -->

### Implement Your Books and Authors Many-to-Many Relationship

When your group is happy with the outline of the database, use PgAdmin to create it!

### Stretch Goals

If you've finished, work on creating the tables for the one-to-one and one-to-many relationships you drew. 

<!-- maybe have them to add those to their default postgress db? -->

#### Exit Ticket!
Send us a screenshot of the Generated ERG from PG admin for the books and authors many to many.

Want to check the tables you created are as expected?
View ERD tool in 

<p align='center'>
  <img src='../../Images/Week2/pgadmin_makeERD.png'>
</p>
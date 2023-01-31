## Lab Objectives
* Practice writing `JOIN` queries
* Practice using `JOIN` and `WHERE` together

Let's write some more advanced queries on our Library database. You should have a one-to-many relationship between books and patrons. Each book can be checked out by one patron. And each patron can check out many books.

You probably still have your books and patrons tables, but if not here is a script to create those tables and add some sample data.

```SQL
DROP TABLE books, patrons;
-- this should be a list of the student's tables.  You should update this script with the appropriate table names if you need to help students get started with a clean version.

CREATE TABLE patrons (
	id serial PRIMARY KEY,
	FirstName varchar(50),
	LastName varchar(50),
	PhoneNumber varchar(10)
);

CREATE TABLE books (
	id serial PRIMARY KEY,
	Title varchar(255),
	Author varchar(255),
	CheckedOutBy int REFERENCES patrons
);

INSERT INTO 
  patrons ( 
    FirstName, LastName, PhoneNumber
  )
VALUES
('Zoe', 'Farrell', '1231231234'),
('Richard', 'Tillies', '1111111111' ),
('Megan', 'McMahon', '2222222222');

INSERT INTO 
  books ( 
    Title, Author, CheckedOutBy
  )
VALUES
('Winter Counts', 'David Heska Wanbli Weiden', 1),
('Atlas Of the Heart', 'Brene Brown', 1),
('Winter Counts', 'David Heska Wanbli Weiden', 2),
('Winter Counts', 'David Heska Wanbli Weiden', 3),
('A Plague of Giants', 'Kevin Hearne', 2),
('Honor', 'Thrity Umrigar', null)
```

### Joining the books and patrons data

Write a `JOIN` query to join the patrons and books data that only returns books that are currently checked out.

<details><summary>Spoiler</summary><br/>

```SQL
SELECT books.*, patrons.* FROM books JOIN patrons ON books.CheckedOutBy = patrons.id;
```

</details>

Write a `JOIN` query to join the patrons and books data that returns all books, even ones that are not checked out.

<details><summary>Spoiler</summary><br/>

```SQL
SELECT books.*, patrons.* FROM books LEFT JOIN patrons ON books.CheckedOutBy = patrons.id;
```

</details>

### Writing questions

Start by brainstorming possible queries for books and patrons that would require a `JOIN`. As a breakout room, post at least two potential queries in the slack thread.

Here are two examples to get you started:

* Who are all the patrons who have currently checked out the book 'A Plague of Giants'?

* What books does the patron with id 2 have checked out?

### Writing SQL queries with joins

Once you've posted your three queries in slack, write the query to answer the two examples above and some of the queries from slack.

I recommend changing the names of books and patrons to match the data in your database so you can better test your queries!

### Extra Challenge

If you want an extra challenge, try writing queries that combine `JOIN` with the aggregate functions we learned yesterday.

For example: 

How many books by the author 'David Heska Wanbli Weiden' does the patron with the phone number '1111111111' have checked out?

This is a tricky question, try building your query bit by bit instead of trying to write the whole thing at once!

<details><summary>Spoiler</summary><br/>

```SQL
select count(*) from books LEFT JOIN patrons ON books.CheckedOutBy = patrons.id WHERE patrons.PhoneNumber = '1111111111' AND author = 'David Heska Wanbli Weiden';
```

</details>
<!-- Instructor note, might be good to find a volunteer who can talk through their process for building this complicated query for the class. Good to see building something like this step by step -->



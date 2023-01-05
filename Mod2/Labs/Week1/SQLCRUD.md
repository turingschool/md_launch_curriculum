## Lab Objectives
* Practice using `SELECT` `UPDATE` `REMOVE` and `INSERT`

** Instructor Note ** Students are going to build upon their work from yesterday's lab.  It would be helpful if they are in the same groups, if possible.  If students need to start from a fresh database setup, you can provide them with this script (it should work if their database is called 'Library').
```SQL
DROP TABLE books, patrons;
-- this should be a list of their tables.

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
	CheckedOutBY int REFERENCES patrons
);
```


## Practice

In small groups, use PgAdmin to create, update, remove, and query some records for the Library database we created yesterday.  There are some required activities below, but feel free to experiment with your database!  If you ever feel that you need a fresh start for your database, reach out to your instructors.

### Add Books to the Library and Create Library Patrons

1. Use `INSERT` to create at least 5 patrons for your library (these can be real, or fake people).
2. Use `INSERT` to create at least 10 books in your library.  The books can be all unique, or you could have multiple copies of more popular titles!  (books can also be real, or fake)

### Check Out Books

3. Use `UPDATE` to add a patron to at least 4 of your books (indicating that the book has been checked out by that patron). Make sure that at least 2 patrons have checked out a book.

### Remove Old Books

4. Occasionally, libraries need to pull books out of circulation (perhaps someone wrote in the margins, or the book has too much wear and tear).  Use `REMOVE` to delete the 3 oldest books in the library (the three you created first).

### Query for Available and Unavailable Books

5. Use `SELECT` and `WHERE` to return the title and author of all books that are not checked out.
6. Use `SELECT` and `WHERE` to return the title and author of all books that are checked out.
7. For each patron, use `SELECT` and `WHERE` to return the title of the books each patron has checked out.

## Exit Ticket

Send a slack message to your instructors with the SELECT queries you created in the last section above.
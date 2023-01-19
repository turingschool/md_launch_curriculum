## Learning Goals

* Visualize and practice a SQL join query
* Use WHERE to filter joined queries 
* Understand the difference between an inner join and a left join

<!-- TODO: Delete this link to BE lesson before merging -->
https://docs.google.com/presentation/d/175ycpUYkQp8kmxrZrxaq-0wk63Uq0aFXL7l3cGX9O98/edit#slide=id.g11fafc7594a_0_59


## Warm Up Challenge

Let's keep practicing with our Songs and Artists tables.

<p align='center'>
  <img src='../../Images/Week3/1_to_many_db_image_5.png'>
</p>

For each of the following, what is the SQLcommand we would use to get this information:
  - Get all song titles  
  - Get the songs with a play count greater than 100
  - Get the artists that have a hometown of Minneapolis, sorted alphabetically  

  Extra challenge!
  - Get the 5 longest songs that have the word “bad” in the title and at least 100 plays

## Joining Tables

### The SQL Join Query

So far, we have looked at SQL queries that deal only with one table. But you will sometimes need to run queries based on information from more than one table. Maybe our query involves both songs and artists!

For example: 
- Find the artists with songs that have been played more than 100 times
- Find all songs where the artist name contains “Prince”

When we come up against this problem, we rely on `JOIN` queries to accomplish this goal.

A `JOIN` pulls information from multiple tables into one temporary table.  Let's see how this works.


<!-- Change this to PG admin -->
In PG Admin, let's take a look at our `songs` and `artists` tables:

```
SELECT * FROM songs;

id |      title      | length | play_count | artist_id
----+-----------------+--------+------------+-----------
 1 | And She Was     |    234 |         23 |         1
 2 | Wild Wild Life  |    456 |        894 |         1
 3 | Raspberry Beret |    340 |        434 |         2
(3 rows)
```

```
SELECT * FROM artists;

id |      name      
----+----------------
 1 | Talking Heads
 2 | Prince
 3 | Zac Brown Band
(3 rows)
```

Above, we see our songs and artists table - what happens if we `JOIN` these tables together?

```
SELECT artists.*, songs.* FROM songs JOIN artists ON artists.id = songs.artist_id;

id |     name      | id |      title      | play_count | length | artist_id
----+---------------+----+-----------------+------------+--------+-----------
 1 | Talking Heads |  1 | And She Was     |         23 |    234 |         1
 1 | Talking Heads |  2 | Wild Wild Life  |        894 |    456 |         1
 2 | Prince        |  3 | Raspberry Beret |        434 |    340 |         2
(3 rows)
```

**Turn and Talk** What did this query do? How might you describe the return value of this query?

When we run this `JOIN`, we are _joining_ the songs and artists tables together to return a table that includes all the information from _both_ tables. For each artist, we see a row for each song that they have, with the information from both the artists table and the songs table.

When creating a `JOIN` query, there are three essential parts:

  1. `SELECT` - this is what indicates which columns will be included in the resulting table
      - `SELECT * FROM songs`
  2. `JOIN` - the command to join in data from another table
      - `JOIN artists`
  3. `ON` - this tells the join _how_ to join the two tables together, or what is the relationship between the two tables (most often, primary key = foreign key)
      - `ON artists.id = songs.artist_id`
  
Looking at our joined table, what information could seem to be missing? What happened to `Zac Brown Band`?

**Turn and Talk** Why are we not seeing _all_ our artists on this joined table?

<!-- Now add another song where the artist isn't in the table. Pause for predictions, and run the join again. -->

## Types of Join Queries

When we create `JOIN` queries, there are a handful of different join types that we can declare that will affect the resulting table.  Today, we are going to cover the most common two: **Inner Join** and **Left Join**

### Inner Join
<p align='center'>
  <img src='../../Images/Week3/inner_join_venn_diagram.png'>
</p>

The default `JOIN` type in SQL is an **Inner JOIN**.  

- Default join type (This is what we've been doing so far when we use the SQL keyword `JOIN`)
- Only returns records that match the ON condition
- Only returns records from table A that have a corresponding record in table B


<p align='center'>
  <img src='../../Images/Week3/inner_join_before.png'>
</p>

<p align='center'>
  <img src='../../Images/Week3/inner_join_after.png'>
</p>

### Left Join

<p align='center'>
  <img src='../../Images/Week3/left_join_venn_diagram.png'>
</p>


The next most common `JOIN` type is a **Left Join**.  

- Will get all records from table A regardless of if they have corresponding rows in table B
- “Left” refers to the first table referenced in the query
  - FROM artists LEFT JOIN songs artists is the “LEFT” table

Example: 
```SQL
SELECT artists.id, artists.name, songs.id, songs.title 
FROM artists 
LEFT JOIN songs 
ON songs.artist_id = artists.id;

```

<p align='center'>
  <img src='../../Images/Week3/left_join_before.png'>
</p>

<p align='center'>
  <img src='../../Images/Week3/left_join_after.png'>
</p>

Now, we see 'Jerry Garcia Band' even though that artist has no songs.

## Practice

With your partner: Write a SQL query would to retrieve a list of artists who have songs longer than '400'.

<!-- Make this drop down -->
#### SQL
```
set_list_development=# SELECT artists.name FROM artists JOIN songs ON artists.id = songs.artist_id WHERE songs.length > 400;

     name      
---------------
 Talking Heads
(1 row)
```

### Combining `JOIN` and `WHERE`

<!-- Practice filtering using where in combination with a join -->

<!-- Open question, should multiple joins be here e.g. 

SELECT * FROM songs JOIN playlist_songs ON playlist_songs.song_id = songs.id 
JOIN playlists ON playlist_songs.playlist_id = playlists.id
 -->

## Checks for Understanding

1. What are the two types of joins covered today? And, what do they return?
1. What is the default type of join used when you just type `JOIN`?
1. What is the SQL query to get a list of Artists who have songs that have been played more than 20 times?
1. Which of the following queries would require a join. 
    1. dfd
    1. sdfs
    1. dsfs
    1. sdfsd
1. How would you summarize when/why you need to use a join?
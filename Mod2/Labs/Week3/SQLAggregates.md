## SQL Aggregates

**Data in the Real World**
Our set list dataset is fun, and it helps us learn the mechanics of SQL.  But, SQL can be much more impactful than analyzing song data.  In fact, there is a whole field of study called `Data Analytics` that relies heavily on querying data to help us learn more about the world and our place in it.

One of the first projects new data analysts work on to learn their craft is an analysis of the [Titanic](https://en.wikipedia.org/wiki/Titanic) passengers.  In our lab today, we are going to do an abbreviated version of this project.

_A note on historic data_: Today, we strive to collect data that is accurate to each individual's identity.  Good data collectors use inclusive language, provide multiple options, as well as the ability to provide additional information.  Unfortunately, much of the data we have from history is not presented in an inclusive way.  We point this out not to discount all historic data, but to be better prepared to collect data today for future analysts.  

** Instructor Note ** You will want to walk through the dataset with students, clarifying what each column represents.

### Setup

1. In pgAdmin, create a database called `titanic`
2. Run [this script]() to set up the database.

### Questions

Use what you have learned about SQL so far to query the database and answer the following questions.  As you go, reach out to your cohort-mates and instructors with questions!

1. How many passengers were on the Titanic?
1. How many passengers were younger than 10?
1. What was the average age of passengers?
1. How many passengers were in each class of service?
1. What was the average age of survivors?
1. How old was the oldest survivor?
1. How young was the youngest survivor?
1. How many survivors were there for each age represented in the passenger list?
1. For each class of service, what was the average age of male and female survivors?
1. What are the names and ages of girls 10 years or younger who died?
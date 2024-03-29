# Week 3 Assessment

<p align='center'>
  <img src='../Images/Week3/erd_for_assessment.png'>
</p>

[Citation for ERD](https://circle.visual-paradigm.com/hospital/)
1. Use the Doctors Office ERD above to answer the following questions:
    1. How many patients can each doctor have?
    1. How many doctors can each patient have?
    1. How would you describe the relationship between patients and tests? Be sure to use either one-to-one, one-to-many, or many-to-many in your answer.
    1. What are the foreign keys in this diagram?
    1. What is the primary key for the Tests table.
    1. What query would return the number of doctors who have a specialization in "pediatrics"?

<br>

2. What does a join table do? Why would we need one?
3. What is a question that the following query helps answer?
```SQL
SELECT hometown, COUNT(name) FROM artists
GROUP BY hometown;
```
4. I'm trying to write a query to find the average age of all patients, but it's not working. How would you modify this query to get it to work as expected?
```SQL
SELECT age FROM AVERAGE(patients);
```
5. How would you describe the difference between a `LEFT JOIN` and an `INNER JOIN`
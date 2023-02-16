# Many-to-Many With an ORM

## Learning Goals
*  Reinforce how to structure many-to-many database relationships
*  Implement a many-to-many relationship using EF

### A Bit About Versions
Wow new update in EF Core 5.0: https://learn.microsoft.com/en-us/ef/core/what-is-new/ef-core-5.0/whatsnew#many-to-many

The old way of doing it: https://www.entityframeworktutorial.net/efcore/configure-many-to-many-relationship-in-ef-core.aspx

<!-- Instructor note, I recommend giving a quick note about gradual release of responsibility here and why we are having students learn on their own. -->

### Learning From the Documentation

https://learn.microsoft.com/en-us/ef/core/modeling/relationships?tabs=fluent-api%2Cfluent-api-simple-key%2Csimple-key#many-to-many

You add the fields and then it does the thing and makes the join table!

<!-- What's different? Very subtle, they call it rooms_id instead of room_id.... -->

<!-- Open question, should we we be doing things with CRUD here and how that works with a many to many relationship? Not really going to know until we build the next unit. I think leave it unless later we realize we want it. -->


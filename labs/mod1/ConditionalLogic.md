# Lab
Lab time is designed for you to prepare for upcoming lessons, and practice what you have learned so far.  Both aspects are important for your success.  During this time, you are encouraged to collaborate with fellow students, and reach out to instructors with any and all questions!

** Instructor Note ** Today's lab has very little 'prep' information; students should be ready to get right into Looping with this week's learning goals as preparation.  It would be great to take two opportunities to bring the whole group back together at least twice today to showcase what individual and groups of students are working on. We should also HIGHLY encourage group work (maybe even set some groups up from the start).  This project _should_ require students to use: math, string concatenation (or interpolation), conditional logic, and string methods.

<!-- I definitley agree that labs should be as collaborative as possible - I think at some point our instructor notes should be more explicit such as "Before this lab, create groups of 2-3 students and post groups in cohort Slack channel at the start of the lab." Almost making it like a checklist so it is easy for future instructors to prep. -->

## Practice

In today's lab, you are going to be putting together what you have learned so far into a mini project - something you can (and should) show off to your family and friends!

Using your what you have learned in lessons and labs so far, you are going to build an order-taking program that could be used at a restaurant.  Because we are early on in our program, this application will have some unrealistic paramenters, but will give you a good idea of the kinds of things you might start building even with just the fundamentals!

You are going to fork [this starter repl](https://replit.com/@MeganMcMahon1/ConditionalLogicLab#main.cs) and build a simple Order Taker program for a restaurant.

You SHOULD collaborate with others in your cohort!

### Order Taker
In this restaurant, we only take orders in batches of 4.  So, 4 people can order at a time, or 1 person can pretend to be 4 people ordering 4 different meals 🙂.

You are going to write a program that will ask for an order from 4 users.  We will want to store their orders in a variable called 'combinedOrder'.  A user's order will only be added to the 'combinedOrder' if what they ask for is included in the restaurant's 'menu'.

After the combined order is made, we should print a summary of the order and include the total cost.  At our restaurant, we charge $2.12 per letter in the order.  So, an order of "tacos, popcorn, popcorn, ice cream" would cost $57.24 (we don't charge for spaces, or commas).

When completed, your program output may look something like this (if it is not exactly the same words, that's no big deal - make it your own!).  Do take note that if someone orders something in a different case (upper or lower) than it appears in the menu, we should still accept that item; TACOS is the same as tacos and the same as TaCoS.

![](/images/Mod1/Labs/Restaurant1.png)


If you have a user that orders something NOT on the menu, your program might look something like this:

![](/images/Mod1/Labs/Exercise2.png)

**Keep an eye on slack!!** We will come together as a whole group every 30-45 minutes to work through some of the tougher parts of the project.  During these group sessions, we will ask for some of you to share out what you have been working on - a great opportunity to practice using technical language!
<!-- It might be helpful to have a list of all of the directions embedded here as well. Related to that, a thought I had was to include some type of brainstorming/planning/pseudocoding section for each lab - I wonder if we include this into labs it will push our students to grapple with problem solving better and we could potentially use early lab checkins to review high-level problem solving/pseudocoding for each section of the lab. Basically, we can catch students who's approach is off EARLY and redirect so they can grapple with the intended learning goals. Thoughts? -->

<!-- Overall I think this is a GREAT lab - really pushes studednts to apply the learning that we covered this week and I think is a real-world type of application (albeit a little simplified given where they are in their learrning). I think that as you continue to build labs, it is OK (and maybe even preferrable?) to iterate on past activities with more functionality, adjustments, etc. to mimick working off existing code, adding features, etc. I also hope this approach alllevaites some of the pressure/writer's block of trying to come up with a "new" thing or scenario. -->
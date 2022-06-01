# Week 1 Assessment

This weekly assessment is an opportunity for you to explore the main learning goals from the week.  If there are any topics that are unclear, now is the time to reach out for additional information and assistance!

During this assessment, you may use any resource other than fellow students.  Feel free to google, look back at your notes, lessons, etc...

## Build a Guessing Game

In a new [Replit](https://replit.com/~) project, write a program to greet users by completing the following steps:

1. Ask a user for their name, and then greet them by name.

![](/images/Mod1/Assessments/week1_1.png)

2. Update the program to only greet user's whose names include the letter 'a' (or 'A').  If the user's name does not include the letter 'a', we should let them know that we don't recognize their name.

![](/images/Mod1/Assessments/week1_2.png)

3. Ask the user if they would like to play a guessing game.  If they enter 'yes', have them guess a number between 1 and 10; at this point, you can set the answer to be any number you like (in the example below, I've used '7').  Give feedback to user based on the guess provided.  If a user answers anything other than 'yes' to the prompt asking if they want to play a guessing game, the program should end.

![](/images/Mod1/Assessments/week1_3.png)

## Stretch Goals
These can be done in any order.

* If a user opts to play the guessing game, loop through asking for guesses until the correnct answer is given.

![](/images/Mod1/Assessments/week1_4.png)

* If a user guesses something that is not a number, the program should exit gracefully (without an error!)

![](/images/Mod1/Assessments/week1_5.png)

* Update the guessing game to use a random number (between 1 and 10)

## Submission

In slack, DM a link to your replit project to your instructors.

Assessment Notes
- I think we should include some sort of rubric that lays out what is considered Passing vs Not Passing
- In addition to coding practice, it might be useful to have some short answer/fill in the blank type questions that allow students to show their learning in others way + explain concepts in their own words + make connections. Do you think we could do something similar to this using code comments? - https://www.w3schools.com/cs/exercise.php?filename=exercise_user_input1
- I think a benefit of including some short answer/annotate/fill in the blank type questions is that it allows students to show (and see for themselves) some of their learning that may not fully be captured in the coding section. I think about a student who might actually be on track but struggles with a syntax error the entire time and can't show much of what they know.  
- As I searched through lessons, I couldn't find anything related to Console.ReadLine() which seems to be a big component of this assessment setup. I eventually found it in the Lab section. It might be useful to include some language in the instructions for students around "gathering user input" to help trigger recall on the concepts touched on in the labs.
- As it is currently set up, this assessment doesn't really touch much on two of the lessons - How Computers Work and Datatypes/Variables. I think we could include some questions that include written responses for the How Computers Work portion. I envision just using code comments for written stuff so that we only have students working in one place. As for datatypes/variables, it might be good to include some demonstration of variable declaration + using proper datatypess to ensure mastery of syntax and concepts
- To me, the second exercise (evaluating whether a string contains "A") feels a little stretch-y. In my mind, we should aim to evaluate whether a student understands conditional logic, while this exercise also involves working with a method they would have to research more about (.Contains()). Is there a different exercise we could implement that is a little more targeted on conditional logic, perhaps with some work around variables too? Conversely, we could incorporate some "research" component where we link students directly to the .Contains() method, have them do some work with that to provide boolean outputs, and then give them the instruction to work it into the actual application. 
- Related to the conditional logic, I wonder if we do some work where we give them either a scaffolded function that requires them to fill in key parts to get it to work OR have them annotate an already written function to predict what the output could be? I think about the third exercise a lot here - it seems they have to manage some type casting as well as the setup for the conditional logic. If we are really just trying to gauge their understandng of conditional logic, perhaps giving them some clues on how to handle taking a string from the user input + converting to a number might allow us to really focus on the meat of the issue. 
- I do appreciate that you included some iterative approaches to building upon the previous exercise! I wonder if there is a way for us to include a place for them to comment out/submit/capture their prior code before moving onto the next step so we can still give feedback on those areas.
- Thinking about student submission, I wonder how we think about actually delivering feedback. I think we could do something where we just fork the student's REPL and annotate directly into it for specific feedback. 
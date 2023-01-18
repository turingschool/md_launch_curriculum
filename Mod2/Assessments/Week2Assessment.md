# Week 2 Assessment

## Questions
1. What does TDD stand for?

1. What are three benefits of using TDD?

1. Imagine you are in an interview.  The interviewer asks: How do you use TDD?

1. For the class below, outline the tests you would need.  Try to use as much C# syntax as possible. The first test has been provided for you.
```c#
public class Dog
    {
        public string Name { get; }
        public string Breed { get; }
        public bool IsHungry { get; private set; }

        public Dog(string name, string breed)
        {
            Name = name;
            Breed = breed;
            IsHungry = true;
        }

        public void Eat()
        {
            IsHungry = false;
        }

        public void Sleep()
        {
            IsHungry = true;
        }

        public string Speak()
        {
            return "Bark Bark!";
        }
    }
```
```c#
// Add your tests here

[Fact]
public void DogHasNameAttribute()
{
    Dog dog = new Dog("Nile", "Golden Retriever");

    Assert.Equal("Nile", dog.Name);
}
```

1. What is a merge conflict, and when might you encounter one?

1. You and a partner are working on a project together.  Your partner is working on aa-branch; you are working on bb-branch.  In as much detail as possible, describe how you both would get your work combined onto the main branch.

1. Why is it important to never merge your own branch (when working on a team)?

## Exercise
* Git Workflow

## Rubric
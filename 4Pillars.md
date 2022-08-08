## Four Pillars of OOP

There are 4 principles of OOP which we will introduce here, and continue to learn more about as we go.  At this point, some of these concepts might not make sense - that's ok!  We want to get a start on recognizing these patterns today, and we will re-inforce these patterns throughout your time at Turing.

### Encapsulation

**Contain Information in an Object, Only Expose Necessary Information**
Encapsulation hides the internal implementation of attributes and behaviors inside of objects.  When we declare a class, we are indicating what properties and methods will be encapsulated in the objects created from that class template.  These attributes and behaviors can be either **public** or **private**.  Public components are available from _outside_ the object; these are the properties and attributes that we can call on objects.  Private components are only available within the class; there is no mechanism to call that method or property from an object.

Let's take a car as a methophor.  When a car is created, all of the components that make it run are **encapsulated** in the body of the car - engine, gauges, breaks, seatbelts, indicators, etc... .  Some of these components are public: blinkers to indicate turns, brake lights, the sound of a reving engine.  These public pieces of information can be seen from _outside_ the car.  Other components are kept private: engine temperature, occupancy, transmission type.  These private components are essential attributes/behaviors of the car, but they do not need to be exposed - this additional information is not needed outside the car.

### Abstraction

**Only Expose High Level Attributes and Methods**
Abstraction is the practice of exposing _only_ what a user _needs_.  

> With a partner, what are some examples of abstraction in the real world?  You might want to go back to previous lessons 😉

Benefits of Abstraction
* Simple User Interfaces
* Complex Code is Hidden
* Easier Software Maintenance
* Security

### Inheritance

**Child Classes Get Attributes/Behaviors From Parent Class**
When we think about objects in the real world, we can often describe two different objects as having a 'type-of' relationship.  For example, a car, a motorcycle, and a semi are all _types of_ vehicles.  They all share some attributes and behaviors:

![UML Diagram of Car Motorcycle and Semi Classes](/Mod1/Images/Week4/InheritancePre.png)

While these classes are not identical, they do share a lot of attributes and behaviors.  Inheritance allows us to create a **parent** class that contains the shared components, with **child** classes that **inherit** these components and can include any additional attributes and behavior.

![UML Diagram of Car/Moto/Semi inheriting from Vehicle](/Mod1/Images/Week4/Intherited.png)

**Instructor Note** Make sure to walk through UML class diagramming.  You could show them the free tool [smartdraw](https://cloud.smartdraw.com/)

We will learn how to implement and work with Inheritance later in this mod!

> With a partner: what other Inheritance relationships can you think of in the real world? (try to think of objects that are not humans!)

### Polymorphism

**Shared Behavior May Differ For Specific Types**
In some cases, we might have objects that share behavior with potential small variations.  Take a look at the diagram below:

![UML Diagram of Polymorphism](/Mod1/Images/Week4/Polymorphism.png)

In this example, all dogs can `Speak()`, but one type of dog has a very distinct bark that will **override** the behavior that is inherited from the parent class.  We want to inherit that behavior because _most_ of the types of that class behave in the same way, with just this one outlier.

Like Inheritance, we will continue to explore polymorphism in later lessons!
##Day 1

1) New Requirement:  
     Write shameless green for bowling  
     Bob Martin's spec, "Game" class recieves _all_ rolls and calculates score.  

1) New Requirement:  
    Calculate score of incomplete game

1) New Requirement:  
    No-tap Game  
    This should make them extract a config.

1) New Requirement:  
    Duckpin Game  
    This should merely require adding a new config, no new code should be needed.  
    It's just like magic.  
    Yay, it's now lunch! (or possibly waaaay past lunch)

### Lunch

1) Introduce "structural" design patterns  
    adapters, composites, decorators and facades

1) New Requirement: Acquire rolls from several "source"'s
    * one by one from stdin
    * one by one from a file? (watch disk for changes?, or not?)
    * all rolls at once from a file?

    Game (Scorer?) should be independent of "source" of rolls.  
    They should TDD everything they write.
    Use this to explore adapters, decorators and facades.

1)	Explore possible designs via sequence diagrams

1)  Write code for various "sources"

1) New Requirement: Persist rolls to a "target"
    * file?
    * pstore?

    Game (Scorer?) should be independent of target for persistence
    They should TDD their new code.
    This might also be useful for exploring adapters, decorators and facades.

1)	Explore possible designs via sequence diagrams again

1) They write or "adapt" existing "source" and "persistence" providers.  See below.

#### Day 1 Instructor Notes/Questions/Ideas/Uncertainties

* They can write their own "source" and "persistence" providers (if time permits),  
  or
* We can give them code for the different "source" and "persistence" providers, but trouble them with code that conforms to different APIs. This would free them from writing the code, but ensure they have to write adapters.

Question: what's a requirement that would drive them to use the composite pattern?

# Day 2

1) Introduce "behavioral" design patterns  
    chain of responsibility, command, observer, state, strategy  

1) New Requirement:  
    Recalculate score when rolls change.   
    (Now they need to observe something.)

### Lunch

1) New Requirement:  
  Something that will force them to invent MVC.
    This is about loosen coupling.  Extend the existing example to teach it!


# Day 3

1) Go through the Magic Tricks talk slides to explain what to test  
    Give them a little app with multiple classes and some tightly coupled tests, and change requirements such that the tests break during a refactoring.  They should fix the tests, refactor to a new shape, and only _then_ implement the new requirement.

### Lunch

1) New Requirement:  
     Lowball  
     Gutter balls count as 10.  This is a special rule for 0 pins, which forces them to separate the number of pins knocked down from the score of those pins.

1) New Requirement:  
     The game I don't know with the red pin that's worth 10.
     1 specific pin counts 10 points?  rather than 1?  Or something?

1) New Requirement:  
     5-Pin
     Different pins score different values.  
     Should the incoming roles tell me the pin that fell, or the value of that pin?  Hmmmm.










----------------------------------------
----------------------------------------
## The "Official" outline
### Day 1 - Testing and Design
#### Lessons
* Understanding the practice of TDD
* Deciding what to test
* Creating tests that tolerate changes to code
* Bending reality with doubles, stubs, spies, mocks and fakes
* Rescuing tests gone wrong

#### Exercises
1) Use TDD to create an ideal test suite for a new requirement
1) Refactor a costly, confusing test suite into one that’s straightforward and economical

### Day 2 - Orchestrating Object Collaboration
### Lessons
* Understanding structural design patterns  
 	 adapters, composites, decorators and facades  

* Understanding behavioral design patterns  
    chain of responsibility, command, observer, state, strategy  

* Choosing the right technique for sharing code  
    inheritance vs composition vs decoration  

* Lowering costs by reducing coupling between objects  

### Exercises
1)	Practice well-known structural and behavioral patterns
1)	Learn how to choose between inheritance, composition and decoration by solving the same problem with each technique
1)	Explore different ways to remove conditionals by leaning on polymorphism 
1)	Simplify a real-world code example using a combination of techniques

## Day 3 - Application Architecture

### Lessons
* Modeling object interaction using sequence diagrams
* Defining architectural layers
* Managing dependencies between layers

### Exercises
1)	Design a new application using sequence diagrams
2)	Write code that implements a layered architecture


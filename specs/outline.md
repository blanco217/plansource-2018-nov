## Day 1

1) New Requirement -> Write shameless green for bowling  
     Bob Martin's spec, "Game" class receives _all_ rolls and calculates score.  

1) New Requirement  -> Calculate score of incomplete game

1) New Requirement  -> OUTPUT: Display simplest possible scoresheet on stdout  
    This is just so they can see a simple scoresheet independent of the tests.  
    We'll add support for different output targets later.  

1) New Requirement -> INPUT: Read rolls from stdin  
    Straightforward input from stdin.  
    Just like for output, we'll make this more complicated later.

1) New Requirement -> No-tap Game  
    This should make them extract a config.

1) New Requirement -> Duckpin Game  
    Should just need a new config.
    _It's almost like magic._  
    _Yay, it's now lunch! (or possibly waaaay past lunch)_

### Lunch

1) Introduce "structural" design patterns  
    adapters, composites, decorators and facades

1) New Requirement -> INPUT: Alternative sources of rolls  
    They add support for getting input from

    * highline (https://github.com/JEG2/highline/blob/master/examples/basic_usage.rb)
    * TTY (https://github.com/piotrmurach/tty, specifically TTY-prompt and TTY-reader)  
    They now need an adapter, so ..
    * Explore alternative designs via sequence diagrams.  
    _? Maybe they break up into teams, draw sequence diagrams and give presentations ?_

**Question:  
Should I provide pre-written input/output variants and have them just do the wiring?**

# Day 2

1) New Requirement -> OUTPUT: Display prettier scoresheet to stdout  

    * table_print (https://github.com/arches/table_print)
    * term_table (https://github.com/tj/terminal-table)
    * formatador (https://github.com/geemus/formatador)   
    * Explore alternative designs via sequence diagrams.

? Can we make them use decorators or facades to solve the above ?  

1) New Requirement: PERSIST: Save rolls for later
    * file?
    * pstore?
    * Explore alternative designs via sequence diagrams.


**? What requirement would drive them to use the composite pattern ?**

### Lunch

1) Introduce "behavioral" design patterns  
    chain of responsibility, command, observer, state, strategy  

1) New Requirement -> Recalculate score when rolls change.   
    (Now they need to observe something.)
    (Now they're headed towards MVC.)

1) New Requirement:  
    Something that forces them to use the state pattern.


# Day 3

1) New Requirement:  
  Something that will make them invent MVC.
    This is about loosening coupling.  
    Maybe they should break up into groups, research MVP, and then do presentations where they act out the parts. Some people play models, others views, others controllers, and finally, some folks play messages!

1) Go through the Magic Tricks talk slides to explain what to test  
    Give them a little app with multiple classes and some tightly coupled tests, and change requirements such that the tests break during a refactoring.  They should fix the tests, refactor to a new shape, and only _then_ implement the new requirement.  

    Remember FakeFS (https://github.com/fakefs/fakefs)

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


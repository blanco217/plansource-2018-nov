# Day 1

----
### Task 1 - Bowling Kata  

Branch:  
* task_1_bowling_kata

Time: 30 minutes

Instructor:  
* Describe the task (basically, say what's in tasks.md)  
* Make sure they can run the tests

----
### Task 2 - No-tap and Duckpin

Branch:
* task_2_support_notap_duckpin

Time: 2 30-minute blocks ?

Instructor:
* First, just do No-tap.
* Is shameless green open to No-tap?
* What do you need to vary? What smells? How to dry it out?
* Once they get No-tap working, ask them to do duckpin and watch them be really happy that to just add a config.

10:30?

----
### Task 4a - Lowball via config change and factory complexity

Branch:
* task_4_implement_lowball

Time: 30 minutes

Instructor:
* Encourage them to try to solve this problem by creating a LOWBALL config, and extending it/changing the factory in whatever ways are required to support LOWBALL.

They do:
* write code

Instructor:
* What keys did you add to the config?
* What changes did you make in the factory code?

----
### Task 4b - Learn to draw sequence and class diagrams

After they finish (or fail to finish) hacking the config/factory

Instructor:

* Have them study the sequence diagram tutorials listed in references.txt
* We explain class diagrams (TODO we draw one?, be prepared!)

----
## Lunch

(maybe here, or perhaps midway into the next task)

----
### Task 4c - Lowball via extract parser

Instructor:
* They probably made the config much more general (by passing in an operation and some lambda's to evaluate in the factory).
    * point out that these things are just hidden conditionals
        * if the config is 'a', do thing 'a1'
        * if the config if 'b', do thing 'b1', 
        * etc.
    * Conditionals mean we're missing objects.  
    * What objects are missing?
    * Make them figure out what varies, which is ...
        * the rules for figuring out what kind of frame the incoming rolls represent, and
        * the value to be added to the score for each pinfall
    


They do:
* draw sequence/class diagrams of their proposed LOWBALL design
* write code to
    * extract the thing that varies (StandardRollParser)
    * inject it so that they can depend on an abstract role (Parser)
    * create another player of the role (LowballRollParser)
        * Do they TDD this, or spike it via integration tests (the refactor branch commit at this point has ponderings)
    * inject LowballRollParser when they're playing LOWBALL


### Task 5 - Unit tests

Instructor:
* Walk through the Magic Tricks talk here.

Branch:  
* task_5_update_tests

Time: 60 minutes

They do:
* Update the unit tests
* Browse bowling_5_unit_tests_refactor and be prepared to discuss
    * The StandardRollParserTest uses a made up config.  Ask them why?  What purpose does this serve?
    * The Variant test uses a fake parser (TestParserWhichAlwaysReturnsTwoRollsOfOnePin).  Why?  Again, what purpose?



*Day 1 probably ends before they complete Task 5.  Continue it on Day 2*


# Day 2

----
### Survey and Reflection?

----
### Finish Task 5 - Unit tests (complete this if needed)

-----
### Task 7 - Finish Interactive Game

Wo-ah

-----
### Task 8 - Use classic scoresheet

Branch:  
* task_8_use_classic_scoresheet

Notes:  
For teaching adaptor pattern
Also has some interesting tests. It creates API tests for scoresheets.



# Day 3

----
### Survey and Reflection?

-----
### Task 9 - Isolate Frame Status

Branch:  
* task_9_isolate_frame_status

Notes:
For fixing slightly incorrect hierachy
For teaching composition
For discussing mutation

-----
### Task 10 - Output multiple scoresheets

Branch:  
* task_10_output_multiple_scoresheets

Notes:
For teaching observer pattern
For discussing MVC


-----
### Task 11 - Cheating

Branch:  
* task_11_cheat

Notes:
For teaching decorator pattern


----
----
----
----
----






    
Need to explicitely address

* "structural" design patterns  
    * adapters 
    * composites 
    * decorators
    * facades

* "behavioral" design patterns  
    * chain of responsibility
    * command
    * observer
    * state
    * strategy  
    

----
----
----
----
----

## The original "Official" outline
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


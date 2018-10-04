# Day 1
----
----
### Task 1 - Bowling Kata

Branch:
* task_1_bowling_kata

Lessons:
* Shameless Green
* Introduction to bowling scoring

Time:
* 30 minutes

Instructor:
* Describe the task (basically, say what's in tasks.md)
* Make sure they can run the tests


----
----
### Task 2 - No-tap and Duckpin

Branch:
* task_2_support_notap_duckpin

Lessons:
* Open/closed, isolating the things that vary, DRY
* Practice refactoring

Time:
* 2 30-minute blocks ?

Instructor:
* First, just do No-tap.
    * Is shameless green open to No-tap?
    * What do you need to vary? What smells? How to dry it out?
* Once they get No-tap working
    * ask them to do duckpin
    * watch them be really happy that they can just add a config.


----
----
### Task 4a - Lowball via config change and factory complexity

Branch:
* task_4_implement_lowball

Lessons:
* More of what worked might not be better
* Understand the tension between designing
    * one common, shareable but very abstract solution, vs
    * defining single abstract 'role' and dividing the code into multiple concrete role players.

Time:
* 30 minutes

Instructor:
* Encourage them to try to solve this problem by creating a LOWBALL config, and extending it/changing the factory in whatever ways are required to support LOWBALL.

They do:
* write code

Instructor after:
* What keys did you add to the config?
* What changes did you make in the factory code?


----
----
### Task 4b - Learn to draw sequence and class diagrams

After they finish (or fail to finish) hacking the config/factory

Lessons:
* Design is about the image in your head, not the characters you type

Instructor:

* We explain class diagrams (TODO we draw one?, be prepared!)
* Have them study the sequence diagram tutorials listed in references.txt
* Demo the seqence diagram syntax for creating new classes! They won't notice it in the tutorials.



----
----
## Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch

(maybe here, or perhaps midway into the next task)

----
----
### Task 4c - Lowball via extract parser

Lessons:
* Conditionals, no matter how well hidden, tell us to create objects
* Sometimes you have to stop and think
* Spikes can help you think if you don't understand the problem well enough to do TDD

Time:
* I wish I knew


Instructor:
* They probably made the config much more general (by passing in an operation and some lambda's to evaluate in the factory).
    * point out that these things are just hidden conditionals, i.e.
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
        * Do they TDD this, or spike it via integration tests (the refactor branch commit at this point has intergrations tests, with ponderings about TDD)
    * inject LowballRollParser when they're playing LOWBALL


----
----
### Task - Magic Tricks Talk

Time:
* 30 minutes

Lessons:
* How/When to test the 6 kinds of messages
    * Incoming command/query
    * Private command/query
    * Outgoing commnd/query

Instructor:
* Walk through the Magic Tricks talk here.


----
----
### Task 5 - Unit tests

Branch:
* task_5_update_tests

Lessons:
* Practice writing loosly coupled unit tests

Time:
* 60 minutes

They do:
* Update the unit tests
* Browse bowling_5_unit_tests_refactor and be prepared to discuss
    * The StandardRollParserTest uses a made up config.  Ask them why?  What purpose does this serve?
    * The Variant test uses a fake parser (TestParserWhichAlwaysReturnsTwoRollsOfOnePin).  Why?  Again, what purpose?



*Day 1 probably ends before they complete Task 5.  Continue it on Day 2*


# Day 2
----
----
### Survey and Reflection?


----
----
### Finish Task 5 - Unit tests (complete this if needed)


----
----
### Task 6 (has no 'task' branch in repo)

Branch:
* bowling_6_detailed_scoresheet_refactor

Notes:

This refacotor adds PendingFrame as a subclass of Frame so scoresheet can differentiate between a missing roll and a gutterball.

It also adds max_rolls_in_frame to the configs so it can print a frame that's the right visual width.  I can't figure out a way to derive this number, so I just put it into the configs.

The actual DetailedScoresheet code is not very interesting, but the TDD that creates it might be useful for them to study.

The first commit in the refactor branch contains a description of the problem in bowing_test.rb

The step-by-step refactors do a pretty good job of walking through in the right size chunks.

I fear they won't understand the next refactoring unless they understand this one, so to get them through this as quickly as possible....


Lessons:
* TDD
* Delegation to  player of a role
  * Frames sends running_score to a 'frame' which increments the score or returns nil, depending on whether it's a Frame or a PendingFrame.
* How inheritance goes wrong
  * When PendingFrame was created, the thing it specialized should have been pulled down to parallel subclass 'CompleteFrame'.

Instructor:

* Hook up to the projector and show them how to compare branches in GitLens.
    * Select bowling_5_unit_tests_example then 'select for compare'
    * Select bowling_6_detailed_scoresheet_example then 'compare to selected'
* Walk through the comparison together, showing them the changes.

They do:
* Look at the endpoint of bowling_6_detailed_scoresheet_example and draw class/sequence diagrams
* Walk through the refactoring and ponder the decisions
* Articulate things that are wrong/suspicious about the design

----
----
### Task 7 - Finish Interactive Game

Branch:
* task_7_finish_interactive_game

Notes:

This branch adds Game, Player, MissingNormalRollsFrame, MissingBonusRollsFrame, GeneralTurnRule, and FinalTurnRule.

Lessons:
* Layered Architectures
* More practice with sequence/class diagrams
* Practice making up their own designs

Time:
* ???

Instructor:
* We should re-read the tasks.md in the branch before talking to them

They do:
* Get oriented by studying the commits up to where the task branch starts (8 commits into the bowling_7_interactive_play_refactor, after the initial annoying puts/chomps have been written.)
* Draw class and sequence diagrams for the code as it exists at the START of the task (This might not be needed if they've drawn diagrams of bowling_6_classic_scoresheet_example.)

NOTE: TAG THIS COMMIT IN THE REFACTOR BRANCH ?

Once they're oriented about the starting point, they do:
* Discuss possible interactive game designs
* Draw class and sequence diagrams for their designs
* Maybe ? write some code (probably not)
* Prepare to present their design to the class, illustrated by their diagrams

----
----
## Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch Lunch
----
----
### Task 7a - Interactive Game Design Presentations and Discussion

Teams take turns presenting their interactive game designs, respsonding to questions from the audience.


----
----
### Task 7b - Critique my Interactive Game implementation

They do:
* checkout branch bowling_7_interactive_play_refactor
* draw sequence/class diagrams of the end point
* class discussion to critique the code


----
----
### Task - Patterns keynote presentation

Time:
* 30 minutes

Lessons:


Instructor:
* Walk through the Patterns presentation here.


----
----
### Task 8 - Use classic scoresheet

Branch:
* task_8_use_classic_scoresheet

Lessons:
* Adapter pattern
* Test doubles: stubs, mocks, fakes

Instructor:
* Remind them about the adaptor pattern
* Suggest that they write a Scoresheet API test
* Ask them to consider which scoresheet should be used in the tests
* Should they define a FakeScoresheet for the tests? If they create a Fake, how will they ensure that the 3 players of the scoresheet role (DetailedScoresheet, ClassicScoresheet, FakeScoresheet) remain in sync?
* What if they wanted to Mock the scoresheet in the tests?  How hard/easy is this, given the current implementation (Game has a demeter violation, i.e. scoresheet_maker.new().render).

They do:
* Adapt ClassicScoresheet such that it can be used by Game (i.e. such that it responds to #render)
* Change Game to be able to use either scoresheet
* Decide how to test the Game/Scoresheet interaction.
    * Game tests using a real scoresheet
    * Game tests by stubbing #render in a real scoresheet
    * Game tests using a fake scoresheet (whose API they guarantee)
    * Game tests using a mock





# Day 3

----
### Survey and Reflection?

----
----
### Task 9 - Isolate Frame Status

Branch:
* task_9_isolate_frame_status

Lessons:
* Separating abstract and concrete in Inheritance Hierarchies
* How correct inheritance hierachies enable composition
* Composition
* Strategy-ish pattern
* Consequences of immutability
    * Where is the logic to pick the correct status?
    * How would this be different if you allowed the rolls in a Frame to mutate?

Notes:
For fixing slightly incorrect hierachy
For teaching composition
For discussing mutation

----
----
### Task 10 - Output multiple scoresheets

Branch:
* task_10_output_multiple_scoresheets

Lessons:
* Observer pattern
* Loosening coupling

Instructor:
* Have them write list of ways to be coupled, from most tight to most loose.  Their list should contain things like:
    * I know the name of a class and say #new -> #render
    * I get passed an object which I hold in a variable, to which I say #render
    * I hold a list which others can put themselves on, when I change, I iterate over the list and send each item a message.
    * I know a rule by which I can dynamically figure out to whom to send #render
    * I know a rule by which I can dynamically figure out to whom to send a message, which is also dynamic
    * Someone passes me a lambda (command) which I then execute (the 'call' dilemma.)


----
----
### Task 11 - Cheating

Branch:
* task_11_cheat

Lessons:
* Decorator pattern
* Testing decorated objects


----
----
### Stickers !!

----
----
### All Bowl !!

Have them pair up and bowl, using a random number generator to determine each roll's pinfall. They can play the bowling variant of their choice.  The winner advances, the loser becomes a fan of the winner.

Play until only one winner remains. They get the 'Luckiest Bowler' certificate.


----
----
### Pep talk and Goodbyes



----
----
----
----
----
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

## General notes

- Write down the purpose of each lesson/task on the whiteboard

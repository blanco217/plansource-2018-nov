## Bowling Spec

1) Implements Martin's bowling design, that is

    A Game class  
    accepts a complete games worth of rolls, and  
    calculates a score.
 
1) Accept rolls one at a time

    Take input from the console and/or a file.  
    Persist rolls in memory and/or pstore.   

    Should be able to accept input from any source.  
    Should be able to use any persistence mechanism.  

    Accept input from multiple concurrent sources?  
    Simultaneously persist to multiple stores?  

1) Recalculate the score when necessary.

1) Output the running pinfall/score

    To the console.  
    To html?>  
    To a file??  
    To pstore??

    Output to multiple concurrent targets?


## Bowling Variants

1) Generous Strike: A strike is 9 (or 8 or 7, whatever) pins

    If you knock down 9 (or whatever) pins in one roll, that's a strike. The frame ends but you get two bonus rolls from the next frame(s).  

1) Duckpin: A frame contains 3 rolls

    If you knock down 10 pins in two rolls, that's a strike.  The frame ends but you get two bonus rolls from the next frame(s).  
    If you knock down 10 pins in three rolls, that's a spare.  You get one bonus roll from the next frame.  
    Otherwise the frame score is the sum of the pinfall of the three rolls in the frame.  

1) 5 Pin (Canadian): 

    5 pins are arranged in a 'V' pointing towards the bowler.  
    The center pin is worth 5.  
    The two adjacent pins are worth 3.  
    The end pins are worth 2.  
        So max of 15 within a frame (not counting strikes or spares).  
    A strike is all 15 pins on first roll, you get two bonus rolls as usual.
    A spare is all 15 pins in first two rolls; 1 bonus roll as usual.

1) Lowball:

    Lowest score wins  

1) TODO: What's the game where one pin  is painted red and worth more???????
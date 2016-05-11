#We've been asked to build a game!#

In order to take our game live we will need to first determine our "MVP".   In the development world the "MVP" is typically defined by our client as the bare minimum requirements our program needs to have in order to pass.  We call it the MVP because it is our 
    __Minimum Viable Product__.  

#Client Meeting!#
I met with our customer and listened intently to put together this list of requirements for you. If this sounds impossible, don't worry; it's easy when you break down the code into small manageable tasks.  I know you can handle it!  Now let's look at what we'll need to do:

:white_medium_square: [Prompt] the player to enter their [name].

:white_medium_square: Use their [name] to print a greeting.

:white_medium_square: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.


:white_medium_square: Before each guess, [Prompt] the player:

  1. let them know how many guesses (out of 10) they have left.
  2. to make a guess as to what the [target_number] is.
        

:white_medium_square: [if] the player's guess is less than the [target_number], [alert] "Oops. Your guess was LOW."

:white_medium_square: [if] the player's [guess] is greater than the [target_number], [alert] "Oops. Your guess was HIGH.".

:white_medium_square: [if] the player's [guess] is equal to the [target_number], [alert] them "Good job, [name]! You guessed my number in [number_of_guesses] guesses!".

:white_medium_square: Keep track of the [number_of_guesses] the player has made.

:white_medium_square: Keep allowing the player to guess until they get it right, [or].

:white_medium_square: [if] the players [number_of_guesses] is equal to 10 without guessing correctly, [Alert] "Sorry. You didn't get my number. My number was [target]."

Before we jump into the code lets pause for a minute to think about how our users will enter information (user Interface) and define some variables.

#User Interface#

from the MVP meeting with our customer we listed the requirements MVP above.  I have highlited some of the variables, if statements, prompts, incrementers, and alerts above can you spot them?

Variables: | type   
---------------|---------        
name |  string               
target_number | number            
players_guess | number
number_of_guesses | number      

Logic: | code
---------------------|------------------------
error test | !number, to_string, Title case?        
random number 0-100 | math.random          
errror test | 0 => 100
increment guess | number_of_guesses++

User Interface: | code
---------------------------------|------------
ask and store player's name | prompt();
Display greeting name | alert();
guesses left, | warning();
make a guess | prompt();
Your guess was HIGH. | prompt();
Your guess was LOW | prompt();
You Win! | alert();
Sorry you didn't guess my number. | danger();

Functions: | Method
----------------|-----------------------------------
bad player name | if name = ""
too Low | if players_guess < target_number
Too High | if players_guess > [target_number]
Victory | if players_guess = [target_number]
Gameover | if number_of_guesses >=10

#3.  Setting Up Our Environment!#

If you are using c9.io and cloned the project from Github you should be ready to go.  Otherwise lets check to be sure we have everything in place.  
See if you have the following files in your C9.io workspace.
    1. Readme.md 
    2. GuessMyNumber.js

The file readme.js is full of our instructions.
The file GuessMyNumber.js should be completely empty -You didn't think I was going to do all the work did you?

### Lets get Started!###

#4. Prompting for information#
Our first requirement is to greet the user by name and ask (prompt) them to guess a number between 1 and 100. To accomplish that, we'll need to write a script that gets input from the user, stores that input, and then uses that stored value to create some output. We can do all this in just a few lines of JavaScript code:  Please open your GuessMyNumber.js file and type in the following code _*EXACTLY*_ as it is dislayed below.
```javascript

var name = prompt("Welcome to 'Guess My Number!  What's your name? ");
var player_guess = alert("See if you can guess my number in less than 10 tries!");

```

That was easy!  When the game is loaded, our user will be asked to enter his/her name. 
```javascript 
var name = prompt("Welcome to 'Guess My Number!  What's your name? ");
```

This is the first of two jobs belonging to "prompt". The "prompt" method reads a line from our input field (characters will be typed into an input field on the pop-up window in ur browser). When you call prompt, it causes the program to halt until the user types their name and presses the Enter key.  

The second job is to store the players name as our [name] variable.  So you see when we assign a variable name to a "prompt" command it asks for a value and saves the user's input to the program as an object which we assigned to the variable we defined as [name].  "Prompt" can store string (text), or integers (numbers). 

##Alert the user##
The second block of code...
```javascript
    var player_guess = alert("See if you can guess my number in less than 10 tries!");
```
This block of code essentially works the same way but it doesn't allow for the player to input any information.  The "alert" command offers the user an ok button to proceed but does nothing with the result of you pressing ok other than resume from its paused state.  Kind of like talking to a pet turtle right?  Thank goodness that ok buton is there otherwise the program would be frozen.  

So far the player has typed his/her name and hits the Enter/Return key, THen they see a second message that starts the game.  Well that sounds like a good start but hmmm... something is missing.  Our prompt command stores their name be we are not using it in fact our MVP required us to use their name in a greeting.  Also how do we know the computer didn't pick a number less than zero or greater than 100?  We definitely need to be more friendly and tell the player a little bit more about the game.  Lets go back to th eMVP list above doesn't it say the computer would choose between 1 and 100.  We must pass that information on to our player in the "alert" command.  What else can we do to make our game better?

    What if they don't want to play?  How will we handle that? 
    What if they can't play because they have chores or homework to do?  
 We should program our game to detect if they want to play "Guess My Number!" by testing if their guess is within the lower and upper limit.  What it their guess is not a number al all?
    
    Alert doesnt store any values. Why are we using alert instead of prompt?

These decisions come up all the time in software development that's the fun part... we get to make __Executive Decisions!__  

But wait, asking the user if they want to play is not in our MVP list from above.  True, but it really helps the program if our users are informed on what to do or given the opportunity to stop playing right?  Besides the better we make the program, the more people will paly the game and the work we will be awarded and the more we can charge for our work because we are __Awesome!__.  Whenever we have an opportunity to improve the user experience we should try our best. Unless of course those efforts will cause us to turn our work in late, or those efforts will cost us a lot of extra time and money which we cannot afford.  It's a good opportunity to ask your fellow developers what they would do in this situation if you don't know.  Developers are always willing to share their ideas.  

So here is our first opportunity to make an impression on our customer!  You can be the one who decides what our greeting should be.  Maybe you can ask a family member or your neighbor.  Before you ask a pet turtle for inspiration, below is an example for you to get started with.  You can paste the code just as it is right into your javascript file or you can change the wording inside the "  ".  Be sure not to delete the "" and also double check your spelling!  We really need to impress our client and our players.  Especially since this is an added feature!
```javascript
  var name = prompt("Hello, what's your name? ");
  alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to proceed.  You may type 'quit' or 'no' anytime in the future to leave the game");
 ```
__Hint:__  Click your mouse anywhere inside the code window above and press Ctrl+A to select all.  Then hold and press Ctrl+C to Copy to your clipboard after you navigate into your GuessMyNumber.js file press Ctrl+V to paste.

####Wow the first two check boxes are off our list!  However we are still uncertain how we are going to allow our players to quit early but lets move on anyway.
:ballot_box_with_check: [Prompt] the player to enter their [name].

:ballot_box_with_check: Use their [name] to print a greeting.


###Our player greeting is done. Let us look at our next requirement###

#5. Random Numbers and Math!#
###:white_medium_square: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.###

Javascript uses Math.random() which is a bult in JavaScript method used to generate a random number within a given range.  Calling Math.random should be able to create a [target_number] for us. However Math.random selects a random number from 0 to .999999.  Additionally Math.random is not a whole number in fact look at all those nines after the decimal. 

Oh no! Math.random will return a floating decimal number less than 1 and we told our user we were going to pick a number from 1 to 100.  How can we make this right if not at least fair?  Well in order to return 1 to 100 we would simply need to multiply the result of Math.random by 100 and add 1.  Here is another JavaScript trick.  Math.floor is another command we use to round down to the nearest whole number.  So we choose a floating decimal between 1 and 100.999 then round down to the nearest whole number in order to chomp off those pesky numbers after the decimal. 


        __OFF TOPIC:__ 
        Do you remember from Math class the "Order of Operations" principle?  Yeah you thought you'd never use it in real life right?  Well guess again!  In summary the order of operations says certain math functions must be performed first before others.  Do you remember the acronym PEMDAS?  

        PEMDAS stands for: 
        1. _P_ erenthesis, 
        2. _E_ xponents, 
        3. _M_ ultiplication, 
        4. _D_ ivision, 
        5. _A_ ddition, and 
        6. _S_ ubtraction 

        PEMDAS is the order all mathmaticians (and JAvaScript) must handle complex math.  In the example below see if you can follow the work as we add parenthesis "()" to our code.  Remember we handle all the math within the innermost parenthesis first working our way outward until there are no more parenthesis left
            1.   Math.random_()_ = 0 to .999999
            2.   Math.random() _*100 _ ) = 0 to 99.99999
            3.   _(_ Math.random()*100) _+1)_ = 0 to 100.9999
            4.   Math.floor# _(_ (Math.random()*100)+1 _)_ = 0 to 100

Whew that was some really hard math!  If this doesn't make sense dont worry, it is a very complicated law of Mathematics that you will be familiar with very soon.  And you can say you learned it here first!  For now our next line of code will look like this.  
```javascript

       var target_number = Math.floor((Math.random()*100)+1);      
       
```

The code in the example above creates a variable named [target_number] and sets it equal to an integer between the range 1 and 100.  In JavaScript try to think of the equals sign as assigning a value to a variable.  If I were to read your code out loud I might say it like this:  

"Variable" target_number "gets the value of" a random "whole" number between 1 and 100.


###That's another requirement down!
:ballot_box_with_check: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.

###Let's look at the next step...

#6. Counting our guesses#
:white_medium_square: Before each guess, _*[Prompt]*_ the player:

  1. let them know how many guesses (out of 10) they have left.
  2. to make a guess as to what the [target_number] is.

The first step is to let them know how many guesses they have left.  So you can see we will need a formula and a variable to track how many guesses the player has made.  Obviously when the player first starts they haven't made any guesses, so we'll create a variable named [number_of_guesses] that's set to 0 at the start of every game.  Next we will want [number_of_guesses] to count up by 1 on each turn. Here is a little known JavaScript trick using ++ to count up by one.  

It's the same as saying "number_of_guesses" gets the new value of "number_of_guesses + 1". 
```javascript
    
    var number_of_guesses = 0;
    number_of_guesses++;

```
This looks crazy doesn't it?  But it works!  In fact we have used this before in a "for loop" do you remember? 
```javascript
    //  for example only do not paste this into your program!
    for(var i = 0; i <= 10; i++)
```
The incrementer is near the end.  Do you see "i++"?  

#7.  Join objects like magic!# 
Before we allow our player to make a guess as to what the [target_number] is,  our MVP states we must first tell them how many guesses they have left...  

Way back in step one we learned how to prompt our user to input information using the "prompt" command. 

The first thing you might attempt to do is display the [number_of_guesses] remaining but how would they know what the number meant.  Well we need to speak them.  After all we are the program developers right?  We can do anything including joining our code right smack in the middle of a well written sentence!  

How we request their input is called the "prompt" command; and how we join our code in a sentence is called "concatenation". In fact we used both "prompt" and "concatenation" previously when merging the playyers [name] into our greeting in step one.  The prompt method simply retrieves input from the user and stores it as a variable.  Prompt in the next code block is going to call for our users guess (input) and then records the user's number as their guess.  

One magical way to interact with our users is through concatenation.  'Concatenation' works with string (text) numbers, variables, functions, and other objects in JavaScript to concatenate (join) multiple objects together using the + sign, just as many other languages do. Something like this: "You have + [7] + guesses left!"  Well it is actually a little more complicated but essentially I want you to recognize we have some words before and after our code which is a variable name [guesses_remaining] joined by '+'.  Remember the number [7] represents our [guesses_remaining] variable and is updated by ++ (one turn) each time the user takes a turn at guessing our number.  So we can't hard code the number in our well written sentence, in fact our remaining guesses has to be able to change as the game goes on.  Thats the magic happening behind the curtain using variables and 'concatenation'.
```javascript
var guesses_remaining = (10-number_of_guesses);
alert("You have" + " " + guesses_remaining + " " + "guesses left.  Guess what my number is");

```
One other thing I want to point out is concatenation will not add spaces into your well written sentence unless you tell it to.  When we want to display string (words) we enclose our words in  " " (double quotes) such as "You have" and "guesses left."  Notice I also inserted two extra blank spaces into our well written sentence above.  The first space appears after the word 'have' and the second appears before the word 'guesses'. They look like this " " two double quotes around a space is all it takes.  I could also have written our code like this:
```javascript
var guesses_remaining = (10-number_of_guesses);
alert("You have " + guesses_remaining + " guesses left.  Guess what my number is");
```
See if you can find the extra spaces.  They both display the same well written sentence just two different ways to do the same thing thats all.  For future reference if you place double quotes around a number, or a variable name, JavaScript will treat it like a word so be extra cautious!  Remember ##We are Awesome## and we never make mistakes like this!  _Well maybe once in a while_. 

###Hey wait a minute "alert" just tells the reader what we want to say and give them an 'Ok' button to proceed.  Our MVP says we need to prompt them for their guess.
Well good thing you are paying attention!  Yes, the alert, and prompt, commands perform unique tasks.  Prompt is actually what we need to use here so lets make that change.  


#8. Progress#
Lets take a minute to review our entire code up to this point just to make sure we are all on the same page.
```javascript
var number_of_guesses = 0;
var guesses_remaining = 10;

var target_number = Math.floor((Math.random()*100)+1);

var name = prompt("Welcome to 'Guess My Number!  What's your name? ");
alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to proceed.  You may type 'quit' or 'no' anytime in the future to leave the game");


    number_of_guesses++;
var guesses_remaining = (10-number of guesses);
var players_guess = prompt("You have" + " " + guesses_remaining + " " + "guesses left.  Guess what my number is" );

```

Check your code against the progress report above first then lets save our file: ###GuessMyNumber.js### before we move forward.  


from within c9.io select:
     File > Save > OK.  


##Well Done! lets review what you have just completed!##

:ballot_box_with_check: [Prompt] the player to enter their [name].
```javascript
    var name = prompt("Welcome to 'Guess My Number!  What's your name? ")
```
:ballot_box_with_check: Use their [name] to print a greeting.
```javascript
    var player_guess = alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to PLAY, or Type no to Cancel on the next screen to quit. Once we begin, you may type 'quit' or 'no' anytime in the future to leave the game");
```
:ballot_box_with_check: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.
```javascript
    var target_number = Math.floor((Math.random()*100)+1); 
```
:ballot_box_with_check: Keep track of how many guesses the player has made.
```javascript
    var number_of_guesses = 0;
    number_of_guesses++;
```    
:ballot_box_with_check: Before each guess, _*[Prompt]*_ the player:
  1. let them know how many guesses (out of 10) they have left.
  2. to make a guess as to what the [target_number] is.
```javascript  
    var guesses_remaining = (10-number of guesses);
    var players_guess = prompt("You have" + " " + guesses_remaining + " " + "guesses left.  Guess what my number is" );
``` 


#9.  A fork in the road#

Let's look at the next group of requirements from our MVP list.

:white_medium_square: [if] the player's guess is less than the [target_number], [Alert] "Oops. Your guess was LOW."

:white_medium_square: [if] the player's [guess] is greater than the [[target_number]], [Alert] "Oops. Your guess was HIGH.".

:white_medium_square: [if] the player's [guess] is equal to the [target_number], _*[Alert]*_ them "Good job, [name]! You guessed my number in [number_of_guesses] guesses!".

:white_medium_square: Keep track of the [number_of_guesses] the player has made.

:white_medium_square: Keep allowing the player to guess until they get it right, [or].

:white_medium_square: [if] the players [number_of_guesses] is equal to 10 without guessing correctly, [alert] "Sorry. You didn't get my number. My number was [target]."

:white_medium_square: [else] the player has made a choice that is not even a number and clearly does not want to continue to play.


// Wow there is a lot of things going on here.  Do you see we are at a fork in the road?  [if] this [else] that and if not then [else] do this [or] another [if] statement.  Ha! no problem you ? just break it into manageable chunks!  Sure thing.  First we want to know when the player actually wins, or looses the game.  I mean lets get this thing over with soon, that's a lot of code to write!

##Conditionals##
first we need to understand how __Conditinals__ work.  Conditionals rely on a "boolean expression" (one with a true or false value) to decide whether the code they contain should be executed. Javascript has constants representing the two boolean values, true and false.  When JavaScript looks at the conditional [if] statement (the line of code that starts with the word if) and the [if] statement is a 'true' statement, the code that immediately follows will run (execute).  If not, the following code surrounded in {} is just ignored.  JavaSccipt then proceeds to the next line and tests to see if it is true or false and so on.   If the players guess is too high we should probably tell them they are too high, similarly if thier guess is too low we should tell them they are too low.  Else if their guess is not a number we should exit the game.  We use Javascript to run and test the users guess against portions of our code under certain "Conditions".  Thats where the word __"Conditionals"__ comes from. 

##10. Lets dive into our first Conditional statement!##  

First we need to compare the player's guess with the target. If it's too high, we print a message saying so. Otherwise, if it's too low, we print a message to that effect, and so on... doesn't this look like we need the ability to execute portions of our code only under certain conditions?

### Too Low ###
If the player's guess is less than the [target_number], say "Oops. Your guess was LOW."
```javascript
if(players_guess < target_number {
    alert("Oops. Your guess was LOW.")
}
```

### Too High ###
If the player's guess is greater than the [target_number], say "Oops. Your guess was HIGH."
```javascript
if(players_guess > target_number {
    alert("Oops. Your guess was HIGH.")
}
```

### Game Over ###
If the player runs out of turns without guessing correctly, say "Sorry. You didn't get my number. My number was [target_number]." 
```javascript
if([number_of_guesses] >= 10 {
    game_over = true;
    alert("Sorry. You didn't guess my number. My number was " + [target_number] +".");
}

```
    Q. I notice that you're indenting the code between the if and the end. Is that required?

    A. Javascript doesn't treat indentation as significant to the meaning of the program, No. (Unlike some other languages, such as Python.) But indenting code within if statements, loops, methods, classes, and the like is just good coding style. It helps make the structure of your code clear to your fellow developers (and even to yourself).

### Victory!!! ###
If the player's guess is equal to the [target_number], tell them "Good job, [name]! You guessed my number in [number_of_guesses] guesses!"
```javascript
if(players_guess = target_number {
    game_over = true;
    alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
}

```
#11.  Want to Quit???###
Remember a while back we wanted to alow our user to exit the game at any time.  Well in order to quickly determine if the game is over lets create a variable that we can use that simply switches between true or false.  This [game_over] variable will change if the player has typed in 'quit' or 'no'. We will also call [game_over = true] if the player guessed correctly or they run out of turns and we can end the game by victory or you loose.  At the beginning of every game we obviously want this [game_over] variable to be set to "false" because the game is not over..  Additionally we will move this variable with the other setup variables to the beginning of our program to reset the game to its starting values and to prevent unnecesary conditionals from ever being tested.  
```javascript
var game_over = false;
var number_of_guesses = 0;
var guesses_remaining = 10;
```

There is a way we will test to see if the user wants to quit.  If the player types in anything other than a number or a number outside our range of 1 to 100 they obviously don't want to play and we can call the [game_over] = true.  Remember when using conditionals all the code between the {} will run while the conditiona is true.  Using this knowledge we have the option to display different messages and change variables for each condition.  Lets take a look at how we do this when all other conditions are false we use the [else] command to capture any user input that does not meet our condition testing and allows us to build an emergency exit from our game.

Do you see the word 'NAN' below? Well 'NAN' is short for "Not a Number" if(players_guess='NAN') they must have typed in something like 'quit' or 'no' which are not numbers.  If the 'NAN' statement is true, we will want to quit our game.  But what if the [players_guess] is zero or negative or if the [players_guess] is greater than 100?  how will we test that?
```javascript
game_over = false;

    if(players_guess='NAN'){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }   
    if(players_guess < 0){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }
    if(players_guess > 100){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }
```
This seems like a lot of code lets see if we can understand conditionals better in order to simplify our code.
    

        Here are some more examples of evaluation conditional statements
            Code                   |  Meaning                                               |  Result
            -----------------------|--------------------------------------------------------|-----------------------------
            Condition = false
            
            if players_guess >= 2  | if players_guess is less than the number 2 | "I won't run!" end
            if players_guess > 2   | if players_guess is less than or equal to the number 2 | "I won't run!" end
            -----------------------|--------------------------------------------------------|-----------------------------
            Condition = true
            
            if players_guess = 2  | if players_guess is equal to the number 2 | "I will run this code!" end
            if players_guess == 2  | if players_guess is like the number 2 | "I will run this code!" end
            if players_guess === 2  | if players_guess is exactly the same as the number 2 | "I will run this code!" end
            if players_guess <= 2  | if players_guess is less than or equal to the number 2 | "I will run this code!" end
            if players_guess < 2   | if players_guess is less than the number 2 | "I will run this code!" end
            if players_guess != 2  | if players_guess is not equal to the number 2 | "I will run!" end 

        Wait! is that a mistake why is the "!" in the code above?  Javascript has the boolean negation operator "just in case someone calls opposite day", !, we call it "Bang" which lets you take a true value and make it false, or a false value and make it true.  The ! below reads "if not true", or "if not false"
            if !true     "I won't run!" end
            if !false    "I will run!" end
            

        If you need to ensure that two conditions are both true, you can use the && "and" operator.
            if true && !false   "I will run" end
            if !true && false  "I won't!" end
            
        If you need to ensure that either of two conditions are true, you can use the || "or" operator.    
            if false || false "I won't!" end
            if false || true  "I will run!" end

Spoiler Alwert!   I'm going to help you out a bunch in hopes that you can review the code below and compare it with some examples of Conditional Statements above to see how we are able to shorten all those messy lines of code. 
```javscript
        if(players_guess < target_number) {
        alert("Oops. Your guess was TOO LOW.");
        number_of_guesses++;
        var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess > target_number) {
        alert("Oops. Your guess was TOO HIGH.")
        number_of_guesses++;
        var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess == target_number) {
        alert("Good job, " + name + "! You guessed my number in " + number_of_guesses + " guesses!");
        game_over = true;
        }
        if(number_of_guesses >= 10) {
        alert("Sorry " + name + ". You used up all your guesses and still didn't guess my number.  My number was " + [target_number] +".");
        game_over = true;
        } 

    
    else{
       var status = prompt("It appears you don't want to play.  Type Quit in the field below to end the game, or Play to continue")
       if(status == "quit"){
           alert("Bye for now " + name + "!")
           game_over=true
       } 
```


We have done some amazing work so far! We have just one more requirement to go for our guessing game!
##lets review what you have just completed!##

:ballot_box_with_check: [Prompt] the player to enter their [name].
```javascript
    var name = prompt("Welcome to 'Guess My Number!  What's your name? ")
```
:ballot_box_with_check: Use their [name] to print a greeting.
```javascript
    var player_guess = alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to PLAY, or Type no to Cancel on the next screen to quit. Once we begin, you may type 'quit' or 'no' anytime in the future to leave the game");
```
:ballot_box_with_check: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.
```javascript
    var target_number = Math.floor((Math.random()*100)+1); 
```
:ballot_box_with_check: Keep track of how many guesses the player has made.
```javascript
    var number_of_guesses = 0;
    number_of_guesses++;
```    
:ballot_box_with_check: Before each guess, _*[Prompt]*_ the player:
  1. let them know how many guesses (out of 10) they have left.
  2. to make a guess as to what the [target_number] is.
```javascript  
    var guesses_remaining = (10-number of guesses);
    var players_guess = prompt("You have" + " " + guesses_remaining + " " + "guesses left.  Guess what my number is" );
``` 

:ballot_box_with_check: [if] the player's guess is less than the [target_number], [Alert] "Oops. Your guess was LOW."
```javascript
    if(players_guess < target_number {
    alert("Oops. Your guess was LOW.")
    }
```    
:ballot_box_with_check: [if] the player's [guess] is greater than the [[target_number]], [Alert] "Oops. Your guess was HIGH.".
```javascript
if(players_guess > target_number) {
   alert("Oops. Your guess was TOO HIGH.")
   number_of_guesses++;
var guesses_remaining = (10-number_of_guesses);
}
        
``` 
:ballot_box_with_check: [if] the player's [guess] is equal to the [target_number], _*[Alert]*_ them "Good job, [name]! You guessed my number in [number_of_guesses] guesses!".
```javascript
if(players_guess == target_number) {
   alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
   game_over = true;
}    
``` 
:ballot_box_with_check: [if] the players [number_of_guesses] is equal to 10 without guessing correctly, [alert] "Sorry. You didn't get my number. My number was [target]."
```javascript
 if(number_of_guesses >= 10) {
    alert("Sorry. You used up all your guesses and still didn't guess my number. My number was " + [target_number] +".");
    game_over = true;
 } 
``` 


##Cruising right along what is left of our program then?##
:white_medium_square:  Keep allowing the player to guess until they get it right, [or].

:white_medium_square:  [else] the player has made a choice that is not even a number and clearly does not want to continue to play.
` 

Currently, the player gets more than 10 guesses and there could be better brakes on this speed machine!!!  What stopping us before our player guesses correctly and our program becomes a loser?.  First We need to stop asking them after their 10th turn, [or] until they get the right answer, whichever comes first. The code to prompt for a guess is already in place, we just need to run it more than once and make sure we are counting the [number_of_guesses] correctly. We can use a loop to execute a segment of code repeatedly.  When you need one or more statements to be executed over and over, you place them inside a loop.  JavaScript offers a while loop as a counterpart to a for loop. A while loop repeats until the condition is true (that is, it loops over and over again while it's true and stops when the condition is false). 

A while loop consists of: 
    1. the word while, 
    2. a boolean expression (just like if or else statements),
    3. the code you want to repeat, and
    4. a terminator or something to stop it from running infinitely.
    
The code within the loop body repeats only while the condition is true.  What is tricky about the while loop and code below?   

Here's our conditional code again, updated to run within a while loop:
```javascript
while(!gameover){
    if(players_guess < target_number {
    alert("Oops. Your guess was LOW.")
    }
    if(players_guess > target_number {
    alert("Oops. Your guess was HIGH.")
    }
    if(players_guess = target_number {
    alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
    game_over = true;
    }
    if(number_of_guesses >= 10 {
    alert("Sorry. You didn't guess my number. My number was " + [target_number] +".");
    game_over = true;
    } 
    
    if(players_guess='NAN'){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }   
    if(players_guess < 0){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }
    if(players_guess > 100){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }
}    

```

Did you catch it?  If so give yourself a hug.  If you had to resort to asking your pet turtle pat yourself on the back anyway you were very resourceful and there is no shame in that

. 
#11.  Refactor#
Looking at the last 12 lines of code we are actually testing if the player entered input that is outside our range or typed in something that was "NAN" (not a number).  
```javascript
    if(players_guess='NAN'){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }   
    if(players_guess < 0){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }
    if(players_guess > 100){
       alert("It appears you don't want to play.  Thanks and Bye for now!")
       game_over=true
    }

```
In the development world we want our code to run super fast and having extra lines of code just slows us down.  The process of simplifying our code and making our program run faster is called __REFACTORING__.  In fact there is a programming management style called "Test Driven Development" TDD for short which is extremely popular in large development shops.  TDD is a three step looping process called RED, GREEN, REFACTOR and it works like this.  

1. RED:  TDD shops write all their code tests before they begin developing their programs code. 
2. GREEN After they write their code they run it against the tests until it is all free of bugs and passes all teh tests.
3. REFACTOR! which means revise and simplify.  At each refactor step the developers team up and they repeat the entire process all over again until they can't make their code any simpler or run any faster.  

We are here now in TDD Step 3. ...except we havent built any test scripts.  We can simplify the last 12 lines of code into one smaller conditional statement that is ran when all [else] fails.  The else command basically states if none of the ablove [if] conditional statements are true then do this. 

Lets refactor our code and add a variable.  We need a variable that can be set to determine if the user wants to quit playing the game.  We will call this variable [status]  

    ###Off Topic: ###
    normally when we create a variable we must give it a value.  This is the process called instantiation and refers to the very first value assigned to a variable upon its creation.  Just think you were instantiated when your parents named you when you were first born.  You see the very first time (instance) a variable is created we should give it a value.  When a pet turtle is hatched its parents probably instantiated it with the value "" or null.  That will work just fine until the time its owner comes along and renames it.  

When we instantiate the variable [status] below we are immediately giving it the name or the value returned by the user in the prompt command.  The condition is tested to see if the player types the word quit, or Quit, or QUIT.  [if] the condition is true the users choice is comfirmed and the game is ended.  If not the program executes the next block of code or hits the incrementer before repeating through the while loop all over again
###Lets see how much we can refactor our code:###
```javascript
else{
       var status = prompt("It appears you don't want to play.  Type Quit in the field below to end the game, or Play to continue")
       if(status == "quit"){
           alert("Bye for now " + name + "!")
           game_over=true
       } 
 ```
 
We used the == indicator from above to test if quit, and Quit, and Quit are all similar.  Remember this rule regarding equality in Javascript (and many other languages) because it is not completey normal to us at first:
 1.  = "assigns" the variable to a new value   example var name = "Dr. Jeanyes" does not test the condition it renames the variable and overwrites the old [name] value away.
 2.  == tests for "similarity" upper case or lower case are considered matches.
 3.  === tests for "exact match".
 
This is the code that will loop "while" our variable [game_over] is false.  The minute game_over = true, we want our code to stop and either declare a victory or offer our words of sorrow to our user who lost the game.  Notice how we run our final alerts just before we call an end to our game by changing game_over to true just like another a condition.  Wouldn't it be nice if we could use the same code over and over again (9 more times in fact) using game over as a condition in a "loop".

```javascript
    if(players_guess < target_number) {
        alert("Oops. Your guess was TOO LOW.");
        number_of_guesses++;
        var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess > target_number) {
        alert("Oops. Your guess was TOO HIGH.")
        number_of_guesses++;
        var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess == target_number) {
        alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
        game_over = true;
        }
        if(number_of_guesses >= 10) {
        alert("Sorry. You used up all your guesses and still didn't guess my number. My number was " + [target_number] +".");
        game_over = true;
        } 
    }
    else{
       var status = prompt("It appears you don't want to play.  Type Quit in the field below to end the game, or Play to continue")
       if(status == "quit"){
           alert("Bye for now " + name + "!")
           game_over=true
       } 
```
But how will we give the player a second guess?  Well first remember we only want to give them 10 guesses. We already moved our incrementer code [umber_of_guesses++] inside the while loop.  The incrementer if you remember adds 1 to the variable [number_of_guesses] on each turn. This is so we don't forget how many guesses the player has taken and if they run out of turns we can politely tell them they didn't win. The condition [if(number_of_guesses >= 10)] will not allow the player more than 10 guesses.  

So you still want to know how we can give them a second chance if they aren't Dr Jeanyes' and cannot guess our number on the first try?  Ok you probably know by now we need another looping function but just how will that work exactly?

Javascript offers "for" loops which we have used before in our minecraft canvas builder game, Javascript also offers "while" or "Do While" loops, and they work like this. 

We are going to use a simple while loop to generate up to ten player guesses per game using our incrementer [number_of_guesses++], and our game_over to tell us when the game is won or lost.  Previously we created all the necessary code to test most of our players possible choices.  If it didn't meet a certain condition we had no other condition but to end the game.  Now we can loop back and continue to play the next round!   Believe it or not building the game so it would not run infinitely was the hard part.  Repeating it is the easy part.

"While" a condition is true, "do" this"  
```javascript
while(condition is true) {
    run this code
}
```

It is actually that simple only where the example above says "run this code" we want all of our conditions to appear there instead.  Technically what we are doing is wrapping all of our conditional statements inside one big condition.  Large programs can have thousands of lines of code enclosed inside; conditions, functions, for loops or a while loops to name a few.  The most important thing to remember is the curly braces {}.  They tell Javascript when to start and stop functions and conditional statements.  When they stop Javascript jumps outside teh curly braces to the next line of code until the parent condition is met then steps back outside the while loop to end the program.  Curly braces {} provide guidance like navigation tools to JavaSccipt and other programmers who are reading your code.  If one is missing or is out of place your program will either not run at all, end early, or continue to go on forever.  Best practices are to indent your code and line the closing curly brace } up with the conditional statement [if], [else], [else if] that owns the opening curly brace {.  See if you can spot all the opening and closing braces in our code below. 
   

```javascript
var game_over = false;
var number_of_guesses = 0;
var guesses_remaining = 10;

var target_number = Math.floor((Math.random()*100)+1);

var name = prompt("Welcome to 'Guess My Number!  What's your name? ");
alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to proceed.  You may type 'quit' or 'no' anytime in the future to leave the game");

while(!game_over){
    var players_guess = prompt("You have" + " " + guesses_remaining + " " + "guesses left " + name + ".  Guess what my number is!");
    if(players_guess>0 || players_guess<101){if(players_guess < target_number) 
    {alert("Oops. Your guess was TOO LOW."); number_of_guesses++; var guesses_remaining = (10-number_of_guesses);}
    if(players_guess > target_number) {
    alert("Oops. Your guess was TOO HIGH.")
            number_of_guesses++; var guesses_remaining = (10-number_of_guesses);}
        if(players_guess == target_number) {
    alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
            game_over = true;}
    if(number_of_guesses >= 10) {alert("Sorry. You used up all your guesses and still didn't guess my number. My number was " + [target_number] +".");
            game_over = true;} 
    }
    else{
            var status = prompt("It appears you don't want to play.  Type Quit in the field below to end the game, or Play to continue")
            if(status == "quit"){
                alert("Bye for now " + name + "!")
                game_over=true
    }}
```


Yuck! that was horible to read.   

Here's our well written and completed GuessMyNumber.js code. Notice how much easier it is to read when indents are used and all the curly braces } are line up in a well written fashion?  This is considered "Best Practice"  you will have some happy co-workers if you use "Best Practices" when codeing.
```javascript
var game_over = false;
var number_of_guesses = 0;
var guesses_remaining = 10;

var target_number = Math.floor((Math.random()*100)+1);

var name = prompt("Welcome to 'Guess My Number!  What's your name? ");
alert("If you would like to play, then step on up " + name + ".  I have picked a number from 1 to 100.  See if you can guess my number in less than 10 tries!  Click Ok to proceed.  You may type 'quit' or 'no' anytime in the future to leave the game");

while(!game_over){
    var players_guess = prompt("You have" + " " + guesses_remaining + " " + "guesses left " + name + ".  Guess what my number is!");
    if(players_guess>0 || players_guess<101){
        if(players_guess < target_number) {
            alert("Oops. Your guess was TOO LOW.");
            number_of_guesses++;
            var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess > target_number) {
            alert("Oops. Your guess was TOO HIGH.")
            number_of_guesses++;
            var guesses_remaining = (10-number_of_guesses);
        }
        if(players_guess == target_number) {
            alert("Good job, " + [name] + "! You guessed my number in " + number_of_guesses + " guesses!");
            game_over = true;
        }
        if(number_of_guesses >= 10) {
            alert("Sorry. You used up all your guesses and still didn't guess my number. My number was " + [target_number] +".");
            game_over = true;
        } 
    }
    else{
            var status = prompt("It appears you don't want to play.  Type Quit in the field below to end the game, or Play to continue")
            if(status == "quit"){
                alert("Bye for now " + name + "!")
                game_over=true;
            }
    }
}


Let's test our game!
Using variables, strings, method calls, concatenation, conditionals, equality and other comparisons, !Bang, Test Driven Design, and even loops, you have written a complete game in Javascript! Better yet, it took less than 40 lines of code thanks to yur refactoring skills! Pat yourself on the back! #You did it!!!#

#We've been asked to build a game!#

In order to take our game live we will need to first determine our "MVP".   In the development world the "MVP" is typically defined by our client as the bare minimum requirements our program needs to have in order to pass.  We call it the MVP because it is our 
    __Minimum Viable Product__.  

I met with our customer and listened intently to put together this list of requirements for you. If this sounds impossible, don't worry; it's easy when you break down the code into small manageable tasks.  I know you can handle it!  Now let's look at what we'll need to do:

:white_medium_square: [Prompt] the player to enter their [name].

:white_medium_square: Use their [name] to print a greeting.

:white_medium_square: Generate a random number from 1 to 100, and store it as a [target_number] for the player to guess.


:white_medium_square: Before each guess, _*[Prompt]*_ the player:

  1. let them know how many guesses (out of 10) they have left.
  2. to make a guess as to what the target number is.
        

:white_medium_square: [If] the player's guess is less than the target number, [Alert] "Oops. Your guess was LOW."

:white_medium_square: [else] the player's [guess] is greater than the [target number], [Alert] "Oops. Your guess was HIGH.".

:white_medium_square: [else] the player's [guess] is equal to the [target_number], _*[Alert]*_ them "Good job, [name]! You guessed my number in [number of guesses] guesses!".

:white_medium_square: Keep track of the [number_of_guesses] the player has made.

:white_medium_square: Keep allowing the player to guess until they get it right, [or].

:white_medium_square: [If] the players [number_of-guesses] is equal to 10 without guessing correctly, [Alert] "Sorry. You didn't get my number. My number was [target]."

Before we jump into the code lets pause for a minute to think about how our users will enter information (user Interface) and define some variables.

from the MVP meeting with our customer we listed the requirements MVP above.  I have highlited some of the variables, if statements, prompts, incrementers, and alerts above can you spot them?

Variables: | type   
---------------|---------        
name |  string               
target_number | number            
players_guess | number      

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
Too High | if players_guess > target number
Victory | if players_guess = target number
Gameover | if number_of_guesses >=10

We should have already set up our environment when cloning from Github.  Just to be sure we have everything in place check to see if you have the following files in your C9.io workspace.
1. Readme.md 
2. GuessMyNumber.js

####Lets get Started!

Our first requirement is to greet the user by name and ask them to guess a number between 1 and 100. To accomplish that, we'll need to write a script that gets input from the user, stores that input, and then uses that stored value to create some output. We can do all this in just a few lines of JavaScript code:
```javascript

var name = prompt("Welcome to 'Guess My Number!  What's your name? ")
var player_guess = prompt("Welcome " +name +" See if you can guess my number")

```

That was easy!  When the game is loaded, our user will be asked to enter his/her name.  This is the first of two jobs belonging to "prompt". The "prompt" method reads a line from standard input (characters typed in the terminal window). When you call prompt, it causes the program to halt until the user types their name and presses the Enter key. .  The second job is to store the players name as our "name" variable.  So you see "prompt" returns or saves the user's text to the program as a text string which we assigned to the variable "name" by typing "var name = prompt" 

The second prompt "var player_guess = prompt" essentially works the same way but it asks the player to choose a number the computer first stores that number before our code compares the players number to the computers number.



So the player types his/her name and hits the Enter/Return key, they will then see a second message that welcomes them by name and starts the game.  Well that sounds like what we want but hmm... something is missing.  What if they can't play because they have chores or homework to do?  We should ask them first if they want to play "Guess My Number!" and tell them a little bit about the game The MVP list said the computer would choose between 1 and 100.  The user can answer yes or no to play or exit. or perhaps if they clicked a box that returns ok to play and X to exit the game.  How will we handle that?  

These decisions come up all the time in software development that's the fun part... we get to make __Executive Decisions!__  But wait, asking the user if they want to play is not in our MVP list from above.  True, but it really helps the program if our users are informed on what to do or given the opportunity to stop playing right?  Besides the better we make the program the more work we will be awarded and the more we can charge for our work because we are __Awesome!__.  Whenever we have an opportunity to improve the user experience we should try our best. Unless of course those efforts will cause us to turn our work in late or those efforts will cost us a lot of extra money which we cannot afford to pay.  Its a good opportunity to ask your fellow developers what they would do if you don't know.  Developers are always willing to share their ideas.  

So here is our first opportunity to make an impression on our customer.  You can be the one who decides what our greeting should be, maybe ask a family member or your neighbor?  Below is an example for you to start with.  You can paste the code just as it is right into your javascript file or you can change the words inside the "  ".  Be sure to double check your spelling we really need to impress our client and our players.  Especially since this is an added feature!
```javascript

  var name = prompt("Hello, what's your name? ")
  alert("Do you want to play 'Guess My Number!' " +name + "?")
  var player_guess = prompt("Welcome to 'Guess My Number! " +name + " I have chosen a number between 1 and 100.  See if you can guess it!")

```
###Wow the first two check boxes are off our list! 
####:ballot_box_with_check: [Prompt] the player to enter their [name].
####:ballot_box_with_check: Use their [name] to print a greeting.

####On to the next step.

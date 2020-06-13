# Getting Started

> To create TicTakToe you need functions to display the board, take in a user input and change the board accordingly
> Here are some functions you are going to have to understand in order to build the game
> It is easier if you divide the problem into smaller sub-problems

* Display the board - displayBoard()

* Ask user for the position of the board they want to change - positionChoice()

* Replace the old choice with the new user choice - replaceChoice()

* Ask user if they wish to continue playing - keepPlaying()

> There are no order but these are necessary function in order to build any program that can display a board, take in user's choice, and
> replace board with the new choice. Once the game is over you can ask if they want to play again.

## Display the board
* TicTacToe requires 3x3 unit board

###### How?

You already know how to create one line using a print() statement.
```python
print("-----this is the first line----")
```  
We can use multiple print() to create a board
```python
print("1|2|3")
print("4|5|6")
print("7|8|9")
```
> Just like that we have created a 3x3 board.
> you can have your own variations 
```python 
print("1|2|3")
print("------")
print("4|5|6")
print("------")
print("7|8|9")
```

## positionChoice()

* Get a user's input and determine if it's a valid input

###### How?

You already know how ask for user's input
```python
userinput = input("Please enter any number between 1-3")
```
What if user enter an invalid choice? Such as "7" or "Abracadabra"

You can use a while loop to keep asking user until they enter a correct value
```python
###You want user's input to be a integer between 1-3
###   This is equivalent of checking if something is in [1,2,3]
###   userinput = input("is string by default")
###   userinput.isdigit() will check if the user input is a digit
###   int(userinput) will cast the input into an integer

#Start with an initial false value
userinput = "false"

#Begin the while loop
## while the user doesn't enter a number or if the number is out of range

while not (choice.isdigit() or withinRange):
      
      choice = input("Plese enter a valid number: ")
        
      # Digit Check
      if choice.isdigit():
          print("Sorry that is not valid")
        
      # Range Check
      if choice.isdigit():
          if int(choice) in acceptableRange:
              withinRange = True
          else:
              False
                
return int(choice)


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
But you can't edit this board because it doesn't have indices
instead you can create a list and use indexing to create a more efficient board
```python
#first create a list
board = ['-', '-', '-', '-', '-', '-', '-', '-', '-',]

#now create your board by printing each element
print(board[0]+'|'+board[1]+'|'+board[2])
##this will print -|-|-

#In order to change values, you can do so by, board[i] = ' '
board[0] = 'X'
board[1] = 'O'
##now it will print X|O|-

#To print the whole board you can do something like this
print(board[0]+'|'+board[1]+'|'+board[2])
print(board[3]+'|'+board[4]+'|'+board[5])
print(board[6]+'|'+board[7]+'|'+board[8])
##this will print
X|O|-
-|-|-
-|-|-
```

## Accepting user's input
* Get a user's input and determine if it's a valid input

###### How?

You already know how ask for user's input
```python
userinput = input("Please enter any number between 1-3")
```
What if user enter an invalid choice? Such as "7" or "Abracadabra"

You can use a while loop to keep asking user until they enter a correct value
```python
def userChoice():
      ###You want user's input to be a integer between 1-3
      ###   This is equivalent of checking if something is in [1,2,3]
      ###   userinput = input("is string by default")
      ###   userinput.isdigit() will check if the user input is a digit
      ###   int(userinput) will cast the input into an integer
      ###   check if int(userinput) is within the acceptable range [1,2,3]

      #This is the acceptable range anything else is invalid
      withinRange = [1,2,3]

      #Start with an initial false value
      userinput = "false"

      #Begin the while loop
      ## while the user doesn't enter a number or if the number is out of range
      while not (userinput.isdigit() or withinRange):

          userinput = input("Plese enter a valid number: ")

         # Digit Check
         if userinput.isdigit():
                print("Sorry that is not valid")

          # Range Check
           if userinput.isdigit():
                if int(userinpput) in acceptableRange:
                    withinRange = True
                else:
                  #Exit while loop
                  False

      return int(userinput)
```

## Insert user's choice on the board
* If the user has inserted a valid input, you have to change the board or else you'll be displaying the same empty board

###### How?
Our board is a list, and lists have indices
```python
def replacementChoice(gameList, position):

    userPlacement = input("Type a string to place at position: ")

    gameList[position] = userPlacement

    return gameList
```

## Ask user if they wish to play again
* Ask the user if they want play again, 'Y' for yes and 'N' for no

###### How?
This is almost same as asking for user's user's input
Ask for the user's input, and check if its a valid input ('Y' or 'N').

```python
def keepPlaying():

    choice = 'wrong'

    while choice not in ['Y', 'N']:

        choice = input("Keep Playing (Y or N): ")

        if choice not in ['Y', 'N']:

            print('Sorry, invalid choice')

    if choice == 'Y':
        return True
    else:
        return False
```

## Put them together
```python
playAgain = True
board = [0,1,2]

while playAgain:
    displayGame(board)
    position = userChoice()
    board = replacementChoice(board, position)
    displayGame(gameList)
    gameon = keepPlaying()
```

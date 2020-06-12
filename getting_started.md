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

> how?

* You already know how to create one line using a print() statement.
```python
print("-----this is the first line----")
```  
* We can use multiple print() to create a board
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

# This is the game code

```python
import random

#Display the board
def displayBoard(board):
    print(board[0]+ " | " + board[1]+" | " + board[2])
    print(board[3]+ " | " + board[4]+" | " + board[5])
    print(board[6]+ " | " + board[7]+" | " + board[8])    

#Ask player one to choose 'X' or 'O', player two gets the other one by default

def playerInput():
    '''
    OUTPUT: (player1 marker, player2 marker)
    '''
    
    marker = ""
    
    #Keep asking player 1 to choose X or O
    while marker != 'X' and marker != 'O':
        marker = input("Player 1 choose X or O: ")
           
    if marker == 'X':
        return ('X','O')
    else:
        return ('O','X')
        

#Mark the board with the proper player's mark
def placeMarker(board, marker, position):
    board[position] = marker
    

#Check all winning cases
def winCheck(board, marker):
    
    #Horizontal check
    if board[0]== marker and board[1]== marker and board[2]==marker:
        return True
    elif board[3]== marker and board[4]== marker and board[5]==marker:
        return True
    elif board[6]== marker and board[7]== marker and board[8]==marker:
        return True
    
    #Vertical check
    elif board[0]== marker and board[3]== marker and board[6]==marker:
        return True
    elif board[1]== marker and board[4]== marker and board[7]==marker:
        return True
    elif board[2]== marker and board[5]== marker and board[8]==marker:
        return True
    
    #Diagnal check
    elif board[0]== marker and board[4]== marker and board[8]==marker:
        return True
    elif board[2]== marker and board[4]== marker and board[6]==marker:
        return True
    else:
        return False
    

#Randomly chooses who goes first        
def chooseFirst():
    
    coinFlip = random.randint(0,1000)
    if coinFlip%2 == 0:
        return 'Player 1'
    else:
        return 'Player 2' 


#Check if the the position user asked for is empty
def spaceCheck(board, position):
    
    if board[position] == '-':
        return True
    else:
        return False

#Check if the entire board is filled. Indirectly checking for tie
def fullBoardCheck(board):
    
    for i in range(0,9):
        if spaceCheck(board,i):
            return False
        
    return True
    
#Ask player to place a mark on the board            
def playerChoice(board):
    
    nextChoice = ""
    
    while nextChoice not in '0 1 2 3 4 5 6 7 8 '.split() or not spaceCheck(board, int(nextChoice)):
        
        nextChoice = input("Enter the location you want to mark: ")
        
    return nextChoice
    
#Ask player if they want to play again    
def replay():
        
    choice = ''
    
    while choice not in ['Y', 'N', 'y', 'n']:
        
        choice = input("Keep Playing (Y or N): ")
        
        if choice not in ['Y', 'N', 'y', 'n']:
            
            print('Sorry, invalid choice')
    
    if choice == 'Y':
        return True
    else:
        return False
        
#The actual game
print("Welcome to TicTacToe")

while True:
    #play the game

    ## SET UP: board, whos first, chose marker
    gameOn = True
    board = ['-', '-', '-',
         '-', '-', '-',
         '-', '-', '-']
    
    player1Marker,player2Marker = playerInput()
    
    turn = chooseFirst()
    print(turn + " will go first")
    
    playGame = input('Ready to play? Y or N?')
    if playGame == "Y":
        gameOn = True
    else:
        gameOn = False
    
    
    ## game play
    while gameOn:
        
        ###player1 turn
        if turn == 'Player 1':

            #show the board
            displayBoard(board)
            
            # choose a position
            position = int(playerChoice(board))
            # place the marker on the position 
            placeMarker(board, player1Marker, position)
            #check if they won 
            if winCheck(board, player1Marker):
                displayBoard(board)
                print("Player 1 has won")
                gameOn = False
            # or check for tie
            else:
                if fullBoardCheck(board):
                    displayBoard(board)
                    print("Tie")
                    gameOn = False
                else:
                    turn = 'Player 2'
       
        ###player2 turn
        if turn == 'Player 2':

            #show the board
            displayBoard(board)
            
            # choose a position
            position = int(playerChoice(board))
            # place the marker on the position 
            placeMarker(board, player2Marker, position)
            #check if they won 
            if winCheck(board, player2Marker):
                displayBoard(board)
                print("Player 2 has won")
                gameOn = False
            # or check for tie
            else:
                if fullBoardCheck(board):
                    displayBoard(board)
                    print("Tie")
                    gameOn = False
                else:
                    turn = 'Player 1'

    if not replay():
        break
    #reak out of the while loop on replay()
    ```
        

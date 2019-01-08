from random import randint
ship_dict = {}
board = []
while True:
    try:
        board_size = int(input("Enter a board size (1-9): "))
        if board_size > 0 and board_size < 9:
            break
        raise ValueError   
    except(ValueError):
        print("Please enter a valid number")

for x in range(board_size):
    board.append(["O"] * board_size)
def print_board(board):
    for row in board:
        print(" ".join(row))
print_board(board)
def random_row(board):
    return randint(1, len(board) )
def random_col(board):
    return randint(1, len(board[0]) )
while True:
    try:
        num_ships = int(input("Enter number of ships (1-5): "))
        if num_ships > 0 and num_ships < 6:
            break
        raise ValueError
    except(ValueError):
        print("Please enter a valid number")
for x in range(num_ships + 1):
    if len(ship_dict) != num_ships:
        #Add conditions so that values are not replaced, but added
        #such that it meets the total requirement of # of ships needed
        ship_dict[random_row(board)] = random_col(board)
for key in ship_dict:
    print(key, ship_dict[key])
#Turn Based
"""while True:
    try:
        num_turns = int(input("Enter # of turns: "))
        break
    except(ValueError):
        print("Enter a valid number")
for turn in range(num_turns):"""
#Until all ships are destroyed
while len(ship_dict) != 0:
    while True:
        try:
            guess_row = int(input("Guess Row: "))
            if guess_row > 0 and guess_row < board_size + 1:
                break
            raise ValueError
        except(ValueError):
            print("Please enter a valid number")
    while True:
        try:
            guess_col = int(input("Guess Col: "))
            if guess_col > 0 and guess_col < board_size + 1:
                break
            raise ValueError
        except(ValueError):
            print("Please enter a valid number")     
    if guess_row in ship_dict and ship_dict[guess_row] == guess_col:
        del ship_dict[guess_row]
        print("Congratulations! You sunk my battleship!")
        board[guess_row-1][guess_col-1] = "|"
    else:
        if (guess_row < 0 or guess_row > board_size) or \
           (guess_col < 0 or guess_col > board_size):
            print("Oops, that's not even in the ocean.")
        elif board[guess_row-1][guess_col-1] == "X" or \
             board[guess_row-1][guess_col-1] == "|":
            print("You guessed that one already.")
        else:
            print("You missed my battleship!")
            board[guess_row-1][guess_col-1] = "X"
            #if turn == 3:
                #print("Game Over")
    #print(turn + 1)
    print_board(board)

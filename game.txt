cells = list("         ")
end_game = False
board = []
def board_update():
    global board
    row_1 = [cells[0], cells[1], cells[2]]
    row_2 = [cells[3], cells[4], cells[5]]
    row_3 = [cells[6], cells[7], cells[8]]

    col_1 = [cells[0], cells[3], cells[6]]
    col_2 = [cells[1], cells[4], cells[7]]
    col_3 = [cells[2], cells[5], cells[8]]

    dia_1 = [cells[0], cells[4], cells[8]]
    dia_2 = [cells[2], cells[4], cells[6]]

    board = [row_1, row_2, row_3, col_1, col_2, col_3, dia_1, dia_2]



def board_state():
    print(f"""  1  2  3
 ---------
1| {cells[0]} {cells[1]} {cells[2]} |
2| {cells[3]} {cells[4]} {cells[5]} |
3| {cells[6]} {cells[7]} {cells[8]} |
 ---------""")

def check_board():
    global board
    global end_game
    x_count = 0
    o_count = 0

    for n in cells:
        if n == "X":
            x_count += 1
        elif n == "O":
            o_count += 1
    if (x_count + o_count) == 9 and end_game == False:
        print("Draw")
        end_game = True
    for line in board:
        if line == ['O', 'O', 'O']:
            print("O wins")
            end_game = True
        elif line == ['X', 'X', 'X']:
            end_game = True
            print("X wins")



numbers = list("1234567890")

board_state()

turn = 1
while not end_game:
    move = input("Enter the coordinates:")
    if move == "1 1":
        if cells[0] == " ":
            if turn % 2 != 0:
                cells[0] = "X"
            else:
                cells[0] = "O"

            board_state()
            board_update()
            check_board()

            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "1 2":
        if cells[1] == " ":
            if turn % 2 != 0:
                cells[1] = "X"
            else:
                cells[1] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "1 3":
        if cells[2] == " ":
            if turn % 2 != 0:
                cells[2] = "X"
            else:
                cells[2] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "2 1":
        if cells[3] == " ":
            if turn % 2 != 0:
                cells[3] = "X"
            else:
                cells[3] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "2 2":
        if cells[4] == " ":
            if turn % 2 != 0:
                cells[4] = "X"
            else:
                cells[4] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "2 3":
        if cells[5] == " ":
            if turn % 2 != 0:
                cells[5] = "X"
            else:
                cells[5] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "3 1":
        if cells[6] == " ":
            if turn % 2 != 0:
                cells[6] = "X"
            else:
                cells[6] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "3 2":
        if cells[7] == " ":
            if turn % 2 != 0:
                cells[7] = "X"
            else:
                cells[7] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif move == "3 3":
        if cells[8] == " ":
            if turn % 2 != 0:
                cells[8] = "X"
            else:
                cells[8] = "O"
            board_state()
            board_update()
            check_board()
            if end_game:
                break
            else:
                turn += 1
                continue
        else:
            print("This cell is occupied! Choose another one!")
    elif len(move.split()) == 2:
        if move.split()[0] and move.split()[1] in numbers:
            print("Coordinates should be from 1 to 3!")
        else:
            print("You should enter numbers!")
    else:
        print("You should enter numbers!")

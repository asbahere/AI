board = [[" " for _ in range(3)] for _ in range(3)]

def draw_board():
    print("  0 1 2")
    for i, row in enumerate(board):
        print(i, *row)

def get_move(player):
    while True:
        try:
            row = int(input("Enter row for player {}: ".format(player)))
            col = int(input("Enter column for player {}: ".format(player)))
            if row in range(3) and col in range(3) and board[row][col] == " ":
                board[row][col] = player
                return
            else:
                print("Invalid move, try again.")
        except ValueError:
            print("Invalid input, try again.")

def has_won(player):
    # check rows
    for row in board:
        if row == [player, player, player]:
            return True
    # check columns
    for col in range(3):
        if board[0][col] == player and board[1][col] == player and board[2][col] == player:
            return True
    # check diagonals
    if board[0][0] == player and board[1][1] == player and board[2][2] == player:
        return True
    if board[0][2] == player and board[1][1] == player and board[2][0] == player:
        return True
    return False

def main():
    draw_board()
    while True:
        get_move("X")
        draw_board()
        if has_won("X"):
            print("Player X has won!")
            break
        get_move("O")
        draw_board()
        if has_won("O"):
            print("Player O has won!")
            break

main()

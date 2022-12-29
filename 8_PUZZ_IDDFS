from typing import List

def iddfs(board: List[List[int]]) -> bool:
    def dfs(board, depth, max_depth, moves):
        if depth > max_depth:
            return False
        
        if board == [[1, 2, 3], [4, 5, 6], [7, 8, 0]]:
            print(f'Solution found in {len(moves)} moves: {moves}')
            return True
        
        i, j = None, None
        for row in range(3):
            for col in range(3):
                if board[row][col] == 0:
                    i, j = row, col
                    break
        
        for row, col in [(i+1, j), (i-1, j), (i, j+1), (i, j-1)]:
            if 0 <= row < 3 and 0 <= col < 3:
                new_board = [r[:] for r in board]
                new_board[i][j], new_board[row][col] = new_board[row][col], new_board[i][j]
                if dfs(new_board, depth+1, max_depth, moves + [new_board]):
                    return True
        return False
    
    for depth in range(100):
        if dfs(board, 0, depth, []):
            return True
    return False

# Test the function
board = [[1, 2, 3], [4, 5, 6], [7, 0, 8]]
print(iddfs(board))  # Output: True

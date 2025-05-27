import random

def create_board():
    # Create a dictionary to represent snakes and ladders
    # key is the starting position, value is the ending position
    snakes_and_ladders = {
        2: 38, 7: 14, 8: 31, 15: 26, 21: 42, 28: 84, 36: 44, 51: 67, 71: 91, 78: 98, 87: 94,
        16: 6, 46: 25, 49: 11, 62: 19, 64: 60, 74: 53, 89: 68, 92: 88, 95: 75, 99: 80
    }
    return snakes_and_ladders

def roll_dice():
    return random.randint(1, 6)

def move_player(player, current_pos, dice_roll, board):
    new_pos = current_pos + dice_roll
    
    if new_pos > 100:
        print(f"{player} cannot move. Needs exact roll to reach 100.")
        return current_pos
    
    print(f"{player} rolled a {dice_roll} and moved from {current_pos} to {new_pos}")
    
    # Check for snake or ladder
    if new_pos in board:
        if new_pos < board[new_pos]:
            print(f"Wow! Ladder from {new_pos} to {board[new_pos]}")
        else:
            print(f"Oops! Snake from {new_pos} to {board[new_pos]}")
        new_pos = board[new_pos]
    
    return new_pos

def play_game():
    board = create_board()
    players = {"Player 1": 0, "Player 2": 0}
    current_player = "Player 1"
    
    print("Welcome to Snake and Ladder Game!")
    print("Rules:")
    print("- Each player takes turns to roll a dice")
    print("- Move forward the number of spaces shown on the dice")
    print("- If you land on a ladder, climb up")
    print("- If you land on a snake, slide down")
    print("- First to reach exactly 100 wins!")
    
    while True:
        input(f"{current_player}'s turn. Press Enter to roll the dice...")
        dice_roll = roll_dice()
        
        players[current_player] = move_player(
            current_player, players[current_player], dice_roll, board
        )
        
        if players[current_player] == 100:
            print(f"\n{current_player} wins!")
            break
        
        # Switch players
        current_player = "Player 2" if current_player == "Player 1" else "Player 1"
        
        print(f"\nCurrent positions:")
        print(f"Player 1: {players['Player 1']}")
        print(f"Player 2: {players['Player 2']}\n")

if __name__ == "__main__":
    play_game()

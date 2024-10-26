# Tic-Tac-Toe Game

The AI in this Tic-Tac-Toe game uses the **minimax algorithm** to make intelligent choices. Here's a more approachable breakdown of how it functions and what goes on behind the scenes:

## 1. Understanding the AI's Thinking (Minimax Algorithm)
When playing Tic-Tac-Toe, the AI anticipates every move it might make and then imagines your (the opponent's) reaction. To select the optimal move, the AI employs the **minimax algorithm**, which functions similarly to a "look-ahead strategy" by forecasting the results of each potential move. It attempts to block any move you could make because it believes you're playing at your best as well.

## 2. Two Approaches: Maximizing and Minimizing
- **Maximizing (When the AI is "X")**: Since the AI wants to win, it searches for strategies that will help it win or at the very least keep it from losing.
- **Minimizing (When the AI is "O")**: The AI's goal in this situation is to keep the opponent from winning. The AI searches for moves that reduce the opponent's odds of success since it believes the opponent ("X") is trying to win.

## 3. How the Game Ends (Terminal States)
The AI knows the game is over when:
- Someone wins (either "X" or "O").
- All spaces on the board are filled (a tie).
The AI checks for these conditions at every step using the `terminal()` function, which tells it when to stop looking for more moves.

## 4. Scoring the Game (Utility Function)
To decide if a move is good, the AI uses a **score**:
- `1` means "X" wins.
- `-1` means "O" wins.
- `0` means it’s a tie.
The AI uses this scoring system to decide which move is best.

## 5. How the AI Decides What to Do (Minimax Flow)
Here’s a simplified look at the AI’s decision process:
1. The AI checks the board to see whose turn it is.
2. It looks at all possible moves (empty spots on the board) and tries them one by one.
3. After imagining making each move, the AI simulates the rest of the game to see how it would play out.
4. It evaluates all these possibilities and picks the move that leads to the best outcome—either winning or, if it can’t win, at least not losing.

## 6. Making the Process Faster (Alpha-Beta Pruning)
The AI uses a trick called **alpha-beta pruning** to speed up its decision-making. This means it doesn’t waste time checking moves that are clearly worse than others. For example, if the AI already found a great move, it won’t keep looking at moves that can’t possibly be better.

## 7. How the AI Takes Its Turn
- If it’s the AI’s turn, it uses the `minimax()` function to figure out the best move.
- Once the AI picks a move, it updates the board, and the game continues.
- This process keeps going until the game is over (someone wins or it’s a tie).

## AI Concepts at Play
- **Strategic Decision-Making**: The AI always makes the best possible move based on the current board, assuming both players are making their best moves.
- **Recursion**: The AI looks ahead, predicting all future moves, like a chain of "what if" scenarios.
- **Game Theory**: The AI uses principles from **game theory**, where both players try to outsmart each other by playing optimally.
- **Efficiency (Alpha-Beta Pruning)**: By cutting off unnecessary calculations, the AI makes its decisions faster, without compromising on quality.

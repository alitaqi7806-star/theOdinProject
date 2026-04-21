
### Console-First Development Cheat Sheet  
**(Focus: Get the game working in the console before touching the DOM)**

| Priority | Task | Why It’s Important | Recommended Approach |
|----------|------|--------------------|----------------------|
| **1**    | Build the core game logic first | DOM and UI will distract you and make debugging much harder | Ignore HTML/CSS completely for now |
| **2**    | Create the three main modules | Keeps responsibilities separated and code clean | Gameboard, GameController, Player |
| **3**    | Implement win condition checking | Must detect all 8 possible winning combinations | Horizontal, vertical, and diagonal |
| **4**    | Implement draw (tie) detection | Game must end when board is full with no winner | Check if board is full and no winner |
| **5**    | Test everything manually in console | Verify logic works before adding UI | Call functions directly with arguments |

### Core Modules & Responsibilities (Console Phase)

| Module              | Responsibility | Key Methods to Implement |
|---------------------|----------------|--------------------------|
| **Gameboard**       | Store board state and basic operations | `getBoard()`, `placeMark(index, mark)`, `resetBoard()`, `isFull()` |
| **Player**          | Represent a player | Factory function returning `{ name, mark }` |
| **GameController**  | Manage game flow and rules | `startNewGame()`, `playTurn(index)`, `getCurrentPlayer()`, `checkWinner()`, `checkDraw()`, `isGameOver()` |

### Win Condition Checklist (All 8 Wins)

| Type          | Winning Combinations (indices) |
|---------------|--------------------------------|
| Rows          | [0,1,2], [3,4,5], [6,7,8] |
| Columns       | [0,3,6], [1,4,7], [2,5,8] |
| Diagonals     | [0,4,8], [2,4,6] |

**Tip**: Create a `winningCombinations` array and loop through it in `checkWinner()`.

### Console-First Workflow (Recommended Order)

| Step | What to Build | How to Test |
|------|---------------|-------------|
| 1    | `Gameboard` module + `placeMark()` | `Gameboard.placeMark(4, 'X')`; `console.table(Gameboard.getBoard())` |
| 2    | `Player` factory | Create two players and log them |
| 3    | `GameController` with turn management | `GameController.playTurn(0)` and check current player |
| 4    | Win checking logic | Manually place marks to test all 8 winning lines |
| 5    | Draw checking logic | Fill board with no winner and verify draw detection |
| 6    | `isGameOver()` | Return true when someone wins or it's a draw |

### Example Console Testing Commands

```js
GameController.startNewGame("Alice", "Bob");

GameController.playTurn(0);   // X places in top-left
GameController.playTurn(3);   // O places in middle-left
GameController.playTurn(1);
// ... continue until win or draw

console.log(GameController.getCurrentPlayer().name);
console.log(Gameboard.getBoard());
```

### Important Rules for This Stage

| Rule | Explanation |
|------|-----------|
| **No DOM yet** | Do not touch `index.html` or create any DOM elements |
| **No user input** | Manually call functions with numbers (0–8) |
| **Test thoroughly** | Try to break the game on purpose (placing in occupied cells, etc.) |
| **Keep it simple** | Focus only on logic. UI comes later |
| **Use console heavily** | `console.table()`, `console.log()`, and manual function calls are your best friends |

### Success Criteria (Before Moving to UI)

- You can start a new game
- Players can take turns correctly
- All 8 winning combinations are detected
- Draw condition is correctly identified
- Game stops when over (no more moves allowed)
- You can reset the game and play again

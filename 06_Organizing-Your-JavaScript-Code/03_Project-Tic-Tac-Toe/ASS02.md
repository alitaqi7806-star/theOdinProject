

### Tic-Tac-Toe – "Where Should the Logic Live?" Cheat Sheet

| Logic / Responsibility                  | Recommended Home          | Why It Belongs Here |
|-----------------------------------------|---------------------------|---------------------|
| Storing the 3x3 board state             | **Gameboard**             | The board is the core data structure |
| Placing a mark (X or O) on the board    | **Gameboard**             | Only the board should modify its own state |
| Checking if a cell is empty             | **Gameboard**             | Related to board state |
| Resetting / clearing the board          | **Gameboard**             | Board management |
| Creating a new player                   | **Player** factory        | Player-specific data and behavior |
| Getting player name or mark             | **Player**                | Player owns its own information |
| Managing whose turn it is               | **GameController**        | Controls the flow of the game |
| Switching turns                         | **GameController**        | Part of game flow |
| Checking for a winner                   | **GameController**        | Game rule, not board or player |
| Checking for a draw                     | **GameController**        | Game rule |
| Determining if the game is over         | **GameController**        | Game state management |
| Rendering the board to the screen       | **DisplayController**     | Purely UI / presentation logic |
| Handling user clicks on cells           | **DisplayController**     | UI interaction |
| Showing messages (win, draw, etc.)      | **DisplayController**     | UI responsibility |
| Starting a new game                     | **GameController**        | Orchestrates reset of board + players |
| Validating a move (cell already taken)  | **Gameboard** or **GameController** | Can be in either, but Gameboard is cleaner |

### Recommended Module Responsibilities

| Module                | Owns These Responsibilities |
|-----------------------|-----------------------------|
| **Gameboard**         | Board array, placing marks, checking cell status, resetting board |
| **Player**            | Name, mark (X/O), any player-specific methods |
| **GameController**    | Current player, turn management, win/draw checking, game state, starting new game |
| **DisplayController** | Rendering the board, handling clicks, showing messages, UI updates |

### Decision Framework (Ask Yourself These Questions)

| Question                                           | If Yes → Put Logic In          |
|----------------------------------------------------|--------------------------------|
| Does this directly modify or read the board?       | **Gameboard** |
| Does this involve player data (name, mark)?        | **Player** |
| Does this control the flow or rules of the game?   | **GameController** |
| Does this involve updating or interacting with the DOM? | **DisplayController** |

### Best Practice Tips

- **Gameboard** should **not** know anything about the DOM or players.
- **DisplayController** should **not** directly modify the board array.
- **GameController** acts as the "brain" — it talks to Gameboard and DisplayController.
- Keep each module focused and single-responsibility.
- If you're unsure, ask: “Does this logic belong to the data, the rules, the player, or the UI?”

### Example of Good Separation

```js
// Gameboard only cares about the board
Gameboard.placeMark(4, 'X');

// GameController manages the game flow
GameController.playTurn(4);

// DisplayController only handles rendering
DisplayController.render();
```


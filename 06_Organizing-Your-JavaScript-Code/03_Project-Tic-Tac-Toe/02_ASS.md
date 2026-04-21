
### Tic-Tac-Toe – Core Objects & Architecture Cheat Sheet

| Component              | Purpose                                                                 | Recommended Implementation |
|------------------------|-------------------------------------------------------------------------|----------------------------|
| **Gameboard**          | Stores the current state of the 3x3 board                               | Object containing a private array (`board`) |
| **Player**             | Represents each player (X or O)                                         | Object with `name`, `mark` ('X' or 'O'), and methods |
| **Game Controller**    | Controls the flow of the game (turns, win conditions, reset, etc.)      | Main object that orchestrates everything |
| **Display Controller** | Handles everything related to the DOM and rendering                     | Separate object for UI updates |

### 1. Gameboard Object (Most Important Starting Point)

```js
const Gameboard = (function() {
  let board = ['', '', '', '', '', '', '', '', ''];   // 9 cells, indexed 0-8

  const getBoard = () => board;

  const placeMark = (index, mark) => {
    if (board[index] === '') {
      board[index] = mark;
      return true;
    }
    return false;   // Cell already taken
  };

  const resetBoard = () => {
    board = ['', '', '', '', '', '', '', '', ''];
  };

  return {
    getBoard,
    placeMark,
    resetBoard
  };
})();
```

### 2. Player Object

```js
const Player = (name, mark) => {
  return {
    name,
    mark,
    getName: () => name,
    getMark: () => mark
  };
};
```

### 3. Game Controller (Flow Control)

```js
const GameController = (function() {
  let players = [];
  let currentPlayerIndex = 0;
  let gameOver = false;

  const startGame = (player1Name, player2Name) => {
    players = [
      Player(player1Name, 'X'),
      Player(player2Name, 'O')
    ];
    currentPlayerIndex = 0;
    gameOver = false;
    Gameboard.resetBoard();
    DisplayController.render();
  };

  const playTurn = (index) => {
    if (gameOver) return;

    const currentPlayer = players[currentPlayerIndex];
    const success = Gameboard.placeMark(index, currentPlayer.mark);

    if (success) {
      // Check for win or draw here (to be added later)
      currentPlayerIndex = currentPlayerIndex === 0 ? 1 : 0;
      DisplayController.render();
    }
  };

  const getCurrentPlayer = () => players[currentPlayerIndex];

  return {
    startGame,
    playTurn,
    getCurrentPlayer
  };
})();
```

### 4. Display Controller (UI Layer)

```js
const DisplayController = (function() {
  const boardDiv = document.getElementById('board');

  const render = () => {
    boardDiv.innerHTML = '';
    const board = Gameboard.getBoard();

    board.forEach((mark, index) => {
      const cell = document.createElement('div');
      cell.classList.add('cell');
      cell.textContent = mark;
      cell.dataset.index = index;
      boardDiv.appendChild(cell);
    });
  };

  return { render };
})();
```

### Summary Table – Object Responsibilities

| Object                | Stores                          | Main Responsibilities |
|-----------------------|---------------------------------|-----------------------|
| **Gameboard**         | `board` array                   | Store marks, place marks, reset |
| **Player**            | name, mark                      | Hold player data |
| **GameController**    | Current player, game state      | Manage turns, win conditions, game flow |
| **DisplayController** | — (UI only)                     | Render board, handle clicks, update DOM |

### Key Principles to Follow

- Keep **data** (Gameboard) separate from **display** (DisplayController)
- Use **Immediately Invoked Function Expressions (IIFEs)** for modules to create private scope
- Gameboard should **not** know about the DOM
- DisplayController should **not** directly modify the game logic

Would you like me to expand this cheat sheet with:
- Win condition checking logic?
- How to connect click events on the board?
- Full starter code with all 4 modules?




### Adding Marks via DOM Click – Cheat Sheet

| Aspect                              | Recommendation & Best Practice |
|-------------------------------------|--------------------------------|
| **Goal**                            | Allow players to click on a board cell to place their mark (X or O) |
| **Key Principle**                   | Keep game logic separate from DOM logic (GameController handles rules, DisplayController handles clicks) |
| **Main Technique**                  | **Event Delegation** – Attach one click listener to the board container |
| **Prevent Invalid Moves**           | Check if the cell is already taken before placing a mark |

### Step-by-Step Implementation

| Step | Task | Code / Details |
|------|------|----------------|
| **1** | Add click listener using event delegation | Attach listener to the board container (`#board`) |
| **2** | Identify which cell was clicked | Use `e.target.dataset.index` |
| **3** | Validate the move | Check if the cell is empty using `Gameboard` |
| **4** | Place the mark | Call `GameController.playTurn(index)` |
| **5** | Update the display | `DisplayController.render()` is called inside `playTurn` |

### Recommended Code

#### 1. Update `DisplayController` to add event listeners

```js
const DisplayController = (function() {
  const boardElement = document.getElementById('board');

  const render = () => {
    boardElement.innerHTML = '';
    const board = Gameboard.getBoard();

    board.forEach((mark, index) => {
      const cell = document.createElement('div');
      cell.classList.add('cell');
      cell.textContent = mark || '';           // Show X, O, or empty
      cell.dataset.index = index;
      boardElement.appendChild(cell);
    });
  };

  // Add click handling with event delegation
  const addClickListeners = () => {
    boardElement.addEventListener('click', (e) => {
      const cell = e.target.closest('.cell');   // Ensure we clicked a cell
      if (!cell) return;

      const index = parseInt(cell.dataset.index);

      GameController.playTurn(index);   // Let GameController handle logic
    });
  };

  return {
    render,
    addClickListeners
  };
})();
```

#### 2. Update `GameController.playTurn()`

```js
const GameController = (function() {
  // ... existing code ...

  const playTurn = (index) => {
    if (gameOver) return;

    const currentPlayer = players[currentPlayerIndex];
    const success = Gameboard.placeMark(index, currentPlayer.mark);

    if (success) {
      DisplayController.render();           // Update UI after valid move

      // Check win or draw
      if (checkWinner()) {
        gameOver = true;
        console.log(`${currentPlayer.name} wins!`);
      } else if (checkDraw()) {
        gameOver = true;
        console.log("It's a draw!");
      } else {
        // Switch turn
        currentPlayerIndex = currentPlayerIndex === 0 ? 1 : 0;
      }
    }
  };

  return { playTurn, ... };
})();
```

### Important Logic Flow

1. User clicks a cell → `DisplayController` catches the click
2. Click passes the `index` to `GameController.playTurn(index)`
3. `GameController` asks `Gameboard` to place the mark
4. If successful → `DisplayController.render()` is called
5. GameController checks for win/draw and switches turns if needed

### Key Rules to Follow

| Rule | Why |
|------|-----|
| Use **event delegation** | Only one listener on the parent instead of 9 separate listeners |
| Check cell is empty **before** placing mark | Prevents overwriting existing moves |
| Always call `render()` after a successful move | Keeps UI in sync with game state |
| Game logic stays in `GameController` | DisplayController should not decide if a move is valid |

### Quick Testing Tip

After implementing, test in this order:
1. Click empty cells → marks appear
2. Click already taken cells → nothing happens
3. Play until someone wins or draw → correct message appears

Would you like me to provide:
- The full updated code for all three modules?
- CSS for nice-looking cells?
- Or how to disable clicks when the game is over?


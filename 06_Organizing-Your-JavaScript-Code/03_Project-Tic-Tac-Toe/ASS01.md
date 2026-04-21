

### Minimize Global Code – Tic-Tac-Toe Cheat Sheet

| Principle                          | Explanation                                                                 | How to Apply in Tic-Tac-Toe |
|------------------------------------|-----------------------------------------------------------------------------|-----------------------------|
| **Goal**                           | Keep as little code as possible in the global scope                         | Only expose what is absolutely necessary |
| **Main Strategy**                  | Use **factories** for multiple instances and **IIFEs (Module Pattern)** for single instances | Wrap single-use objects in IIFEs |
| **Factories**                      | Functions that return new objects (used when you may need multiple instances) | `Player` factory |
| **Modules (IIFE)**                 | Immediately Invoked Function Expression that returns a single object        | `Gameboard`, `GameController`, `DisplayController` |
| **Why this matters**               | Prevents namespace pollution, improves maintainability, and reduces bugs    | Makes your code cleaner and more professional |

### Recommended Architecture (Best Practice)

| Object / Module               | Type          | Should It Be Reusable? | Implementation |
|-------------------------------|---------------|------------------------|----------------|
| **Gameboard**                 | Module (IIFE) | No (only one board)    | Wrap factory in IIFE |
| **GameController**            | Module (IIFE) | No (only one game)     | Wrap in IIFE |
| **DisplayController**         | Module (IIFE) | No (only one UI)       | Wrap in IIFE |
| **Player**                    | Factory       | Yes (two players)      | Regular factory function |
| **Global Scope**              | —             | Minimal                | Only `myLibrary` or nothing at all |

### Code Structure Example

```js
// 1. Player Factory (can create multiple players)
const Player = (name, mark) => {
  return {
    name,
    mark,
    getName: () => name,
    getMark: () => mark
  };
};

// 2. Gameboard Module (single instance → IIFE)
const Gameboard = (function() {
  let board = Array(9).fill(null);

  const getBoard = () => board;
  const placeMark = (index, mark) => { ... };
  const reset = () => { board = Array(9).fill(null); };

  return { getBoard, placeMark, reset };
})();

// 3. GameController Module (single instance → IIFE)
const GameController = (function() {
  let players = [];
  let currentPlayer = 0;

  const startNewGame = () => { ... };
  const makeMove = (index) => { ... };

  return { startNewGame, makeMove, getCurrentPlayer: () => players[currentPlayer] };
})();

// 4. DisplayController Module (single instance → IIFE)
const DisplayController = (function() {
  const render = () => { ... };
  const addEventListeners = () => { ... };

  return { render, addEventListeners };
})();
```

### Key Rules to Follow

| Rule | Explanation |
|------|-----------|
| **Single Instance** | If you only need **one** of something (Gameboard, GameController, DisplayController), wrap it in an **IIFE** (Module Pattern) |
| **Multiple Instances** | If you need **multiple** (like two Players), use a **Factory Function** |
| **Minimize Globals** | Ideally, the only thing in the global scope should be the module names themselves |
| **Encapsulation** | Keep internal variables and helper functions private inside the IIFE |

### Benefits of This Approach

- Cleaner global namespace
- Better organization and readability
- Easier debugging
- More maintainable code
- Prevents accidental overwriting of variables

### Quick Checklist

- [ ] `Gameboard` is wrapped in an IIFE
- [ ] `GameController` is wrapped in an IIFE
- [ ] `DisplayController` is wrapped in an IIFE
- [ ] `Player` is a factory function
- [ ] Almost no variables are declared in the global scope
- [ ] All major logic is encapsulated inside modules


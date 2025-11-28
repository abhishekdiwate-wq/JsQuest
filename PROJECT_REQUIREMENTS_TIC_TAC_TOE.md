# ❌⭕ Tic-Tac-Toe Game - Project Requirements

#Demo https://ticktacktoe-7aa6d.web.app/

**Estimated Time:** 2 - 2.5 hours  
**Difficulty:** Medium  
---

## 📋 User Story

**As a** game player  
**I want to** play Tic-Tac-Toe against another player  
**So that I can** compete with my friends and track our win/loss records over multiple games

---

## 📝 Description

Build an interactive two-player Tic-Tac-Toe game (also known as Noughts and Crosses or X's and O's) where players alternate turns placing their marks (X or O) on a 3×3 grid. The first player to get three of their marks in a row (horizontally, vertically, or diagonally) wins the game.

The game should detect win conditions, handle draws, maintain a scoreboard across multiple games, and persist game history using browser's localStorage.

---

## ✅ Acceptance Criteria

### AC1: Game Board Initialization
- **GIVEN** the page loads  
- **WHEN** the game initializes  
- **THEN** a 3×3 grid of empty cells should be displayed  
- **AND** the game should indicate "Player X's Turn"  
- **AND** Player X should always start first  
- **AND** all cells should be clickable

### AC2: Player Turn Mechanics
- **GIVEN** the game is in progress  
- **WHEN** a player clicks an empty cell  
- **THEN** their mark (X or O) should appear in that cell  
- **AND** the cell should become unclickable  
- **AND** the turn indicator should switch to the other player  
- **AND** clicking on an already filled cell should have no effect

### AC3: Win Detection - Rows
- **GIVEN** three cells in any row contain the same mark  
- **WHEN** the third matching mark is placed  
- **THEN** the game should detect the win  
- **AND** display "{Player} Wins!" message  
- **AND** highlight the winning row  
- **AND** prevent further moves  
- **AND** update the winner's score

### AC4: Win Detection - Columns
- **GIVEN** three cells in any column contain the same mark  
- **WHEN** the third matching mark is placed  
- **THEN** the game should detect the win  
- **AND** display "{Player} Wins!" message  
- **AND** highlight the winning column  
- **AND** prevent further moves  
- **AND** update the winner's score

### AC5: Win Detection - Diagonals
- **GIVEN** three cells in either diagonal contain the same mark  
- **WHEN** the third matching mark is placed  
- **THEN** the game should detect the win  
- **AND** display "{Player} Wins!" message  
- **AND** highlight the winning diagonal  
- **AND** prevent further moves  
- **AND** update the winner's score

### AC6: Draw Detection
- **GIVEN** all 9 cells are filled  
- **WHEN** no player has three in a row  
- **THEN** the game should detect a draw  
- **AND** display "It's a Draw!" message  
- **AND** prevent further moves  
- **AND** increment the draw counter

### AC7: Scoreboard Tracking
- **GIVEN** games are being played  
- **WHEN** a game ends (win or draw)  
- **THEN** the appropriate score should increment  
- **AND** the scoreboard should display: Player X wins, Draws, Player O wins  
- **AND** scores should persist after page refresh  
- **AND** scores should be loaded from localStorage on page load

### AC8: Game History
- **GIVEN** games have been completed  
- **WHEN** viewing the game history section  
- **THEN** the last 10 games should be displayed  
- **AND** each entry should show: winner (or "Draw"), date, and time  
- **AND** the most recent game should appear at the top  
- **AND** history should persist after page refresh

### AC9: New Game / Reset
- **GIVEN** a game is in progress or completed  
- **WHEN** I click the "New Game" button  
- **THEN** the board should clear all marks  
- **AND** Player X should start first  
- **AND** the turn indicator should reset to "Player X's Turn"  
- **AND** all cells should become clickable again  
- **AND** winning cell highlights should be removed  
- **AND** scores should NOT reset

### AC10: Clear History
- **GIVEN** there is game history and scores  
- **WHEN** I click the "Clear History" button  
- **THEN** I should see a confirmation dialog  
- **AND** if I confirm, all scores should reset to 0  
- **AND** all game history should be cleared  
- **AND** localStorage should be cleared  
- **AND** the UI should update to reflect the reset

---

## 🔧 Technical Requirements

### TR1: HTML Structure
- Single HTML file with embedded CSS and JavaScript
- Semantic HTML5 elements
- 3×3 grid created dynamically via JavaScript
- No external dependencies or libraries

### TR2: CSS Styling
- Responsive layout for desktop browsers
- Clear visual distinction between X and O marks
- Hover effects on empty cells
- Winning cells highlighted with distinct color/animation
- Professional color scheme
- Proper spacing and alignment

### TR3: JavaScript Implementation
- Pure vanilla JavaScript (ES6+ features allowed)
- Use of `const` and `let` (avoid `var`)
- Clean, modular code with well-named functions
- Proper event handling
- No global namespace pollution

### TR4: Data Persistence
- Use localStorage API for persistence
- Store scores as JSON object:
```javascript
{
  X: Number,
  O: Number,
  draw: Number
}
```
- Store game history as JSON array:
```javascript
[
  {
    winner: "X" | "O" | "Draw",
    date: String,
    board: Array // optional
  }
]
```

### TR5: Game Logic
- Win condition checking for all 8 possibilities:
  - 3 rows
  - 3 columns
  - 2 diagonals
- Board state array to track X, O, or empty
- Game state management (active/ended)
- Turn tracking

---

## 🎯 Functional Requirements

### FR1: Game Board
- 3×3 grid with equal-sized cells
- Cells should be square (1:1 aspect ratio)
- Clear borders between cells
- Adequate spacing for marks
- Responsive to container size

### FR2: Player Marks
- Player X mark: "X" or "❌" emoji
- Player O mark: "O" or "⭕" emoji
- Different colors for X and O (recommended: X=blue, O=purple)
- Marks should be centered in cells
- Font size should be large and readable

### FR3: Turn Indicator
- Display current player's turn prominently
- Format: "Player X's Turn" or "Player O's Turn"
- Update immediately after each move
- Show win/draw message when game ends

### FR4: Scoreboard
- Three score counters displayed horizontally:
  - Player X score (left)
  - Draws (center)
  - Player O score (right)
- Clear labels for each counter
- Large, readable numbers
- Real-time updates

### FR5: Game History
- Display last 10 games
- Scrollable list if needed
- Each entry format: "Winner: X | Date: MM/DD/YYYY HH:MM"
- Most recent game at top
- Show "No games played yet" if history is empty

### FR6: Control Buttons
- "New Game" button - resets board, keeps scores
- "Clear History" button - resets everything
- Buttons should be clearly labeled
- Visual feedback on hover
- Disabled state when appropriate (optional)

---

## 🎨 Non-Functional Requirements

### NFR1: Performance
- Instant response to cell clicks
- No lag in UI updates
- Win detection should complete in < 10ms

### NFR2: Usability
- Intuitive gameplay (no tutorial needed)
- Clear visual feedback for all actions
- Obvious which cells are clickable
- Cannot click on filled cells
- Cannot make moves after game ends

### NFR3: Browser Compatibility
- Must work in modern browsers (Chrome, Firefox, Safari, Edge)
- No console errors
- Graceful handling if localStorage is unavailable

### NFR4: Code Quality
- Function names describe their purpose
- Variable names are descriptive
- Consistent code formatting
- No magic numbers (use constants)
- Comments only where logic is complex

---

## 🧪 Definition of Done

- [ ] All 10 acceptance criteria met and verified
- [ ] Game runs without console errors
- [ ] All 8 win conditions detected correctly
- [ ] Draw condition detected correctly
- [ ] Scores persist after page refresh
- [ ] Game history persists after page refresh
- [ ] New Game button works correctly
- [ ] Clear History button works with confirmation
- [ ] Cannot click filled cells
- [ ] Cannot make moves after game ends
- [ ] Winning cells highlighted
- [ ] Turn indicator updates correctly
- [ ] Code is clean and well-organized
- [ ] No hardcoded values where dynamic needed
- [ ] Instructions section removed from submission

---

## 🧪 Test Scenarios

### Test Case 1: Basic Gameplay
1. Open game in browser
2. Verify empty 3×3 grid displays
3. Verify "Player X's Turn" message shows
4. Click cell (0,0) → X appears
5. Verify "Player O's Turn" message shows
6. Click cell (1,1) → O appears
7. Verify "Player X's Turn" message shows
8. Continue alternating until win or draw

### Test Case 2: Win Conditions
**Test all 8 winning patterns:**
1. Row 1: [0,0], [0,1], [0,2]
2. Row 2: [1,0], [1,1], [1,2]
3. Row 3: [2,0], [2,1], [2,2]
4. Col 1: [0,0], [1,0], [2,0]
5. Col 2: [0,1], [1,1], [2,1]
6. Col 3: [0,2], [1,2], [2,2]
7. Diagonal 1: [0,0], [1,1], [2,2]
8. Diagonal 2: [0,2], [1,1], [2,0]

For each pattern:
- Play to create that pattern for X
- Verify "Player X Wins!" displays
- Verify winning cells highlighted
- Verify cannot make more moves
- Verify score increments

### Test Case 3: Draw Condition
1. Play sequence that fills board without winner:
   - X: [0,0], [0,1], [1,0], [1,2], [2,1]
   - O: [0,2], [1,1], [2,0], [2,2]
2. Verify "It's a Draw!" displays
3. Verify draw counter increments
4. Verify game history records draw

### Test Case 4: Edge Cases
1. Click same cell twice → second click ignored
2. Click cell after game ends → click ignored
3. Rapid clicking → should not break turn logic
4. Click outside cells → no error

### Test Case 5: Persistence
1. Play 3 games (2 X wins, 1 O win)
2. Verify scores: X=2, O=1, Draw=0
3. Refresh page
4. Verify scores still: X=2, O=1, Draw=0
5. Verify game history shows 3 games
6. Click "Clear History" → Cancel
7. Verify scores unchanged
8. Click "Clear History" → Confirm
9. Verify all scores = 0
10. Refresh page → verify still 0

### Test Case 6: Multiple Games
1. Play game 1 → X wins
2. Click "New Game"
3. Verify board cleared, X's turn, scores kept
4. Play game 2 → O wins
5. Click "New Game"
6. Verify scoreboard shows X=1, O=1
7. Play 10+ games
8. Verify history shows only last 10 games

---

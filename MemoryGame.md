# 🎮 Memory Card Game - Project Requirements
# Demo: https://www.helpfulgames.com/subjects/brain-training/memory.html

**Estimated Time:** 2.5 - 3 hours  
**Difficulty:** Medium-Hard  
**Points:** 100

---

## 📋 User Story

**As a** game player  
**I want to** play a memory card matching game  
**So that I can** test and improve my memory while having fun, and track my performance over time

---

## 📝 Description

Build an interactive Memory Card Game (also known as Concentration or Match Match) where players flip cards to find matching pairs. The game should track player performance (moves and time), detect win conditions, and persist game statistics using browser's localStorage.

The game features a 4x4 grid (16 cards, 8 pairs) with emoji symbols. Players flip two cards at a time to find matches. The game tracks moves, elapsed time, and maintains a high score board.

---

## ✅ Acceptance Criteria

### AC1: Game Board Initialization
- **GIVEN** the page loads  
- **WHEN** the game initializes  
- **THEN** a 4x4 grid of face-down cards should be displayed  
- **AND** cards should be randomly shuffled each game  
- **AND** each symbol appears exactly twice (8 pairs total)

### AC2: Card Flipping Mechanism
- **GIVEN** the game is in progress  
- **WHEN** I click on a face-down card  
- **THEN** the card should flip to reveal its symbol  
- **AND** the card should remain flipped until a second card is selected  
- **AND** I should not be able to flip more than 2 cards simultaneously  
- **AND** I should not be able to flip an already matched card  
- **AND** I should not be able to flip the same card twice in one turn

### AC3: Match Detection
- **GIVEN** I have flipped two cards  
- **WHEN** both cards have the same symbol  
- **THEN** both cards should remain face-up  
- **AND** both cards should be visually marked as matched (green background)  
- **AND** the match counter should increment by 1  
- **AND** I should be able to immediately flip the next pair

### AC4: Mismatch Handling
- **GIVEN** I have flipped two cards  
- **WHEN** the cards have different symbols  
- **THEN** both cards should flip back to face-down after 1 second  
- **AND** I should not be able to flip other cards during this delay  
- **AND** the move counter should increment

### AC5: Move Counter
- **GIVEN** the game is in progress  
- **WHEN** I flip two cards (regardless of match/mismatch)  
- **THEN** the move counter should increment by 1  
- **AND** the move count should be displayed in real-time  
- **AND** the move counter should reset when starting a new game

### AC6: Timer Functionality
- **GIVEN** the game has loaded  
- **WHEN** I flip the first card  
- **THEN** the timer should start counting from 00:00  
- **AND** the timer should update every second  
- **AND** the timer should display in MM:SS format  
- **AND** the timer should stop when all pairs are matched  
- **AND** the timer should reset when starting a new game

### AC7: Win Condition
- **GIVEN** I am playing the game  
- **WHEN** all 8 pairs are successfully matched  
- **THEN** the timer should stop  
- **AND** a win modal/message should appear  
- **AND** the modal should display my final moves and time  
- **AND** my score should be saved to the high scores list

### AC8: High Scores Persistence
- **GIVEN** I have completed a game  
- **WHEN** the game ends  
- **THEN** my score (moves and time) should be saved to localStorage  
- **AND** the high scores list should display the top 5 best times  
- **AND** each score should show moves, time, and date  
- **AND** scores should be sorted by fastest time  
- **AND** scores should persist after page refresh

### AC9: Reset Game
- **GIVEN** I am at any point in the game  
- **WHEN** I click the "Reset Game" button  
- **THEN** all cards should be reshuffled and face-down  
- **AND** the move counter should reset to 0  
- **AND** the timer should reset to 00:00  
- **AND** the match counter should reset to 0/8  
- **AND** the timer should not start until I flip the first card

### AC10: Clear History
- **GIVEN** there are saved high scores  
- **WHEN** I click the "Clear History" button  
- **THEN** I should see a confirmation dialog  
- **AND** if I confirm, all scores should be removed from localStorage  
- **AND** the high scores list should show "No scores yet"  
- **AND** the score counters should reset to 0

---

## 🔧 Technical Requirements

### TR1: HTML Structure
- Single HTML file with embedded CSS and JavaScript
- Semantic HTML5 elements where appropriate
- All game elements created dynamically via JavaScript
- No external dependencies or libraries

### TR2: CSS Styling
- Responsive layout that works on desktop browsers
- Visual feedback for hover states on cards
- Smooth transitions for card flips (minimum 0.3s)
- Distinct visual states for: normal, flipped, matched cards
- Matching animation when cards match
- Professional color scheme and typography

### TR3: JavaScript Implementation
- Pure vanilla JavaScript (ES6+ features allowed)
- No jQuery or external libraries
- Use of `const` and `let` (avoid `var`)
- Proper event delegation or individual event listeners
- Clean, readable code with meaningful variable names

### TR4: Data Persistence
- Use localStorage API for data persistence
- Store scores as JSON strings
- Proper error handling for localStorage operations
- Data structure: Array of score objects
```javascript
{
  moves: Number,
  time: Number (in seconds),
  date: String (ISO format or locale string)
}
```

### TR5: Game Logic
- Card shuffling using Fisher-Yates algorithm (or Math.random())
- Timer implementation using setInterval
- Proper state management (prevent race conditions)
- Board lock mechanism during card comparison

---

## 🎯 Functional Requirements

### FR1: Card Symbols
- Use 8 different emoji symbols: 🎮, 🎯, 🎨, 🎭, 🎪, 🎸, 🎺, 🎹
- Each symbol appears exactly twice (total 16 cards)
- Symbols should be clearly visible when flipped

### FR2: Game Board Layout
- 4x4 grid layout (4 columns × 4 rows)
- Equal spacing between cards
- Cards should be square (1:1 aspect ratio)
- Responsive sizing based on container width

### FR3: Statistics Display
- Real-time move counter (increments with each pair attempt)
- Real-time timer in MM:SS format with leading zeros
- Real-time match counter (X/8 format)
- All stats should be clearly labeled

### FR4: High Scores Display
- Show top 5 scores only
- Sort by fastest time (ascending)
- Display format: "Time: MM:SS | Moves: X | Date: ..."
- Show "No scores yet" message when list is empty

### FR5: User Interface Controls
- "Reset Game" button - starts new game
- "Clear History" button - clears all saved scores
- "Play Again" button in win modal - starts new game and closes modal
- All buttons should have clear labels and be easily clickable

---

## 🎨 Non-Functional Requirements

### NFR1: Performance
- Game should load and initialize within 1 second
- Card flip animations should be smooth (60fps)
- No noticeable lag when clicking cards
- localStorage operations should not block UI

### NFR2: Usability
- Intuitive gameplay (no instructions needed for basic play)
- Clear visual feedback for all user actions
- Disabled state for cards that shouldn't be clickable
- Responsive button hover states

### NFR3: Browser Compatibility
- Must work in modern browsers (Chrome, Firefox, Safari, Edge)
- Must support browsers with localStorage API
- No console errors in browser DevTools

### NFR4: Code Quality
- Functions should be single-purpose and reusable
- Descriptive function and variable names (camelCase)
- Comments for complex logic only
- Proper indentation (2 or 4 spaces consistent)
- No unused variables or functions

---

## 🧪 Definition of Done

- [ ] All acceptance criteria are met and verified
- [ ] Game runs without console errors
- [ ] All buttons and interactions work as expected
- [ ] localStorage saves and retrieves data correctly
- [ ] Code is clean, readable, and properly formatted
- [ ] No hardcoded values where they should be dynamic
- [ ] Timer displays correctly in MM:SS format
- [ ] Win condition triggers correctly after 8 matches
- [ ] High scores persist after page refresh
- [ ] Confirmation dialog appears before clearing history
- [ ] Cards cannot be clicked during comparison delay
- [ ] Game board reshuffles on reset
- [ ] Instructions section removed from final submission

---

## 🧪 Test Scenarios

### Test Case 1: Basic Game Flow
1. Open the game in browser
2. Verify 16 face-down cards are displayed
3. Click first card → should flip and show symbol
4. Verify timer starts (was 00:00, now 00:01+)
5. Click second card → should flip and show symbol
6. Verify move counter increments to 1
7. If match: both cards stay face-up with green background
8. If no match: both cards flip back after 1 second
9. Continue until all 8 pairs matched
10. Verify win modal appears with correct stats

### Test Case 2: Edge Cases
1. Click same card twice → should not count as second card
2. Click third card while two cards showing → should not flip
3. Click matched card → should not flip
4. Rapid clicking multiple cards → should only flip two at a time
5. Reset game mid-play → all stats should reset

### Test Case 3: localStorage
1. Complete a game → verify score appears in high scores
2. Refresh page → verify scores still present
3. Complete 6 games → verify only top 5 displayed
4. Click "Clear History" → cancel → scores remain
5. Click "Clear History" → confirm → scores removed
6. Refresh page → verify scores still cleared

### Test Case 4: Timer
1. Load game → timer shows 00:00
2. Wait 5 seconds → timer still 00:00
3. Click first card → timer starts
4. Complete game → timer stops at final time
5. Win modal shows same time as game display
6. Reset game → timer resets to 00:00

### Test Case 5: Visual Feedback
1. Hover over face-down card → card scales up slightly
2. Hover over matched card → no hover effect
3. Card flip has smooth animation
4. Matched cards have distinct green background
5. Win modal slides in with animation
6. Button hover states work correctly

---

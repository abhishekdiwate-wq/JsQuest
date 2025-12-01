# 📝 Quiz Application - Project Requirements

## Project ID: JS-EXAM-003
**Project Type:** Practical Exam  
**Estimated Time:** 2.5 - 3 hours  
**Difficulty:** Medium  
**Points:** 100

---

## 📋 User Story

**As a** quiz taker  
**I want to** answer multiple-choice questions with a timer  
**So that I can** test my knowledge, see my results, and track my performance over time

---

## 📝 Description

Build an interactive Quiz Application that presents users with multiple-choice questions, tracks their answers, enforces a time limit, calculates scores, and displays results. The application should save quiz attempts and scores to localStorage for future reference.

The quiz should contain at least 10 multiple-choice questions (each with 4 options), display one question at a time, show a countdown timer, provide immediate feedback on answers, and maintain a history of quiz attempts with scores.

---

## ✅ Acceptance Criteria

### AC1: Quiz Initialization
- **GIVEN** the page loads  
- **WHEN** the quiz initializes  
- **THEN** a "Start Quiz" button should be displayed  
- **AND** the first question should not be visible yet  
- **AND** instructions or welcome message should be shown  
- **AND** previous quiz results should be displayed (if any)

### AC2: Start Quiz
- **GIVEN** the quiz is not started  
- **WHEN** I click the "Start Quiz" button  
- **THEN** the first question should be displayed  
- **AND** 4 answer options should be visible and clickable  
- **AND** the timer should start counting down from the time limit  
- **AND** a progress indicator should show "Question 1 of 10"  
- **AND** the score should be initialized to 0

### AC3: Display Questions
- **GIVEN** the quiz is in progress  
- **WHEN** viewing a question  
- **THEN** the question text should be clearly displayed  
- **AND** exactly 4 answer options should be shown  
- **AND** each option should be clickable  
- **AND** only one option can be selected at a time  
- **AND** the question number should be displayed (e.g., "Question 3 of 10")

### AC4: Answer Selection
- **GIVEN** a question is displayed  
- **WHEN** I click on an answer option  
- **THEN** that option should be visually highlighted/selected  
- **AND** previously selected option (if any) should be deselected  
- **AND** I should be able to change my answer before submitting  
- **AND** a "Next" or "Submit" button should be enabled

### AC5: Immediate Feedback (Optional Standard, Required for Full Points)
- **GIVEN** I have selected an answer  
- **WHEN** I click "Next" or "Submit"  
- **THEN** the correct answer should be highlighted in green  
- **AND** if my answer was wrong, it should be highlighted in red  
- **AND** I should not be able to change my answer after submission  
- **AND** a brief explanation can be shown (optional)

### AC6: Navigate to Next Question
- **GIVEN** I have answered the current question  
- **WHEN** I click the "Next" button  
- **THEN** the next question should be displayed  
- **AND** the progress indicator should update (e.g., "Question 4 of 10")  
- **AND** my previous answer should be recorded  
- **AND** the answer options should be in unselected state  
- **AND** the feedback from previous question should clear

### AC7: Timer Functionality
- **GIVEN** the quiz is in progress  
- **WHEN** time is elapsing  
- **THEN** the timer should count down every second  
- **AND** the timer should display in MM:SS or SS format  
- **AND** when timer reaches 0, the quiz should auto-submit  
- **AND** time remaining should be clearly visible  
- **AND** timer should be red or warning color when < 10 seconds

### AC8: Quiz Completion - Manual
- **GIVEN** I have answered all 10 questions  
- **WHEN** I click "Submit Quiz" on the last question  
- **THEN** the quiz should end  
- **AND** the timer should stop  
- **AND** my score should be calculated  
- **AND** results screen should be displayed  
- **AND** quiz attempt should be saved to localStorage

### AC9: Quiz Completion - Time Out
- **GIVEN** the quiz is in progress  
- **WHEN** the timer reaches 0  
- **THEN** the quiz should automatically submit  
- **AND** unanswered questions should be marked as incorrect  
- **AND** results screen should be displayed  
- **AND** a message indicating "Time's Up!" should be shown

### AC10: Results Display
- **GIVEN** the quiz has been completed  
- **WHEN** viewing the results screen  
- **THEN** my total score should be displayed (e.g., "7/10" or "70%")  
- **AND** time taken should be shown  
- **AND** a performance message should appear (e.g., "Great job!")  
- **AND** an option to "Review Answers" should be available  
- **AND** an option to "Retake Quiz" should be available  
- **AND** the result should be saved to quiz history

### AC11: Review Answers
- **GIVEN** I have completed the quiz  
- **WHEN** I click "Review Answers"  
- **THEN** all questions should be displayed  
- **AND** my answers should be shown  
- **AND** correct answers should be shown  
- **AND** correct answers should be highlighted in green  
- **AND** incorrect answers should be highlighted in red

### AC12: Quiz History
- **GIVEN** I have taken quizzes previously  
- **WHEN** viewing the quiz history section  
- **THEN** my past quiz attempts should be displayed  
- **AND** each entry should show: score, date, time taken  
- **AND** the last 10 attempts should be saved  
- **AND** history should be sorted by most recent first  
- **AND** history should persist after page refresh

### AC13: Retake Quiz
- **GIVEN** I have completed a quiz  
- **WHEN** I click "Retake Quiz"  
- **THEN** the quiz should reset to the first question  
- **AND** all answers should be cleared  
- **AND** the timer should reset to the full time limit  
- **AND** questions should be in the same or randomized order (implementation choice)

### AC14: Clear History
- **GIVEN** there is quiz history  
- **WHEN** I click "Clear History" button  
- **THEN** I should see a confirmation dialog  
- **AND** if I confirm, all quiz history should be deleted  
- **AND** localStorage should be cleared  
- **AND** the history section should show "No quiz history yet"

---

## 🔧 Technical Requirements

### TR1: HTML Structure
- Single HTML file with embedded CSS and JavaScript
- Semantic HTML5 elements
- Form elements for quiz questions and options
- Modal or section for results display
- No external dependencies or libraries

### TR2: CSS Styling
- Responsive layout for desktop browsers
- Clear visual distinction between:
  - Selected answer
  - Correct answer (green)
  - Incorrect answer (red)
  - Unselected options
- Progress bar or indicator
- Timer with visual warning when time is low
- Professional, clean design

### TR3: JavaScript Implementation
- Pure vanilla JavaScript (ES6+ features allowed)
- Use of `const` and `let` (avoid `var`)
- Question data stored in array of objects
- Clean, modular functions
- Proper event handling

### TR4: Question Data Structure
```javascript
const questions = [
  {
    question: "What does HTML stand for?",
    options: [
      "Hyper Text Markup Language",
      "High Tech Modern Language",
      "Home Tool Markup Language",
      "Hyperlinks and Text Markup Language"
    ],
    correctAnswer: 0, // index of correct option
    explanation: "HTML stands for Hyper Text Markup Language" // optional
  },
  // ... more questions
];
```

### TR5: Data Persistence
- Use localStorage API for quiz history
- Store quiz attempts as JSON array:
```javascript
[
  {
    score: Number, // e.g., 7 out of 10
    percentage: Number, // e.g., 70
    totalQuestions: Number, // 10
    timeTaken: Number, // in seconds
    date: String, // ISO format or locale string
    answers: Array // user's answers (optional)
  }
]
```

---

## 🎯 Functional Requirements

### FR1: Quiz Questions
- Minimum 10 multiple-choice questions
- Each question has exactly 4 options
- Questions should be on JavaScript, HTML, CSS, or web development
- Clear, unambiguous question text
- One correct answer per question

### FR2: Timer Configuration
- Total time limit: 120 seconds (2 minutes) OR 60 seconds (1 minute)
- Display format: MM:SS or just SS seconds
- Visual warning when < 10 seconds remain (red color)
- Auto-submit when time reaches 0

### FR3: Progress Indicator
- Show current question number and total (e.g., "Question 5 of 10")
- Visual progress bar (optional but recommended)
- Percentage progress (optional)

### FR4: Score Calculation
- 1 point per correct answer
- 0 points for incorrect or unanswered questions
- Display as: "X/10" and percentage (e.g., "7/10 - 70%")
- Calculate time taken (total time - remaining time)

### FR5: Results Screen
- Overall score (X/10 and percentage)
- Time taken
- Performance message:
  - 90-100%: "Excellent! 🎉"
  - 70-89%: "Great job! 👏"
  - 50-69%: "Good effort! 👍"
  - Below 50%: "Keep practicing! 💪"
- Buttons: "Review Answers", "Retake Quiz"

### FR6: Review Mode
- Show all questions with user's answers
- Highlight correct answers in green
- Highlight user's incorrect answers in red
- Option to return to results or retake quiz

### FR7: Quiz History Display
- Table or list format
- Columns: Attempt #, Score, Percentage, Time, Date
- Last 10 attempts only
- Sort by most recent first
- Responsive layout

---

## 🎨 Non-Functional Requirements

### NFR1: Performance
- Quiz loads instantly
- No lag when navigating between questions
- Timer updates smoothly every second
- localStorage operations don't block UI

### NFR2: Usability
- Intuitive navigation between questions
- Clear visual feedback for all interactions
- Easy-to-read text (proper font size and contrast)
- Obvious which option is selected
- Cannot proceed without selecting an answer (or allow skip)

### NFR3: Browser Compatibility
- Works in modern browsers (Chrome, Firefox, Safari, Edge)
- No console errors
- Graceful degradation if localStorage unavailable

### NFR4: Code Quality
- Well-organized, modular code
- Descriptive function and variable names
- No code duplication
- Proper error handling
- Comments for complex logic only

---

## 🧪 Definition of Done

- [ ] All 14 acceptance criteria met
- [ ] Minimum 10 questions implemented
- [ ] Timer counts down and auto-submits at 0
- [ ] Score calculated correctly
- [ ] Immediate feedback shows correct/incorrect answers
- [ ] Results screen displays all required information
- [ ] Review mode shows all questions and answers
- [ ] Quiz history persists after page refresh
- [ ] Can retake quiz successfully
- [ ] Clear history works with confirmation
- [ ] No console errors
- [ ] Code is clean and well-organized
- [ ] UI is responsive and user-friendly
- [ ] All buttons and interactions work correctly

---

## 🧪 Test Scenarios

### Test Case 1: Complete Quiz Flow
1. Load page → verify "Start Quiz" button visible
2. Click "Start Quiz" → first question appears
3. Verify timer starts counting down
4. Select an answer → verify it highlights
5. Click "Next" → verify correct/incorrect feedback
6. Navigate through all 10 questions
7. Verify progress indicator updates (1/10, 2/10, etc.)
8. On last question, click "Submit Quiz"
9. Verify results screen shows score, time, message
10. Verify quiz attempt saved to history

### Test Case 2: Timer Functionality
1. Start quiz
2. Wait and observe timer counting down
3. Verify timer displays correctly (MM:SS or SS)
4. Answer questions slowly
5. When timer reaches 0, verify quiz auto-submits
6. Verify "Time's Up!" message
7. Verify unanswered questions marked incorrect

### Test Case 3: Answer Selection
1. Start quiz
2. Click option A → verify it highlights
3. Click option B → verify A unhighlights, B highlights
4. Click option C → verify B unhighlights, C highlights
5. Click "Next" → verify answer recorded
6. Verify cannot change answer after clicking Next (if immediate feedback)

### Test Case 4: Score Calculation
1. Complete quiz answering:
   - Questions 1-7: Correct answers
   - Questions 8-10: Wrong answers
2. Verify final score shows "7/10" or "70%"
3. Start new quiz
4. Answer all questions correctly
5. Verify score shows "10/10" or "100%"

### Test Case 5: Review Answers
1. Complete quiz with mixed correct/incorrect answers
2. Click "Review Answers"
3. Verify all 10 questions displayed
4. Verify my answers shown
5. Verify correct answers highlighted green
6. Verify my wrong answers highlighted red
7. Verify correct answers always visible

### Test Case 6: localStorage Persistence
1. Complete 3 quizzes with different scores
2. Verify quiz history shows 3 attempts
3. Refresh page
4. Verify quiz history still shows 3 attempts
5. Complete 8 more quizzes (total 11)
6. Verify only last 10 attempts shown
7. Click "Clear History" → Confirm
8. Verify history cleared
9. Refresh page → verify still cleared

### Test Case 7: Retake Quiz
1. Complete quiz
2. View results
3. Click "Retake Quiz"
4. Verify back to question 1
5. Verify all answers cleared
6. Verify timer reset to full time
7. Complete quiz again
8. Verify history shows 2 attempts

### Test Case 8: Edge Cases
1. Start quiz → immediately let timer run out
2. Verify all questions marked as unanswered/incorrect
3. Start quiz → answer only 5 questions → let timer run out
4. Verify 5 answered correctly, 5 marked incorrect
5. Click "Start Quiz" twice quickly → should not break

---

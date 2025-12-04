# Numerical Mastermind - Project Statement

## 1. Problem Statement
Users interested in logic puzzles and deduction games require a lightweight, text-based application to practice their code-breaking skills without the overhead of heavy graphical interfaces or internet connectivity. There is a need for a streamlined, terminal-based implementation of the classic "Mastermind" mechanic that focuses purely on the logical challenge of deciphering a hidden numerical sequence through iterative feedback.

## 2. Scope of the Project
The scope of this project is to develop a single-player, Command Line Interface (CLI) game written in Python.

**The system includes:**
* **Game Logic:** Generation of a randomized, unique 4-digit secret key.
* **User Interaction:** A loop that accepts user input via the terminal.
* **Validation Layer:** Mechanisms to ensure user inputs adhere to game rules (e.g., length, numeric type, and uniqueness).
* **Feedback System:** Algorithms to calculate and display the accuracy of a guess based on exact matches and partial matches.
* **State Management:** Tracking the history of guesses and remaining attempts.

**The system excludes:**
* Graphical User Interface (GUI).
* Multiplayer capabilities.
* Persistent storage (database) for long-term score tracking.
* Variable difficulty settings (fixed to 4 digits).

## 3. Target Users
* **Logic Puzzle Enthusiasts:** Individuals who enjoy brain teasers and deduction-based games.
* **CLI Users:** Developers or hobbyists who prefer terminal-based utilities over graphical applications.
* **Python Learners:** Students or beginners looking for a clear example of game loops, input validation, and list manipulation in Python.

## 4. High-Level Features
Based on the codebase, the application implements the following core features:

### A. Random Secret Generation
* The system automatically generates a secret "key" at the start of every game.
* The key consists of **4 distinct digits** (0-9) with no repetitions, ensuring a solvable logic puzzle.

### B. Robust Input Validation
To prevent errors and ensure fair play, the system validates every guess:
* **Length Check:** Ensures the guess is exactly 4 characters.
* **Type Check:** Ensures the guess contains only numbers.
* **Uniqueness Check:** Ensures the guess does not contain repeated digits.

### C. Analytical Feedback Mechanism
After every valid guess, the system provides specific feedback:
* **Position Matches:** The count of digits that are correct and in the correct position.
* **Existence Matches:** The count of digits that exist in the secret key but are currently in the wrong position.

### D. Session History & Tracking
* **Attempt Limit:** The user is limited to **12 attempts** to guess the key.
* **History Display:** Before every new input, the game displays a log of the last 6 guesses along with their specific feedback scores, allowing the user to deduce the next move without memorizing previous turns.

### E. Win/Loss Conditions
* **Victory:** The game detects an exact match (`Key == Guess`) and terminates with a success message.
* **Defeat:** If the user fails after 12 attempts, the game reveals the secret key.
* 

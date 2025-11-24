# Numerical Mastermind

## Overview

Numerical Mastermind is a command-line implementation of the classic code-breaking game. The computer generates a secret 4-digit code with unique digits, and the player has 12 attempts to crack it. After each guess, the game provides feedback about how many digits are in the correct position and how many correct digits exist in wrong positions.

This project demonstrates fundamental programming concepts including random number generation, input validation, feedback algorithms, and game loop logic.

## Features

- **Random Code Generation**: Generates a unique 4-digit secret code with no repeating digits
- **Input Validation**: Ensures guesses are exactly 4 digits with no duplicates
- **Intelligent Feedback System**: 
  - Shows number of digits in correct positions
  - Shows number of correct digits in wrong positions
- **Guess History**: Displays the last 6 guesses with their feedback
- **Limited Attempts**: Players have 12 tries to crack the code
- **Clear User Interface**: Clean terminal-based interface with organized output

## Technologies/Tools Used

- **Python 3.x**: Core programming language
- **Built-in Python Modules**:
  - `random`: For generating the secret code
  - `collections.Counter`: For efficient digit counting and matching logic

## Installation & Setup

### Prerequisites
- Python 3.6 or higher installed on your system

### Steps to Install & Run

1. **Save the code**: Copy the game code into a file named `mastermind.py`

2. **Open terminal/command prompt**: Navigate to the directory containing `mastermind.py`
   ```bash
   cd path/to/your/directory
   ```

3. **Run the game**:
   ```bash
   python mastermind.py
   ```
   
   Or on some systems:
   ```bash
   python3 mastermind.py
   ```

4. **Start playing**: Follow the on-screen prompts to enter your guesses

## How to Play

1. The game generates a secret 4-digit code (digits 0-9, no repeats)
2. You have 12 attempts to guess the correct code
3. After each guess, you receive feedback:
   - **position**: Number of digits in the correct position
   - **exist**: Number of correct digits in wrong positions
4. Use the feedback to narrow down possibilities
5. Win by guessing the exact code within 12 attempts

### Example Gameplay

```
Guess 1: 1234
  1234 -> position:1 exist:2
```
This means: 1 digit is in the right spot, and 2 other digits are correct but in wrong positions.

## Testing Instructions

### Manual Testing

**Test 1: Valid Input**
- Input: `1234`
- Expected: Game accepts input and provides feedback

**Test 2: Invalid Length**
- Input: `123`
- Expected: Error message "Guess must be 4 digits."

**Test 3: Non-Digit Characters**
- Input: `12ab`
- Expected: Error message "Guess must contain digits only."

**Test 4: Repeated Digits**
- Input: `1123`
- Expected: Error message "Digits must not repeat."

**Test 5: Correct Guess**
- Input: (the actual secret code)
- Expected: Win message displaying the correct key

**Test 6: History Display**
- Make 6+ guesses
- Expected: Only last 6 guesses shown in history

**Test 7: Max Attempts**
- Make 12 incorrect guesses
- Expected: "Game Over!" message with revealed key

### Automated Testing (Optional)

To test the core functions programmatically, add this code to a separate test file:

```python
from mastermind import validate_guess, get_feedback

# Test validation
assert validate_guess("1234") is None
assert validate_guess("123") == "Guess must be 4 digits."
assert validate_guess("112a") == "Guess must contain digits only."
assert validate_guess("1123") == "Digits must not repeat."

# Test feedback
key = "1234"
assert get_feedback(key, "1234") == (4, 0)  # All correct
assert get_feedback(key, "1243") == (2, 2)  # 2 correct position, 2 wrong position
assert get_feedback(key, "5678") == (0, 0)  # None correct

print("All tests passed!")
```

## Game Strategy Tips

- Start with diverse digits to maximize information (e.g., `0123`, `4567`)
- Track which digits are confirmed correct
- Use the position and exist counts to eliminate possibilities
- Pay attention to the guess history to avoid repeating similar patterns

## License

This project is free to use for educational purposes.

## Contributing

Feel free to fork this project and add enhancements such as:
- Difficulty levels (3-digit, 5-digit codes)
- Hint system
- Score tracking
- GUI interface
- Two-player mode

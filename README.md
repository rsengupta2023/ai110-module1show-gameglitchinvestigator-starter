# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [x] The game aims to generate a random number while the user guesses the correct number within 8 attempts with hints of either higher or lower.
- [x] I found 3 bugs:
   - The sidebar showed 8 attempts left while the main page showed 7.
   - The hint logic was broken where in most cases it output higher instead of lower or vice versa.
   - The new game button failed to initiate a new game and take inputs.
- [x] The following fixes were applied:
   - modified the "st.session_state.attempts = 0" to "st.session_state.attempts = 1" which fixed the attempts left bug.
   - For the hints bug, I used AI to refactor the if else logic to make sense.
   - Reset all related session-state values, not just changing the status—because otherwise the old secret number, score, attempts, or history could remain for the new game bug.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. Attempts show 8 left on both side bar and the main view.
2. When a new game is initiated, suppose a random number 88 is generated to guess.
3. User inputs 5
4. Hint shows GO HIGHER!
5. User inputs 92
6. Hint shows GO LOWER!
7. User inputs 88
8. Game shows correct answer, ballons flow up, and The final score of 60 is shown.
9. New game is clicked
10. All outputs cleared. Attempts reset to 8, new number is generated and the game starts again.


**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]

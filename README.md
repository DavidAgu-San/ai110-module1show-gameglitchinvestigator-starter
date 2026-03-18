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

- [ ] Describe the game's purpose
A guessing game that requires players to guess a hidden number within a specific range determined by the chosen difficulty level while managing a limited number of attempts.

- [ ] Detail which bugs you found.

1)The secret number changed every time a user clicked "Submit" because the application script reruns entirely on every interaction

2)The feedback system provided the opposite of the correct hint.

3)The range is hard coded to always be between 1-100 regardless of the difficulty level.

4)The "New Game" button was initially unresponsive and failed to properly reset all session variables.

- [ ] Explain what fixes you applied.

1)Added an if "secret" not in st.session_state check to ensure the secret number is only generated once at the start of the game or when specifically reseted. This will prevent "secret from changing during every rerun.

2)Updated check_guess func. by switching the hints (guess lower, guess higher) to its correct logic. This resulted in the correct hint to be outputed.

3)connected the difficulty settings to the range display and attempt limits. This ensures the instructions shown to the player accurately reflect the current game configuration.

4)Updated new_game button to reset the attempts, secret, score, status, and history within the st.session_state. This made sure the UI was refreshed when the button was clicked.


## 📸 Demo

- [ ] [Insert a screenshot of your fixed, winning game here]
<img width="937" height="449" alt="Guessing Game final" src="https://github.com/user-attachments/assets/e94f7ff7-6c38-441c-b699-38031d3b853e" />


## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]

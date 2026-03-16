# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The amount of tries were incorrect as it corrilated to the different diffculty levels. The next error I noticed was that the range of numbers were suppose to be proportional to the different difficulty levels, however all of the difficulty setting were hard coded to be from 1-100. Another error I noticed was that when you asked for a hint, it gave you the opposite of what it meant. What I mean by this is that when the secret number was lower than the user guess, the system suggested the user to guess higher which is the wrong hint.
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").
1) Hints were the opposite of what they were suppose to be
2) when trying to restart the game by pressing the restart button, nothing would happen.
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Copilot that was already built into my code editor. Athough, if I had further inquiries I would default to Gemini since it is the LLM I have more familiarity to.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
The first and more direct example of AI suggestions that were correct, was that off the bat when I mentioned the hints error, it lead me to the exact code block that controlled the functionality of the hint feature. Then as I gave it more context, it successfully provided me with the solution(switching hints to the correct order) as well as giving me suggestions on more user friendly was of givng the hints(added rocket emoji for higher)
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
THe only suggestion I got that was "incorrect" was when were were working on fixing the bug where the start over button was not functioning. During this instance it did give me a functioning code that would make the button work as it should, however it changed the name of the variables, this caused some of the other features on the app to not work as a result.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I First I soley based my troubleshooting on the actual frontend side of the project, I played the game over 20 time and guess diverse numbers. I also tested all the buttons to make sure they worked fine.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  I then tried using pytest to run my code. I was having trouble so I prompted claude to help me in this case, it told me that the logic file had to be updated in order for the the values from our app.py script to be reflected on the test. It did that and told me what files it made changes on.
- Did AI help you design or understand any tests? How?
Yes it did, it did the majority of the pytest script, however for the manual test( most of the test), were done by me.
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
The secret number changes because the way steamlit works is that it rerun the entire app.py script everytime an input is given. In the case of the secret numbers everytime you guess it rerun the attribute "secret", which is in charge of generating the secret number.

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
I would compare streamlit to a blank sheet and everytime you input a change ( can be in the form of a button, type in a box, exc) it erases itself and rewrite the program all over again.

- What change did you make that finally gave the game a stable secret number?

Creating an if statement that checks if our attribute "secret" exist in our session. if the answer is False, then turn "st.session_state.secret" to a random number.


---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?

I want to use AI to more quickly find what controls or governs a certain feature. This will help me fix the problem faster.


- What is one thing you would do differently next time you work with AI on a coding task?
I would try to learn to tailor my context to better help the problem at hand instead of giving it the context of the whole project. This will help spped up the diagnose stage of the process.

- In one or two sentences, describe how this project changed the way you think about AI generated code.

I learned to organize my though better using AI, as well as comming up with what the real problem is. Lastly, I learned to better understand the structure of the code using AI as a guide.

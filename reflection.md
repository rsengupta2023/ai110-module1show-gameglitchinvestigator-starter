# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input |           Expected Behavior         |     Actual Behavior       | Console Output / Error |
|-------|-------------------------------------|---------------------------|------------------------|
|   None| Sidebar shows 8 attempts allowed    | Attempts left start with 7|       None             |
| 20    | Too Low Hint shown                  | Too High hint shown       | None |
| None| New Game button starts new game | New game doesn't start until page refresh | None |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  - I used Claude extension on vs code
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
  - It properly reported why all the session states need to be reset to enable the new game button to work
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.
  - Claude provided a long list for how to fix the attempts function, but as I was proceeding step by step, I only needed the attempts to show 8 instead of 7. I therefore only addressed that issue first which was a single line change from a 1 to a 0 on line 88.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
  - Ans: I ran the app on browser and checked manually with different inputs.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  - Ans: I initially tried to remove the if statement for the new game and only set it to change the state back to now playing. It didn't work when I checked the debug log, as the button completely stopped updating the secret number.
- Did AI help you design or understand any tests? How?
  - Ans: I did not find this project complex enough to implement any automated tests.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
  - Ans: Streamlit is a python library that helps run web apps using session states that help keep track of progress of a user interaction.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
    - Ans: Line by line reference to AI to suggest bug fixes.
- What is one thing you would do differently next time you work with AI on a coding task?
  - Ans: Try agentic implementations.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
  - Ans: Prompting correctly is the most important part of using AI generated code. Otherwise, it can change or recommend unnecessarily complicated code.

# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  1. when i entered a number that is higer then the secret the program incorrectly tells you to go higher 

  2. when i entered a number that is lower then the secret the program incorrectly tells you to go lower

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input               | Expected Behavior    | Actual Behavior      | Console Output / Error |
|---------------------|----------------------|----------------------|------------------------|

guess 60 secret 50.  Too High” and go lower The game said go higher. No console error


Guess 40, secret 50    “Too Low” and go higher The game said go lower. No console error


Run pytest.    Tests run against my new functions. All tests failed using the original place NotImplementedError



---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?

I used claude sonnect help inspect the program and to understand the session state.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).

One correct suggestion was to run python3 -m pytest tests/, which fixed the import problem.

- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

AI initially suggested changing several parts of the game at once, but I decided to make smaller changes so I could understand each fix. I verified my final logic by running the tests until all three passed.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I considered a bug fixed only after testing the behavior instead of assuming that the code is correct. Once I ran the pytest to check if the winning was too high or too low, all three tests eventually passed. The AI helped me understand the first failure was essentially an import problem, and then I was able to manually test the Streamlit interface to make sure the displays hint matches the results.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?


I would say that Streamlit runs the entire Python script whenever a user tries to interact with it or tries to click a button. A normal variable can then be recreated and reset using things like `st.session_state`, which stores information.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.


I think one habit that I want to reuse is keeping running tests after each small change instead of waiting until the end, because then I can increment and also run my pytest in the terminal with the latest code. I will also ask AI to explain instead of copying every suggestion immediately. This project kind of just showed me that using AI-generated code can look correct, but it can still contain logic and a lot of state bugs, so I needed to test and review it myself.

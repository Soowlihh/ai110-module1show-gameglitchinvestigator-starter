# Project Reflection – Glitchy Guesser

---

## 1. What Was Broken When I Started

**First impressions:**
[Write 2–3 sentences describing what the app looked like the first time you ran it. What did you see on screen? What felt off immediately?]

**Concrete bugs I noticed:**
- **Bug 1 – Wrong difficulty ranges:** The Hard difficulty displayed the wrong number range. [Expand: what did the sidebar show vs. what you expected?]
- **Bug 2 – Reset button didn't work:** Clicking "New Game" did not clear the attempt count. The number of attempts carried over into the new game instead of resetting to zero.

---

## 2. How I Used AI as a Teammate

**Tools used:** Claude (via terminal / Claude Code)

**Example of a correct AI suggestion:**
Claude spotted the difficulty range bug by reading the code and provided a corrected version directly. [Expand: what did you do with that code? Did you run it and test it?]

**Example of a misleading AI suggestion:**
Claude never flagged the scoring logic bug. The `update_score` function rewards a wrong "Too High" guess with +5 points on even-numbered attempts, which makes no sense for a penalty system. Because Claude didn't catch it and the code ran without errors, I assumed the code was fully fixed — but the logic error was still there.

---

## 3. Debugging and Testing My Fixes

**How I decided a bug was really fixed:**
[Write 2–3 sentences. You manually tested by playing the game — what did you actually do? Click through a full game? Try each difficulty? Hit the reset button mid-game?]

**A test I ran and what it showed:**
[Describe one specific manual test — for example, "I selected Hard difficulty and played a full game to check the range shown matched the actual secret number."]

**Did AI help with testing?**
[Honest answer here: Claude provided the fixes but you verified by running the app yourself. Did Claude suggest any specific things to check?]

---

## 4. What I Learned About Streamlit and State

**Why the secret number kept changing:**
[In your own words: Streamlit reruns the entire script from top to bottom every time the user interacts with the page. Without session state, `random.randint` gets called again on every rerun, generating a new secret number each time.]

**Explaining Streamlit reruns to a friend:**
[Write this like you're explaining it to someone who has never coded. Something like: "Imagine every time you click a button, the whole app restarts from scratch..."]

**The fix that gave the game a stable secret number:**
The code already used `if "secret" not in st.session_state` to protect the secret number from being regenerated. [Expand: did you have to change this, or was understanding it the key insight for you?]

---

## 5. Looking Ahead – My Developer Habits

**One habit I want to reuse:**
Manual play-testing — actually running the app and playing through it — was the most direct way to confirm whether a fix worked. [Expand: why was this useful specifically?]

**One thing I'd do differently with AI next time:**
I verified Claude's suggestions by asking Claude if they were correct, which isn't truly independent verification. Next time I would check fixes against a separate source or reason through the logic myself before accepting them.

**How this project changed how I think about AI-generated code:**
AI can produce code that runs without errors but still contains logic bugs that only show up when you think carefully about what the code is actually supposed to do — not just whether it executes.

---

*Built with Streamlit | Debugged with Claude*

![alt text](https://github.com/gruquilla/prime-guess-r/blob/main/primeguessrlogo.jpg)
<br />
<br />
An interactive Jupyter widget game to learn and drill the primes from 1 to 100, using a batch-based memorization system. CC BY-NC-SA.<br />
<br />
Access the Prime Guess-R Notebook: <br />
[Open Version 1.0](https://github.com/gruquilla/prime-guess-r/blob/main/PrimeGuess-r%20Game.ipynb)
<br />
Check requirements: <br />
[requirements.txt](https://github.com/gruquilla/PrimeGuessR/blob/main/requirements.txt)
<br />
Information: Prime Guess-R runs entirely in a Jupyter notebook using `ipywidgets`.

## Table of contents
- [What is Prime Guess-R?](#what-is-prime-guess-r)
- [How to run the project?](#how-to-run-the-project?)
- [Quick preview](#quick-preview)
- [The project in detail](#the-project-in-detail)
- [Batches ordering](#batches-ordering)
- [Potential practical applications](#potential-practical-applications)
- [FAQ](#faq)
- [Limitations and planned developments](#limitations-and-planned-developments)

## What is Prime Guess-R?
Prime Guess-R is a small research/teaching side-project built with Python and `ipywidgets` that turns the memorization of primes from 1 to 100 into a timed guessing game.<br />
The main challenge was to make prime recognition fast and intuitive rather than purely rote, by grouping the primes into four color-coded "batches" that each follow a distinct digit pattern. Instead of memorizing 25 numbers in one block, the learner progresses batch by batch, reinforcing each pattern with dedicated practice before mixing everything together in Global Mode.<br />
<br />
The main features include: <br />
* A menu with 5 modes: Global Mode (1-100) and 4 thematic batches (Black, Green, Red, Purple), each with its own color scheme.
* A 10-second timer per question, with a "Prime" / "Not Prime" choice.
* A scoring system with streak bonuses, live score tracking, and a mastery bar (5,000 points) for each batch.
* Instant feedback on wrong answers, showing the smallest factor pair of composite numbers (e.g. `51 = 3 × 17`) so the mistake is also a mini lesson.
* Persistent per-batch scores within a session, with a "(mastered)" badge once a batch's mastery threshold is reached.

## How to run the project?
- Step 1: Download the latest notebook.
- Step 2: Install the libraries required (listed on the requirements.txt file at the top of this README — mainly `ipywidgets`).
- Step 3: Open the notebook in Jupyter and run the script.
- Step 4: Pick a mode from the menu and start guessing.

## Quick preview
Example of the main menu:
![alt text](https://github.com/gruquilla/prime-guess-r/blob/main/menuprimeguessr.png)

Example of a Batch Mode round in progress:
![alt text](https://github.com/gruquilla/prime-guess-r/blob/main/timer.png)

![alt text](https://github.com/gruquilla/prime-guess-r/blob/main/ex2.png)

## The project in detail
Here is how Prime Guess-R works:
* **Menu: Mode selection** <br />
  _The user is presented with 5 modes: Global Mode, which draws from the full 1-100 range, and 4 batch modes (Black, Green, Red, Purple), each restricted to its own pool of numbers. Batches already pushed past the mastery threshold are flagged "(mastered)" directly on their button._ <br /> <br />
* **Round: Number draw and timer** <br />
  _A number is drawn at random from the active pool (avoiding an immediate repeat where possible), displayed large on screen, and a 10-second countdown starts. The user answers "Prime" or "Not Prime" before time runs out._ <br /> <br />
* **Scoring: Streaks and bonuses** <br />
  _A correct answer is worth a base 50 points. Consecutive correct answers build a streak, which unlocks bonus points at set milestones (10, 15, 20, 30, 40, 50, 60, 70, 80, 90, 100 in a row), up to a +500 bonus. A wrong answer costs 100 points and resets the streak. A missed timer also resets the streak and auto-advances to the next number._ <br /> <br />
* **Feedback: Learning from mistakes** <br />
  _When a guess is wrong, the app shows whether the number was actually prime, and if not, its smallest factor pair (e.g. `96 = 4 × 24`), so every mistake doubles as a quick refresher._ <br /> <br />
* **Progress: Mastery per batch** <br />
  _In batch modes, a progress bar tracks the score toward a 5,000-point mastery threshold. Once reached, the batch is marked "mastered" both in-game and on the main menu. Global Mode tracks a simple running score instead, with no mastery cap._ <br /> <br />

## Batches ordering

### <span style="color:#2c2c2c;">Black Batch</span> : The Foundations
<span style="color:#2c2c2c; font-weight:bold;">2  3  5  7  11  13  17  19</span>

No shortcut here, you need to learn these by heart. They're the exceptions to every rule below (2 and 5 are the only primes with an even or 5 last digit), so once they're memorized, everything else follows a pattern.

### <span style="color:#2e7d32;">Green Batch</span> : 3s and 9s
<span style="color:#2e7d32; font-weight:bold;">23 / 29,  53 / 59,  83 / 89</span>

These tens are separated by 30, and their unit digit is always 3 or 9 (3×3). It's all a question of 3s with the Green Batch.

### <span style="color:#c62828;">Red Batch</span> : 1s and 7s
<span style="color:#c62828; font-weight:bold;">31 / 37,  61 / 67</span>

These tens get harder: remember it's the 30s, doubled to the 60s. Unit digit is always 1 or 7.

### <span style="color:#6a1b9a;">Purple Batch</span> : The Oddities
<span style="color:#6a1b9a; font-weight:bold;">41 / 43 / 47,  71 / 73 / 79,  97</span>

These don't follow a single clean digit rule like the other batches. Treat them as a short separate list to memorize on their own.

* Notice the symmetry; the 40s have the 7 (47) and the 70s have the 9 (79).
* Learn 97 on its own. Remember 91 is a trap, it looks prime but is in fact 7 × 13.

### Why this grouping works
Every prime above 5 has to end in 1, 3, 7, or 9. Any other last digit means it's divisible by 2 or 5. That's why the batches line up by "tens position": Green, Red, and most of Purple are the same repeating pattern showing up every 30 numbers (this is sometimes called the "wheel of 30" in number theory).

## Potential practical applications
For educational and self-practice purposes only:
  * Fast recognition drilling of primes from 1 to 100 for students, teachers, or anyone brushing up on number theory basics.
  * A lightweight, no-setup companion tool for CFA/math/competitive-exam candidates who want automatic mental-math primes reflexes.
  * Streak-based gamification of a rote memorization task, to make repetition less tedious.

## FAQ

**What are the batches?**
A segmentation technique to learn primes from 1 to 100 faster and recognise them. Suggested order:
1. Learn the Foundations (Black)
2. Deal with the 3/9 and 1/7 series (Green, Red)
3. Finish with the Oddities (Purple)
4. Switch to Global Mode to practice everything mixed together

**Shouldn't the 90s be with the Red batch?**
No, 91 is an exception (7 × 13), so lumping the 90s into a "ends in 1" rule would teach a false pattern. 97 is safer learned on its own as part of the Oddities.

**Does the game avoid repeating the same number twice in a row?**
Yes. Each new round draws randomly from the active pool but will retry the draw (up to a few attempts) if it lands on the same number as the previous round, so you rarely see identical back-to-back questions.

**Do my scores carry over if I restart the notebook?**
Within a single run of the notebook, each batch's score is remembered as you switch between modes and the menu. Restarting the Python kernel resets all scores, since nothing is currently saved to disk.

## Limitations and planned developments
* Persisting scores and mastery status to a file so progress survives a kernel restart.
* Adding an adaptive mode where numbers previously answered incorrectly are more likely to reappear.
* Adjusting the streak-bonus curve based on user testing (some milestones may currently feel too far apart).
* Extending the batch system beyond 1-100 for more advanced practice.
* Adding a summary screen at the end of a session showing accuracy and time-per-answer stats.

Code: © G.RUQUILLA - CC BY-NC-SA <br />
This license enables reusers to distribute, remix, adapt, and build upon the material in any medium or format for noncommercial purposes only, and only so long as attribution is given to the creator. If you remix, adapt, or build upon the material, you must license the modified material under identical terms.

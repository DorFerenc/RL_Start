# 🎮 Prisoner's Dilemma - Reinforcement Learning Assignment

## What is this?
Imagine you and a friend are playing a game. Each round, you both secretly choose:
- 👍 **Cooperate** (be nice)
- 👎 **Defect** (be mean)

Then you reveal your choices and get points:

| You | Friend | Your Points |
|-----|--------|-------------|
| 👍  | 👍     | 3 (both win!) |
| 👍  | 👎     | 0 (you got tricked!) |
| 👎  | 👍     | 5 (you tricked them!) |
| 👎  | 👎     | 1 (nobody wins) |

**The Problem**: Should you be nice or mean? It depends on who you're playing with!

**Our Solution**: We use math (Policy Iteration) to find the BEST strategy against different types of players.

---

## What Technologies We Used

| Technology | What It Does | Why We Need It |
|------------|--------------|----------------|
| **Python 3** | Programming language | Write the code |
| **Gymnasium** | RL environment library | Standard way to make games for AI |
| **NumPy** | Math library | Fast calculations |
| **Matplotlib** | Plotting library | Make graphs |
| **Pillow (PIL)** | Image library | Create animations |
| **Pandas** | Data tables | Organize results |

---

## The 4 Opponents We Play Against

1. **ALL_C (Always Nice)** 😇
   - Always cooperates
   - Very easy to exploit!

2. **ALL_D (Always Mean)** 😈
   - Always defects
   - You can't cooperate with them

3. **TFT (Tit-for-Tat)** 🪞
   - Starts nice
   - Then copies what you did last round
   - Famous strategy that won tournaments!

4. **IMPERFECT_TFT (Clumsy Mirror)** 🎲
   - Like TFT but makes mistakes 10% of the time
   - Simulates real-world noise

---

## What We Found

### 1. Short-term vs Long-term Thinking
- If you only care about NOW (low γ): Always defect
- If you care about FUTURE (high γ): Cooperate with TFT

### 2. Memory Doesn't Help (For These Opponents)
- Remembering 2 rounds vs 1 round gives same result
- These opponents only look at your last move anyway

### 3. Forgiveness Works!
- Even when opponent makes mistakes, keep cooperating
- Fighting back makes things worse for everyone

---

## Files in This Project

```
├── assignment1_fnal.ipynb     # Main notebook (run this!)
├── README.md                  # This file
├── convergence_plots*.png     # How the algorithm converges
├── reward_vs_gamma.png        # Rewards at different discount factors
├── visualizations/*           # visuals of the eppisodes 1,2,50
├── RL2026A-Assignment1.pdf    # The Assignment
└── main.tex                   # The math
```

---

## How to Run

1. Open Google Colab: https://colab.research.google.com
2. Upload `assignment1_final.ipynb`
3. Click "Runtime" → "Run all"
4. Wait for all cells to complete
5. All outputs will appear inline!

---

## The Math (Simple Version)

**Policy Iteration** works in 2 steps:

1. **Evaluate**: "How good is my current strategy?"
   - Calculate expected total points from each situation

2. **Improve**: "Can I do better?"
   - Look at each situation
   - Pick the action that gives most points

Repeat until the strategy stops changing. Done! 🎉

---

## Results Summary

| Against | Low γ (0.1) | High γ (0.9) |
|---------|-------------|--------------|
| ALL_C   | Always Defect | Always Defect |
| ALL_D   | Always Defect | Always Defect |
| TFT     | Always Defect | **Always Cooperate!** |
| Imperfect TFT | Always Defect | **Always Cooperate!** |

**Key insight**: When you care about the future, cooperation becomes the smart choice!

---

## Authors

- Student 1: Dor (ID: XXXXXXXXX)
- Student 2: Sara (ID: XXXXXXXXX)

Course: Reinforcement Learning 2026A

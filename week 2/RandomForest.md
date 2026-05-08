# Random Forests

## 1. Ensemble Methods
Instead of one model, you build many and combine their answers.
One decision tree can be wrong or biased — but if you ask 500 trees and take a majority vote, individual mistakes cancel out.
This is why ensembles reduce overfitting.

---

## 2. Bagging (Bootstrap Aggregating)
For each tree:
1. Randomly samples rows with replacement (some repeat, some get skipped)
2. Train a tree on that sample
3. Repeat

> With replacement = draw from a hat, put it back, draw again.

---

## 3. Random Forest vs Decision Tree

| | Decision Tree | Random Forest |
|---|---|---|
| Features per split | All | Random subset |
| Overfitting | High | Low |
| One bad split? | Ruins the tree | Doesn't matter |

---

## 4. Feature Randomness
At each split, the tree only looks at a random subset of features.
This makes each tree different — without it, every tree would be nearly identical and combining them wouldn't help.

---

## 5. Voting & Averaging

**Classification** — each tree votes, majority wins
- Cat, Cat, Dog, Cat → Cat

**Regression** — each tree gives a number, take the average
- 240, 260, 250, 270 → 255

---

## 6. Hyperparameters

| Param | What it does |
|---|---|
| `n_estimators` | Number of trees. More = better but slower. Default: 100 |
| `max_depth` | How deep each tree grows. Leave as `None` to start |
| `max_features` | Features per split. Default: `sqrt(n_features)` |

---

## 7. Feature Importance
Each feature gets a score (0–1) based on how much it improved splits across all trees.
Good for figuring out which inputs actually matter.

Age      0.72
Income   0.48
City     0.21
Gender   0.09

---

## 8. Pros & Cons

**Good**
- Hard to overfit
- Little tuning needed
- Built-in feature importance

**Bad**
- Slow on large data
- Memory heavy
- Less interpretable than a single tree

---

**Q: Why does averaging trees reduce overfitting?**

Each tree overfits to *different* noise (different random sample + features).
Average 500 of them → noise cancels, true signal stays.

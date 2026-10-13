# Cookie Cats A/B Test Analysis

Does moving the first progression gate from level 30 to level 40 affect Day 7 retention?

## Project Overview

This project analyzes a completed A/B test in the mobile game Cookie Cats.

The control group encountered the first progression gate at level 30, while the treatment group encountered it at level 40. The analysis evaluates the impact on player retention and engagement.

## Experiment Groups

- `gate_30` — control group: 44,700 players.
- `gate_40` — treatment group: 45,489 players.

## Metrics

- **Primary metric:** Day 7 retention.
- **Secondary metric:** Day 1 retention.
- **Exploratory engagement metric:** mean game rounds per player.

## Dataset

Source: [Mobile Games: A/B Testing — Kaggle](https://www.kaggle.com/datasets/yufengsui/mobile-games-ab-testing)

The dataset contains 90,189 player records with the following columns:

- `userid` — unique player identifier.
- `version` — experiment group.
- `sum_gamerounds` — number of game rounds played during the observation period.
- `retention_1` — whether the player returned one day after installation.
- `retention_7` — whether the player returned seven days after installation.

## Methods

- Data quality checks, including duplicate users and group assignments.
- Sample Ratio Mismatch (SRM) check.
- Descriptive statistics and visual comparisons.
- Two-sided Z-tests for retention proportions.
- 95% confidence intervals for retention differences.
- Retrospective MDE estimates using control-group retention, actual group sizes, and 80% power.
- Two-sided Welch’s t-test for mean game rounds.

The significance level for metric comparisons was 0.05.

The SRM check returned p = 0.0086, which did not cross the selected SRM threshold of 0.001.

## Results

All differences are calculated as treatment minus control (`gate_40 − gate_30`).

| Metric | Control | Treatment | Difference | p-value |
|---|---:|---:|---:|---:|
| Day 7 retention | 19.02% | 18.20% | −0.82 pp | 0.00155 |
| Day 1 retention | 44.82% | 44.23% | −0.59 pp | 0.0744 |
| Mean game rounds* | 51.34 | 51.30 | −0.0433 rounds | 0.9495 |

*pp = percentage points.*

- **Day 7 retention:** statistically significant decline. The 95% confidence interval for the difference is **[−1.33, −0.31] pp**.
- **Day 1 retention:** no statistically significant difference detected. The 95% confidence interval is **[−1.24, +0.06] pp**.
- **Mean game rounds:** no statistically significant difference detected.

Non-significant results do not establish that the groups are equivalent.

*The game-round analysis excludes one player with 49,854 rounds. Both retention analyses include this player.*

## Recommendation

**Do not roll out the gate at level 40 in its current form.**

The treatment significantly reduced Day 7 retention, the primary metric. The additional analyses provide no evidence of an improvement that would change this recommendation.

## Limitations

- No experiment assignment dates or pre-experiment data are available. Experiment duration, temporal trends, complete follow-up windows, and a separate A/A test could not be verified.
- MDE estimates are retrospective sensitivity assessments based on observed control-group retention, not predefined business targets.
- The extreme game-round value was excluded without confirmation that it was a data error. The game-round findings apply to the filtered dataset.
- Day 1 retention and game rounds are supplementary analyses; the rollout recommendation is based on Day 7 retention.
- Game rounds do not directly measure the highest level reached or whether a player encountered the gate.

## Tools

Python, pandas, SciPy, statsmodels, Matplotlib, Seaborn, and Jupyter Notebook.

## Project Status

Completed.
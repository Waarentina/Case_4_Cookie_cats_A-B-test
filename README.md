# Case_4_Cookie_cats_A-B-test
A/B test analysis for the mobile game Cookie Cats. Does moving the gate from level 30 to level 40 have a statistically significant effect on 7-day player retention?
# Cookie Cats A/B Test Analysis

## Project Overview

This project analyzes the results of an A/B test conducted in the mobile game Cookie Cats.

The game originally placed its first progression gate at level 30. During the experiment, some players continued to see the gate at level 30, while others saw it at level 40.

The goal of the analysis is to determine whether moving the gate affects player engagement and retention.

## Research Question

Does moving the gate from level 30 to level 40 have a statistically significant effect on 7-day player retention?

## Experiment Groups

- `gate_30` — control group;
- `gate_40` — treatment group.

## Metrics

- **Primary metric:** 7-day retention;
- **Secondary metric:** 1-day retention;
- **Engagement metric:** number of game rounds played.

## Dataset

The dataset contains user-level results of the completed experiment.

Source: [Mobile Games: A/B Testing — Kaggle](https://www.kaggle.com/datasets/yufengsui/mobile-games-ab-testing)

### Columns

- `userid` — unique player identifier;
- `version` — experiment group (`gate_30` or `gate_40`);
- `sum_gamerounds` — number of game rounds played during the observation period;
- `retention_1` — whether the player returned one day after installation;
- `retention_7` — whether the player returned seven days after installation.

## Analysis Plan

1. Validate the dataset and check data quality.
2. Check for duplicate users and inconsistent group assignments.
3. Perform a Sample Ratio Mismatch check.
4. Compare metrics between the control and treatment groups.
5. Test the statistical hypotheses.
6. Calculate effect sizes and confidence intervals.
7. Compare statistical and practical significance.
8. Provide a product recommendation.

## Limitations

The dataset does not contain experiment assignment dates or pre-experiment data. Therefore, it is not possible to validate the experiment duration, temporal trends, conversion-window maturity, or the results of a separate A/A test.

## Project Status

Work in progress.
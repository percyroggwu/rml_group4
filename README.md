# Responsible Machine Learning - Group 4

This repository contains Group 4 solutions for Assignments 1, 2, and 3 in the Responsible Machine Learning course.

## Repository Overview

The assignments focus on core fairness and governance questions in machine learning, including:

- The mismatch between optimization targets and real human objectives
- The limits of feature-level explainability for fairness assessment
- Gairness trade-offs between calibration and equal error rates

## Contents

- RML - assignment 1 - group 4.md
- RML - assignment 2 - group 4.md
- RML - assignment 3 - group 4.md
- RML - assignment 4 - group 4.docx
- RML - assignment 5 - group 4.md

## Assignment Summaries

### Assignment 1 - Proxy mismatch and optimization

This assignment examines when minimizing training loss is equivalent to maximizing human utility, and when that alignment breaks down.

Main ideas:
- A model is aligned only when the one that minimizes loss also maximizes true human utility.
- A counterexample shows that the lowest-loss model may not be the one with the highest real-world value.
- The business interpretation uses automated resume screening, where optimizing prediction error on past hiring decisions may reproduce historical bias instead of selecting the best long-term candidates.

### Assignment 2 - Explainability, proxies, and fairness

This assignment analyzes why explainability outputs alone are not enough to prove fairness.

Main ideas:
- A Shapley value of zero for race does not mean the model is fair.
- Other variables can still act as racial proxies and generate unequal outcomes.
- The discussion uses a COMPAS-style example to show how bias can shift into correlated features such as prior arrests.
- Fairness evaluation should therefore include both feature attribution and group-level outcome metrics such as false positive rate parity.

### Assignment 3 - Calibration and fairness trade-offs

This assignment studies the relationship between calibration, false positive rate parity, and false negative rate parity.

Main ideas:
- Calibration within groups means that the same score should have the same meaning across groups.
- FPR parity and FNR parity require equal error rates across groups.
- When base rates differ, a non-trivial classifier cannot generally satisfy calibration, equal FPR, and equal FNR at the same time.
- The assignment connects this result to the COMPAS case and discusses when calibration may be preferred over FPR parity from a governance perspective.

### Assignment 4 - Calibration and fairness trade-offs

### Assignment 5 - Calibration and fairness trade-offs

## Summary

The purpose of this repository is to document concise written solutions for major Responsible Machine Learning topics, combining mathematical reasoning with practical business and governance interpretation.

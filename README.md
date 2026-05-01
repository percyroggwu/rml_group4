# Responsible Machine Learning - Group 4

This repository contains Group 4 solutions for Assignments 1-5 in the Responsible Machine Learning course.

## Repository Overview

The assignments focus on core fairness, security, and governance questions in machine learning, including:

- The mismatch between optimization targets and real human objectives
- The limits of feature-level explainability for fairness assessment
- Fairness trade-offs between calibration and equal error rates
- Audit frameworks for drift, generalization failure, subgroup disparity, and robustness stress
- Security and privacy risks, including evasion, poisoning, backdoor attacks, differential privacy, and membership inference

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

### Assignment 4 - Audit Framework

This assignment develops a sociotechnical audit framework for evaluating predictive models after deployment, using the COMPAS pipeline as an illustrative case.

Main ideas:
- Strong aggregate performance is not sufficient for defensible deployment.
- Predictive systems must be evaluated for drift, generalization failure, subgroup disparity, and robustness stress.
- Audit metrics should connect technical evidence to governance actions such as monitoring, recalibration, retraining, redesign, or escalation.
- The COMPAS case shows how approximate calibration can coexist with unequal subgroup error rates, especially higher false positive rates for Black defendants and higher false negative rates for White defendants.
- The assignment proposes less discriminatory alternatives, including feature/model redesign and decision-system redesign with human review and continuous monitoring.

### Assignment 5 - Security

This assignment examines security and privacy risks in responsible machine learning systems, using the COMPAS deployment pipeline as the main example.

Main ideas:
- The COMPAS pipeline can be attacked at multiple stages, including data collection, data entry, model training, deployment, and decision use.
- Evasion attacks can occur when individuals manipulate inputs at prediction time.
- Data poisoning and backdoor attacks are higher-risk because they can corrupt the training data or model behavior at scale.
- Differential privacy can reduce membership inference risk, but it may also worsen minority-group performance when privacy noise weakens underrepresented-group signals.
- Governance should prioritize access control, logging, validation, anomaly detection, independent audits, and backdoor testing.

## Summary

The purpose of this repository is to document concise written solutions for major Responsible Machine Learning topics, combining mathematical reasoning with practical business and governance interpretation.

# RML - Assignment 1 - Group 4 - Summary

This repository contains the solution for Group Homework 1 in the Responsible Machine Learning course.

## Task
The assignment analyzes the alignment problem between:
**Training loss**
**Human utility**

The homework includes three parts:
1. State a condition under which minimizing loss is equivalent to maximizing human utility
2. Provide a counterexample where the two objectives select different models
3. Interpret the mismatch in a real-world ML setting

## Solution
Our solution shows that alignment holds when the model with the lowest training loss is also the one with the highest human utility. We also provide a counterexample to show that this is not always true.

For our interpretation for a real world scenario, we use automated resume screening in hiring as an example. 
A model may minimize prediction error on past hiring decisions while still failing to maximize the true human objective, such as long-term employee performance, fairness, and better hiring outcomes.

## File
RML - assignment 1 - group 4.md

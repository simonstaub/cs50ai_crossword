problem: https://cs50.harvard.edu/ai/2024/projects/3/crossword/

### Crossword Puzzle Solver – CS50 AI Project
This project is part of Harvard’s CS50’s Introduction to Artificial Intelligence with Python and focuses on building an AI that can generate complete crossword puzzles from a given grid structure and a list of words.

## Problem Overview
The challenge is to fill in a crossword puzzle such that:

Each horizontal and vertical slot is filled with a word from a given vocabulary list.

All constraints are satisfied:

Words fit the length of their assigned slot.

Intersecting words share the same character at overlapping positions.

No word is used more than once.

This is a classic Constraint Satisfaction Problem (CSP), where each word slot is a variable and possible fitting words are the domain.

## Solution Approach
The AI solves the crossword using the following constraint satisfaction techniques:

# 1. Node Consistency
Ensures that each word slot (variable) only allows words of the correct length.

# 2. Arc Consistency (AC3 Algorithm)
Removes values from domains if they don't have compatible options in neighboring (intersecting) slots.

# 3. Backtracking Search
A recursive depth-first search algorithm that tries to assign words to each slot:

Uses Minimum Remaining Values (MRV) and Degree Heuristic to choose the next variable.

Uses Least Constraining Value (LCV) to decide the order of values.

Continues until a complete and consistent assignment is found or all options are exhausted.

## How to Use
Requirements
Python 3.12

Pillow library for image generation (pip install pillow)

# Run the Generator
python generate.py data/structure1.txt data/words1.txt output.png

# Files
crossword.py: Defines the grid, variables, structure, and overlap logic.

generate.py: Implements the CSP solver and puzzle generation.

data/: Contains example structures and word lists.



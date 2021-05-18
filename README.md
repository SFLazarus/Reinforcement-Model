# Reinforcement-Model
Built a Q-learning model to solve a maze while collecting treasure and reaching goal state in minimum steps avoiding obstacles

## Project 4 - Treasure Hunters Inc.
###  We do the treasure hunting and monster fighting for you
1. Set up a new git repository in your GitHub account
2. Think up a map-like environment with treasure, obstacles and opponents
3. Choose a programming language (Python, C/C++, Java)
4. Formulate ideas on how reinforcement learning can be used to find treasure efficiently while avoiding obstacles and opponents
5. Build one or more reinforcement policies to model situational assessments, actions and rewards programmatically
6. Document your process and results
7. Commit your source code, documentation and other supporting files to the git repository in GitHub

# Environment
    Labels:::>
    Opponent: '_E_'
    Treasure: '_$_'
    OBSTACLE: '|-|'
    Empty space: '---'

    ['---', '---', '---', '---', '_$_', '_E_', '|-|']
    ['_$_', '_E_', '---', '---', '---', '---', '_E_']
    ['---', '---', '_$_', '---', '|-|', '---', '---']
    ['---', '---', '_E_', '---', '|-|', '---', '---']
    ['---', '_$_', '---', '---', '|-|', '---', '---']
    ['---', '---', '---', '_$_', '|-|', '---', '---']
    ['---', '---', '---', '---', '---', '---', 'END']

# Strategy 1:

## Rewards

- Let us punish with -5, if agent encounters its opponent
- Let us punish with -3, if agent crashes into obstacle
- Let us reward with 1, if agent finds treasure
- Let us reward with 100, if agent reaches goal state
- Let us not motivate our model to finish quick by not punishing for each step, i.e., we give 0 reward for every step

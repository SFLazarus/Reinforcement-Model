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
    Goal state: 'END'

    ['---', '---', '---', '---', '_$_', '_E_', '|-|']
    ['_$_', '_E_', '---', '---', '---', '---', '_E_']
    ['---', '---', '_$_', '---', '|-|', '---', '---']
    ['---', '---', '_E_', '---', '|-|', '---', '---']
    ['---', '_$_', '---', '---', '|-|', '---', '---']
    ['---', '---', '---', '_$_', '|-|', '---', '---']
    ['---', '---', '---', '---', '---', '---', 'END']


# Strategy 1:
## Rewards

- Let us punish with -50, if agent encounters its opponent
- Let us punish with -30, if agent crashes into obstacle
- Let us reward with 0, if agent finds treasure
- Let us reward with 100, if agent reaches goal state
- To motivate agent to finish quick, we shall punish every step with -1

# Strategy 2:
## Rewards

- Let us punish with -5, if agent encounters its opponent
- Let us punish with -3, if agent crashes into obstacle
- Let us reward with 1, if agent finds treasure
- Let us reward with 100, if agent reaches goal state
- Let us not motivate our model to finish quick by not punishing for each step, i.e., we give 0 reward for every step

# Results:
## Using Reward policy 1:

        ::::Labels:::>

        Opponent: '_E_'
        Treasure: '_$_'
        OBSTACLE: '|-|'
        Empty   : '---'
        Agent  : '_P_'
        Agent with treasure : '$P$'
        Agent reached goal : '^P^'

        Initial Map
        ['---', '---', '---', '---', '_$_', '_E_', '|-|']
        ['_$_', '_E_', '---', '---', '---', '---', '_E_']
        ['---', '---', '_$_', '---', '|-|', '---', '---']
        ['---', '---', '_E_', '---', '|-|', '---', '---']
        ['---', '_$_', '---', '---', '|-|', '---', '---']
        ['---', '---', '---', '_$_', '|-|', '---', '---']
        ['---', '---', '---', '---', '---', '---', 'END']
        Result:
        starting point: row->1 column->1
        ['_P_', '---', '---', '---', '_$_', '_E_', '|-|']
        ['$P$', '_E_', '---', '---', '---', '---', '_E_']
        ['_P_', '_P_', '$P$', '_P_', '|-|', '---', '---']
        ['---', '---', '_E_', '_P_', '|-|', '---', '---']
        ['---', '_$_', '---', '_P_', '|-|', '---', '---']
        ['---', '---', '---', '$P$', '|-|', '---', '---']
        ['---', '---', '---', '_P_', '_P_', '_P_', '^P^']
        total steps: 13
        total treasure collected 3

## Using Reward policy 2:
        ::::Labels:::>

        Opponent: '_E_'
        Treasure: '_$_'
        OBSTACLE: '|-|'
        Empty   : '---'
        Agent  : '_P_'
        Agent with treasure : '$P$'
        Agent reached goal : '^P^'

        Initial Map
        ['---', '---', '---', '---', '_$_', '_E_', '|-|']
        ['_$_', '_E_', '---', '---', '---', '---', '_E_']
        ['---', '---', '_$_', '---', '|-|', '---', '---']
        ['---', '---', '_E_', '---', '|-|', '---', '---']
        ['---', '_$_', '---', '---', '|-|', '---', '---']
        ['---', '---', '---', '_$_', '|-|', '---', '---']
        ['---', '---', '---', '---', '---', '---', 'END']
        Result:
        starting point: row->1 column->1
        ['_P_', '---', '---', '---', '_$_', '_E_', '|-|']
        ['$P$', '_E_', '---', '---', '---', '---', '_E_']
        ['_P_', '_P_', '$P$', '_P_', '|-|', '---', '---']
        ['---', '---', '_E_', '_P_', '|-|', '---', '---']
        ['---', '_$_', '---', '_P_', '|-|', '---', '---']
        ['---', '---', '---', '$P$', '|-|', '---', '---']
        ['---', '---', '---', '_P_', '_P_', '_P_', '^P^']
        total steps: 13
        total treasure collected 3

# Conclusion and Future Developments:

- Our model performed best with the current reward policy we have good results in the end.
- In future we can try to move the enemy everytime and agent has to escape enemy.


# Project Structure:
### Readme.md
- Project description
### Notebooks
- Jupyter Notebook implementing Reinforcement model using strategy-1.
- Jupyter Notebook implementing Reinforcement model using strategy-2.
### Requirements.txt
- Info about Tools, frameworks and libraries required to reproduce the work flow

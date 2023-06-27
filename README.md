# The Game of Hog

A project I made for CIS 61 @ Laney College. The game is played between two players who take turns rolling dice to score points. The goal of the game is to be the first player to reach 100 points.


## Simulator

### Taking Turns

The `roll_dice` function rolls dice for a specified number of times and returns the sum of the outcomes. If a 1 is rolled at least once, it returns 1 (Pig out). The function takes the following parameters:

- `num_rolls`: The number of dice rolls to be made.
- `dice`: A zero-argument function that returns an integer outcome.

The `take_turn` function simulates a turn by rolling a specified number of dice. If the number of rolls is 0, it performs Free bacon, which means it returns 1 plus the maximum digit of the opponent's score. The function takes the following parameters:

- `num_rolls`: The number of dice rolls to be made.
- `opponent_score`: The total score of the opponent.
- `dice`: A function that returns an integer outcome.

### Playing a Game

The `select_dice` function selects a six-sided dice unless the sum of the current player's score and the opponent's score is a multiple of 7, in which case it selects a four-sided dice (Hog wild). The function takes the following parameters:

- `score`: The current player's score.
- `opponent_score`: The opponent's score.

The `other` function returns the other player's number, given a player's number (0 or 1).

The `play` function simulates a game and returns the final scores of both players. The function takes the following parameters:

- `strategy0`: The strategy function for Player 0, who plays first.
- `strategy1`: The strategy function for Player 1, who plays second.
- `goal`: The goal score of the game (default is 100).

## Strategies

### Basic Strategy

The `always_roll` function returns a strategy that always rolls a specified number of dice. The function takes the following parameter:

- `n`: The number of dice to be rolled.

### Experiments

The `make_averaged` function returns a function that returns the average value of a given function when called. It takes the following parameters:

- `fn`: The function to be averaged.
- `num_samples`: The number of samples to be used for averaging (default is 1000).

The `max_scoring_num_rolls` function determines the number of dice that gives the highest average turn score by calling `roll_dice` with the provided dice. It prints the average scores for different numbers of dice and returns the number of dice that yields the highest average turn score. It takes the following parameter:

- `dice`: The type of dice to be used (default is a six-sided dice).

The `winner` function returns 0 if `strategy0` wins against `strategy1`, and 1 otherwise. It takes the following parameters:

- `strategy0`: The strategy function for Player 0.
- `strategy1`: The strategy function for Player 1.

The `average_win_rate` function returns the average win rate (between 0 and 1) of a given strategy against a baseline strategy. It takes the following parameters:
- `strategy`: The strategy function to be evaluated.
- `baseline`: The baseline strategy function to compare against.
- `num_battles`: The number of games to be played for evaluation (default is 1000).


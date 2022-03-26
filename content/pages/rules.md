---
createdAt: 2022-03-26T11:52:50.558Z
title: Rules
description: Damath Online Game is an online game base on the official board
  game made by Filipino Damath.
---

### How to win?
- The winner will be the player with greater accumulated final total score
- Opponent Player surrendered (not yet implemented).

### Normal Move
- All move should be one block forward diagonal, except for Dama chips.

### Dama
- A chip can became a Dama when the chip reach the end of the row.

### Dama Move
- Unlike normal chip, dama can move forward or backward diagonally as far it can go as long the box is not occupied.

### Taking / Eating Opponent Chips
#### Eat First
- A chip that can eat should be the move of the player.
- Eating a chip, the eater will jump to the next box.
- Eating chip can be forward or backward.

#### Dama Eat First
- Interns of priority for eating a chip, a Dama chip that can eat opponent chip should be the first.

#### Eat More First
- When in terms of eat first either the chip is Dama or not, the chip that will eat more should be the move of the current player.

### Scoring
- Once you eat/take opponents chips you will accumulate a score.
- The score will be base on the value of chip who ates and eaten, with the operation where the chip landed.

**Format**
score = (chip who eat) (operation) (chip that was eaten)

**Example**
- When a chip with value 9 eaten a chip with value 10 and landed on operation -. You will then accumulate a score -1.
- score: 9 - 10 = -1

#### Scores for Dama
- When a dama eats a normal chip or normal chip eats a dama, the score will be doubled (x2).
- When a dama eats a dama, the score will be quadruple (x4).

### Game Over
The game will be over when
- The current player don't have chips anymore
- The current player has no more possible moves
- The player has only one 1 chips, and made 5x repeating moves (not yet implemented).
- 20 minutes has passed (not yet implemented)
- Player surrendered (not yet implemented)
- Both Player agreed to finish the game (not yet implemented)

### Final Total Scores
- The final total score will be computed once the game is over.
- The final total score will determine the winner of the game
- The final total score will be base on the sum of the score made by eating and remaining chips.

**Example**

Player 1 accumulated a total score of 100 via eating opponents chips and after the game is over,
player then chips 9 5 1 remains in the board.
This chip will be added to total score, so the final score will be **100 + 9 + 5 + 1 = 115**

This will also be applied to Player 2

### 20 Second Move (not yet implemented)
- Each move should only take 20 seconds.
- When the current player unable to make the move, the opponent player will do the move for the player.

### 20 Minutes Game (not yet implemented)
- When a total of 20 minutes has passed the game will be game over.

### Touch Move (not yet implemented)
- When a current player, touch (click) the chip with possible move. It should move it.


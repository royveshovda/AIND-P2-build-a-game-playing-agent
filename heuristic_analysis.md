Heuristic Analysis
===========================
By Ry Veshovda
--------------

The theory I worked from was that the custom score would benefit from a weighted result between #my-moves vs #opponent-moves.
I tested this theory using different ratios. The reasoning is that #my-moves is to be considered positive, and more likely to win with many available moves.
It should also be considered on the negative side #opponent-moves. How much each of these parameters are weighted was varied and tested individually.

The function is the following:
f1 * #mo-moves - f2 * #opponent-moves
I ran three different values for f1 and f2.
The ratios I tested are listed below, together with their percentage result in the sections starting with custom_score.
Two of the heuristic functions from the sample players implementation are listed first for reference.


## Results:
Results are written only as percentage from running tournament.py, and reflects the number of wins.
### sample_players.improved_score (baseline):
66.43%

### sample_players.open_move_score (baseline):
55.71%

### custom_score_weighted_1.5_to_1:
68.57%

### custom_score_weighted_1_to_2:
68.57%

### custom_score_weighted_1_to_1.5:
70.71%

## Conclusion
Running the tests shows the best ratio to be 1:1.5 (#my-moves:#opponent-moves).
The result shows that function to beat the benchmark of being better than the ID_Improved agent player, which uses the first baseline heuristic function.
This proves the theory I had about a weighted ratio between #my-moves and #opponent-moves is an good heuristic function.
#### Reason 1:
It increases the heuristic value when my player has many open moves and possibilities to move.
#### Reason 2:
It penalizes the value when opponent has many open moves and possibilities to move.
#### Reason 3:
It considers an equal weight between the number of moves to favorite opponent. A weight shifted toward penalizing opponent moves more gave the best results. But only slightly. This probably means that very different ratio in a situation is rare and hard to find. The heuristic function needs to find the positions with only a small advantage and run with those.

This supports the claim from the lectures that you should keep your friends close, but your enemies closer (by a small factor of 0.5).

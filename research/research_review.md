Research review for the paper: Deep Blue by the IBM Watson Team
===========================
By Roy Veshovda
--------------

# Deep Blue by the IBM Watson Team
The goal of the IBM Watson team was very simple: Defeat the human world champion in a regulation match.
More specifically the IBM Watson team designed a computer called Deep Blue II to take on the chess world champion Gary Kasparov in a six-game match in 1997.

Similar attempts had been made in the years prior to this match, where the computer always had lost for the human player in the game of chess.

Deep Blue II from IBM Watson became the first computer to beat a human reign world champion in the game of chess.
This was a milestone for all AI research, and also got a lot of attention from the rest of the world.

One of the reasons chess was such an interesting challenge for AI researchers (and still is), is because of the enormous search space that exists in chess. It is not feasible to search all the way to end game, due to the branching factor. At least not today, and certainly not in 1997. IBM Watson Deep Blue II implemented a dedicated chess search chip, and a lot of clever search strategies to achieve this victory. The paper describes the design in detail.

The system design in Deep Blue II was a distributed setup with 30 nodes, where one of the nodes acted as a master. And more than 500 processors in total.
The master did the initial search, and then sent positions to the other nodes for deeper searching.
Depending on the current position on the board, Deep Blue could search between 100 and 200 million positions per second.

Deep Blue relies on many of the ideas developed in earlier chess programs, including quiescence search, iterative deepening, transposition tables, and NegaScout. The last two methods are referenced in the paper.
From the lectures we recognize two of these search functions. Namely quiescence search and iterative deepening. Iterative deepening is used to go gradually deeper when searching. For each iteration the result is kept, to make sure the search always have a result to return (in case time runs out). This was combined with quiescence search to make sure the iterative deepening is not ran for too long. Quiescence would make sure that if the results from iterative deepening seems to stabilize, the search terminates (at least in that branch), to free up resources to be used along other branches.

It is also interesting to note that the evaluation function was implemented in hardware, to further speed up the execution time.

The search function in itself was implemented in a hybrid style, partly hardware, and partly software.

The conclusion of the paper is that the match outcome was not the result of a single factor. This was a combination of all the pieces.
The team also learned that many of the pieces could be further improved to provide even better result.

At the end of the day, the IBM Watson team behind Deep Blue II had found a way to beat a human world champion in the game of chess.

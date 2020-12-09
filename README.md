# tic-tac-toe-NN-and--z3-verification
The goal of the assignement is to create a neural netwrok that classifies moves of the first player in a tic-tac-toe games are good or bad(defined below). Then, verify if the given neural network has done some interesting things(also given below).


See the board as a list of integers 0(no one has played),1(player 1 has played here), and 1(player 2 has played here).
eg: [1,1,1,2,2,2,0,0,0] means the first row is occupied by player 1, second row by player 2, and the third is empty(of cpurse such a situation can't happen in an actual game).

We're only considering those configurations where the number of 1's and 2's are equal, both either two or three. We want to train a network to predict a good move for player 1, given a valid configuration. A move involves simply replacing a 0 with 1.

Good/bad states:
A move is bad if (i)there's a way for player 1 to win at this stage and it does not make a winning move, or (ii) there's no way for player 1 to win at this stage; however, player 1's move allows player 2 to win from the resulting configuration in one move.

A move that is not bad is considered good.


Properties considered:
Does there exist an input (a valid configuration, and an index for player 1's move) which is classified as good by the network, but from the configuration resulting from it, it is possible for player 2 to make one move and win?

Does there exist an input, where the configuration has the center cell and at least one of the corner cells marked by player 1, which is classified as good by the network, but from the configuration resulting from it, it is possible for player 2 to make one move and win?

------------------------------

In the ipynb file, the cell marked '1' is generating the data. This generates all configurations where each player has moved twice,
or where each player has moved thrice. This includes cases like [1,1,1,2,2,2,0,0,0] as well. We will get rid of such cases where
the game is already over in the next part.


The '1...z3' part constructs configurations along with the good/bad value, along with getting rid of the case mentioned above.


2 uses tensorflow to make a network, 3 does question 3, and 4 does question 4.


Run in order.

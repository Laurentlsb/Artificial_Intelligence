# Artificial_Intelligence
ELEC 557 Rice University (&amp; UC Berkeley)  
Textbook: Artificial Intelligence A Modern Approach (3rd edision)

## Contents
* Adversarial Search
	* game
	

# Adversarial Search  
## Game  
### Intro
In this chapter we cover **competitive environments**, in which the agents’ goals are in conflict, giving rise to **adversarial search** problems—often known as **games**.  

In AI, the most common games are of a rather specialized kind—what game theorists call deterministic, turn-taking, two-player, ***zero-sum games*** of ***perfect information*** (such as chess). In our terminology, this means deterministic, fully observable environments in which two agents act alternately and in which the utility values at the end of the game are always equal and opposite. For example, if one player wins a game of chess, the other player necessarily loses. It is this opposition between the agents’ utility functions that makes the situation adversarial.  

We first consider games with two players, whom we call **MAX** and **MIN** for reasons that will soon become obvious. MAX moves first, and then they take turns moving until the game is over. At the end of the game, points are awarded to the winning player and penalties are
given to the loser. A game can be formally defined as a kind of search problem with the following elements:  
* `S0`: The **initial state**, which specifies how the game is set up at the start.
* `PLAYER(s)`: Defines which player has the move in a state.
* `ACTIONS(s)`: Returns the set of legal moves in a state.
* `RESULT(s, a)`: The **transition model**, which defines the result of a move. (Or denoted as `Vopt(s, a)`, frequently used in Devika's slides)
* `TERMINAL-TEST(s)`: A **terminal test**, which is true when the game is over and false otherwise. States where the game has ended are called **terminal states** (like `isEnd(S)`)
* `UTILITY(s, p)`: A utility function (also called an objective function or payoff function), defines the final numeric value for a game that ends in terminal state s for a player p.

#### Note: 
A **zero-sum game** is (confusingly) defined as one where the total payoff to all players is the ***same*** (actually not Zero) for every instance of the game. Chess is zero-sum because every game has payoff of either 0 + 1, 1 + 0 or 0.5 + 0.5 (draw).  

* Zero-sum games:  
	* Adversarial, pure competition: win for a player is a loss for the other player and vice-versa.  
	* For a two player game, the sum of the utilities of a state to the two players is zero. So if state has utility +2 for player 1, it has utility -2 for player 2. In game tree shown on previous slide, only utilities for player 1 are shown – the utilities for player 2 are implied. (这里只是说图中的utility只是针对player 1而言的，对于player 2应该是负值，不是说player 1可以提前知道utility)
	
* Non zero-sum games
	* Players have independent utilities; so players are not fighting over one prize.  Payoffs are tuples of utilities – the length of the tuple is the number of players. It is possible to have a win-win situation. 
	* Cooperation, indifference, competition and other strategies are possible.

The initial state, ACTIONS function, and RESULT function define the **game tree** for the game—a tree where the nodes are game states and the edges are moves.  

### A Game Tree
![image](https://github.com/Laurentlsb/Artificial_Intelligence/blob/master/img_folder/game%20tree.png)
![image](https://github.com/Laurentlsb/Artificial_Intelligence/blob/master/img_folder/two%20players.png)



























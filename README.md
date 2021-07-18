# 3rd International AIWolf Contest: The Sajin Agent

**Sajin** is an agent participating in the 3rd International [AIWolf](http://aiwolf.org/en/3rd-international-aiwolf-contest) Contest, whose goal is to develop an AI agent for the [Werewolf](https://werewolf.chat/) game, that can perform reliably well against other AI agents.

Out agent is named after [Sajin Komamura (狛村 左陣)](https://bleach.fandom.com/wiki/Sajin_Komamura), a werewolf character from the Japanese anime and manga, referred to as "Bleach".

This repository contains the source code for the **Sajin** agent.

# How does Sajin work ?
The **Sajin** agent follows several baseline behaviours, which are intertwined together so as to yield the creation of the **Sajin** agent.
We provide a brief outline of these concepts in the following subsections.

## Stochastic Bayesian Deep Q-Network (SBDQN)
The proliferation of Reinforcement Learning (RL) algorithms, as means for solving Markov decision process (MDP) problems, has flourished a trade-off between several substantial factors affecting their performance, such as exploration, exploitation, statistical efficiency, computational expense, uncertainty and estimation bias. As a mitigation, we put forth the Stochastic Bayesian Double Deep Q-Network (SBDDQ), a novel model which attempts to bridge the gaps between those challenges. Where each existing method solely solves a subset of such factors, SBDDQ intertwines several techniques so as to make up for the union of their shortcomings. 

## The Reinforcement Learning Framework for the Werewolf Game
The consideration of RL yields the presence of an action and a state set. 

### State Space
Whereas the state set is derived from the [AIWolf Protocols](http://aiwolf.org/control-panel/wp-content/uploads/2021/05/Regulation_2021_1.2.3.pdf), the later is broadly illustrated in this section. The agents' perception of the environment stems from the state space, which is generated by multiple elements. A state is represented by a matrix, extracted from conversation history. Such a matrix could be roughly divided into two central components, on which we elaborate in the following subsections.
#### Attitude
We regard the attitude of player `i` towards player `j`, as outlined subsequently:
- `SpecialAbility(i,j)` -- Whether player `i` said he utilized his special ability for player `j` or not. Clearly, this feature applies to either a Seer, a Medium or a Bodyguard. which own a special ability.
- `Vote(i,j)` -- Whether player `i` said he voted for player `j` or not.
- `Estimate(i,j)` -- Whether player `i` estimated that player `j` is a werewolf or not. 
- `Guarded(i,j)` -- Whether player `i`, which is a bodyguard, managed to guard player `j`.
Features of this sort are all assigned with a Boolean value of either `0` or `1`, and are stored in a three-dimensional array, denoted by `x_3d`. Each specific attitude is assigned with a numerical value `l` (as depicted in the implementation), where `x_3d`'s `(i,j,l)`-th element corresponds to `i`'s `l`-th attitude towards `j`.


# Contents of this repo

- [/server](server) : the AIWolf server that run Werewolf games with several agents
- [/killerQueen](killerQueen) : code source of the Killer Queen agent
- [/other_agents](other_agents) : code source of other public agents, for testing purpose
- [/archive](archive) : older versions of Killer Queen

# How to run a test game

1. Configure the game's settings in `gameSettings.ini`. follow the format specified to choose games composition (agents algorithms and roles). Here are useful parameters:
  - `game` (int) : number of games to simulate

  - `log` (path) : path to the folder where the server will write game logs

  - `view` (bool) : use the GUI to follow the course of the game (Japanese)


2. Start the server.
* Windows : launch [RUN.bat](RUN.bat) or [server/AutoStarter.bat](server/AutoStarter.bat)
* Linux : launch [RUN.sh](RUN.sh) or [server/AutoStarter.bat](server/AutoStarter.bat)

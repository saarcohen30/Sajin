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

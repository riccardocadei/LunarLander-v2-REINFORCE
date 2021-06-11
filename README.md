# LunarLander-v2-REINFORCE

The repository contains the code for the Final project of [Artificial Neural Network (CS-456)](https://edu.epfl.ch/coursebook/en/artificial-neural-networks-CS-456) course at [EPFL](https://www.epfl.ch/en/) during Spring term 2021. 

### Team
This project is accomplished by:
- Riccardo Cadei: [@riccardocadei](https://github.com/riccardocadei)
- Niccolò Polvani: [@nickpolvani](https://github.com/nickpolvani)

### Abstract
Traditionally, reinforcement learning has operated on "tabular" state spaces, e.g. "State 1", "State 2", "State 3" etc. However, many important and interesting reinforcement learning problems (like moving robot arms or playing Atari games) are based on either continuous or very high-dimensional state spaces (like robot joint angles or pixels). Deep neural networks constitute one method for learning a value function or policy from continuous and high-dimensional observations. 

In this project we teach to an agent to play the Lunar Lander game from [OpenAI Gym](https://gym.openai.com/envs/LunarLander-v2/). The agent needs to learn how to land a lunar module safely on the surface of the moon. The state space is 8-dimensional and (mostly) continuous, consisting of the X and Y coordinates, the X and Y velocity, the angle, and the angular velocity of the lander, and two booleans indicating whether the left and right leg of the lander have landed on the moon.

The agent gets a reward of +100 for landing safely and -100 for crashing. In addition, it receives "shaping" rewards at every step. It receives positive rewards for moving closer to [0,0], decreasing in velocity, shifting to an upright angle and touching the lander legs on the moon. It receives negative rewards for moving away from the landing site, increasing in velocity, turning sideways, taking the lander legs off the moon and for using fuel (firing the thrusters). The best score an agent can achieve in an episode is about +250.

There are two versions of the task: one with discrete controls and one with continuous controls but we focus only work on the discrete version. In the discrete version, the agent can take one of four actions at each time step: [do nothing, fire engines left, fire engines right, fire engines down]. 

We use Policy Gradient approaches (using the REINFORCE rule) to learn the task: a network generates a probability distribution over actions, and is trained to maximize expected future rewards given an observation.

### Results

Example of an episode after 3000 epochs of training using REINFORCE + Adaptive Baseline: the rover perfectly land among the 2 flags (Reward>200).

![alt text](https://github.com/riccardocadei/LunarLander-v2-REINFORCE/blob/main/test.gif)



### Environment

The project has been developed and test using `Google Colab` (see main.ipynb for dependecies setup).

### References

- [Sutton & Barto (2018)](https://www.andrew.cmu.edu/course/10-703/textbook/BartoSutton.pdf) Chapter 13 (13.1-13.4)


* * *
 

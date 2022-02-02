# Reinforcement Learning in Python
Implementing Reinforcement Learning (RL) Algorithms for global path planning in tasks of mobile robot navigation. Comparison analysis of Q-learning and Sarsa algorithms fo the environment with cliff, mouse and cheese.
<br/>[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1317898.svg)](https://doi.org/10.5281/zenodo.1317898)

### Related works:
* Sichkar V. N. "Reinforcement Learning Algorithms in Global Path Planning for Mobile Robot", 2019 International Conference on Industrial Engineering, Applications and Manufacturing (ICIEAM), Sochi, Russia, 2019, pp. 1-5. doi: <a href="https://doi.org/10.1109/ICIEAM.2019.8742915" target="_blank">10.1109/ICIEAM.2019.8742915</a> (Full-text available also here <a href="https://www.researchgate.net/profile/Valentyn_Sichkar" target="_blank">ResearchGate.net/profile/Valentyn_Sichkar</a>)

* Sichkar V. N. Effect of various dimension convolutional layer filters on traffic sign classification accuracy. Scientific and Technical Journal of Information Technologies, Mechanics and Optics, 2019, vol. 19, no. 3, pp. (in English). doi: <a href="https://doi.org/10.17586/2226-1494-2019-19-3-546-552" target="_blank">10.17586/2226-1494-2019-19-3-546-552</a> (Full-text available also here https://www.researchgate.net/profile/Valentyn_Sichkar)

* Sichkar V.N. Comparison analysis of knowledge based systems for navigation of mobile robot and collision avoidance with obstacles in unknown environment. St. Petersburg State Polytechnical University Journal. Computer Science. Telecommunications and Control Systems, 2018, Vol. 11, No. 2, Pp. 64–73. doi: <a href="https://doi.org/10.18721/JCSTCS.11206" target="_blank">10.18721/JCSTCS.11206</a> (Full-text available also here https://www.researchgate.net/profile/Valentyn_Sichkar)

* The research results for Neural Network Knowledge Based system for the tasks of collision avoidance is put in separate repository and is available here: https://github.com/sichkar-valentyn/Matlab_implementation_of_Neural_Networks

* The study of Semantic Web languages OWL and RDF for Knowledge representation of Alarm-Warning System is put in separate repository and is available here: https://github.com/sichkar-valentyn/Knowledge_Base_Represented_by_Semantic_Web_Language

* The study of Neural Networks for Computer Vision in autonomous vehicles and robotics is put in separate repository and is available here: https://github.com/sichkar-valentyn/Neural_Networks_for_Computer_Vision

## Description
RL Algorithms implemented in Python for the task of global path planning for mobile robot. Such system is said to have feedback. The agent acts on the environment, and the environment acts on the agent. At each step the agent:
* Executes action.
* Receives observation (new state).
* Receives reward.

The environment:
* Receives action.
* Emits observation (new state).
* Emits reward.

Goal is to learn how to take actions in order to maximize the reward. The objective function is as following:

<b>Q_[s_, a_] = Q[s, a] + λ * (r + γ * max(Q_[s_, a_]) – Q[s, a]),</b>

where,
<br/><b>Q_[s_, a_]</b> - value of the objective function on the next step,
<br/><b>Q[s, a]</b> - value of the objective function on the current position,
<br/><b>max(Q_[s_, a_]) – Q[s, a])</b> - choosing maximum value from the possible next steps,
<br/><b>s</b> – current position of the agent,
<br/><b>a</b> – current action,
<br/><b>λ</b> – learning rate,
<br/><b>r</b> – reward that is got in the current position,
<br/><b>γ</b> – gamma (reward decay, discount factor),
<br/><b>s_</b> - next chosen position according to the next chosen action,
<br/><b>a_</b> - next chosen action.

The major component of the RL method is the table of weights - <b>Q-table</b> of the system state. <b>Matrix Q</b> is a set of all possible states of the system and the system response weights to different actions. During trying to go through the given environment, mobile robot learns how to avoid obstacles and find the path to the destination point. As a result, the <b>Q-table</b> is built. Looking at the values of the table it is possible to see the decision for the next action made by agent (mobile robot).

<br/>Experimental results with different Environments sre shown and described below.
<br/>Code is supported with a lot of comments. It will guide you step by step through entire idea of implementation.
<br/>
<br/>Each example consists of three files:

* _env.py_ - building an environment with obstacles.
* _agent_brain.py_ - implementation of algorithm itself.
* _run_agent.py_ - running the experiments.

## Content
Codes (it'll send you to appropriate folder):
* [RL_Q-Learning_E-1.py](https://github.com/sichkar-valentyn/Reinforcement_Learning_in_Python/tree/master/RL_Q-Learning_E1)
* [RL_Q-Learning_E-2.py](https://github.com/sichkar-valentyn/Reinforcement_Learning_in_Python/tree/master/RL_Q-Learning_E2)
* [RL_Q-Learning_E-3.py](https://github.com/sichkar-valentyn/Reinforcement_Learning_in_Python/tree/master/RL_Q-Learning_E3)
* [RL_Sarsa_E-1.py](https://github.com/sichkar-valentyn/Reinforcement_Learning_in_Python/tree/master/RL_Sarsa_E1)
* [RL_Sarsa_E-2.py](https://github.com/sichkar-valentyn/Reinforcement_Learning_in_Python/tree/master/RL_Sarsa_E2)

<br/>
Experimental results (figures and tables on this page):

* [RL Q-Learning Environment-1. Experimental results](#rl-q-learning-environment-1-experimental-results)
* [Q-learning algorithm resulted chart for the environment-1](#q-learning-algorithm-resulted-chart-for-the-environment-1)
* [Final Q-table with values from the final shortest route for environment-1](#final-q-table-with-values-from-the-final-shortest-route-for-environment-1)
* [RL Q-Learning Environment-2. Experimental results](#rl-q-learning-environment-2-experimental-results)
* [Q-learning algorithm resulted chart for the environment-2](#q-learning-algorithm-resulted-chart-for-the-environment-2)
* [Final Q-table with values from the final shortest route for environment-1](#final-q-table-with-values-from-the-final-shortest-route-for-environment-1)
* [RL Q-Learning Environment-3. Experimental results](#rl-q-learning-environment-3-experimental-results)
* [Comparison analysis of Q-Learning and Sarsa algorithms](#comparison-analysis-of-q-learning-and-sarsa-algorithms)

<br/>

### <a id="rl-q-learning-environment-1-experimental-results">RL Q-Learning Environment-1. Experimental results</a>
Environment-1 with mobile robot, goal and obstacles

<img src="images/Environment-1.gif" alt="RL_Q-Learning_E-1" width=362 height=391> <img src="images/Environment-1.png" alt="RL_Q-Learning_E-1" width=362 height=391>

<br/>

### <a id="q-learning-algorithm-resulted-chart-for-the-environment-1">Q-learning algorithm resulted chart for the environment-1</a>
Represents number of episodes via number of steps and number of episodes via cost for each episode

![RL_Q-Learning_C-1](images/Charts-1.png)

<br/>

### <a id="final-q-table-with-values-from-the-final-shortest-route-for-environment-1">Final Q-table with values from the final shortest route for environment-1</a>
![RL_Q-Learning_T-1](images/Q-Table-E-1.png)
<br/>Looking at the values of the table we can see the decision for the next action made by agent (mobile robot). The sequence of final actions to reach the goal after the Q-table is filled with knowledge is the following: *down-right-down-down-down-right-down-right-down-right-down-down-right-right-up-up.*
<br/>During the experiment with Q-learning algorithm the found shortest route to reach the goal for the environment-1 consist of 16 steps and the found longest rout to reach the goal consists of 185 steps.

<br/>

### <a id="rl-q-learning-environment-2-experimental-results">RL Q-Learning Environment-2. Experimental results</a>
Bigger environment-2 with more obstacles

![RL_Q-Learning_E-2](images/Environment-2.png)

<br/>

### <a id="q-learning-algorithm-resulted-chart-for-the-environment-2">Q-learning algorithm resulted chart for the environment-2</a>
Represents number of episodes via number of steps and number of episodes via cost for each episode

![RL_Q-Learning_C-2](images/Charts-2.png)

<br/>

### <a id="final-q-table-with-values-from-the-final-shortest-route-for-environment-1">Final Q-table with values from the final shortest route for environment-1</a>
![RL_Q-Learning_T-2](images/Q-Table-E-2.png)

<br/>

### <a id="rl-q-learning-environment-3-experimental-results">RL Q-Learning Environment-3. Experimental results</a>
Super complex environment-3 with a lot of obstacles

![RL_Q-Learning_E-3](images/Environment-3.png)

<br/>

### <a id="comparison-analysis-of-q-learning-and-sarsa-algorithms">Comparison analysis of Q-Learning and Sarsa algorithms</a>
![RQ-learning_via_Sarsa](images/Q-learning_via_Sarsa.png)

<br/>

### MIT License
### Copyright (c) 2018 Valentyn N Sichkar
### github.com/sichkar-valentyn
### Reference to:
Valentyn N Sichkar. Reinforcement Learning Algorithms for global path planning // GitHub platform. DOI: 10.5281/zenodo.1317898

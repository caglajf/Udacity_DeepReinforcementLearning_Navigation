<h1>Udacity Deep Reinforcement Learning Project 1<h1>
<h1>Navigation Report</h1>
  
  Navigation Project is the first project of the Udacity Deep Reinforcement Learning Nanodegree Program.
  
  <h2>Problem Statement</h2>
  
  In this project, an agent should be trained to navigate (and collect bananas!) in a large, square world. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.
  
  ![banana](https://user-images.githubusercontent.com/51778059/155200284-75c8f843-015c-4280-9dee-2814f17ba340.gif)
  
   <h2>Solving the Environment</h2>

  The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward.<br />
1 - move backward.<br />
2 - turn left.<br />
3 - turn right.<br />
  
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.
  
  <h2>Learning Algorithm</h2>
  
  In this project, [deep Q-Learning algorithm](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) was implemented to train the agent. The main idea is to to train deep neural networks to develop a novel artificial agent, termed a deep Q-network (DQN), that can learn successful policies directly from high-dimensional sensory inputs using end-to-end reinforcement learning. In DQN implementation, a single architecture can successfully learn control policies in a range of different environments with only very minimal prior knowledge. In Figure 1, an illustration of DQN Architecture was provided. 
  
 <img width="685" alt="dqn" src="https://user-images.githubusercontent.com/51778059/155212577-b3f188b6-a9e9-4351-897c-2b2506aa5d43.png">
  Figure 1. Illustration of DQN Architecture

  The DQN algorithm was developed by DeepMind in 2015. It was able to solve a wide range of Atari games (some to superhuman level) by combining reinforcement learning and deep neural networks at scale. The algorithm was developed by enhancing a classic RL algorithm called Q-Learning with deep neural networks and a technique called experience replay.

   <h4>Q-learning with deep neural networks</h4>
 Q-Learning is based on the notion of a Q-function. The Q-function (a.k.a the state-action value function) of a policy measures the expected return or discounted sum of rewards obtained from state  by taking action first and following policy thereafter. We define the optimal Q-function as the maximum return that can be obtained starting from observation, taking action and following the optimal policy thereafter. The optimal Q-function obeys the following Bellman optimality equation:
  
  <img width="241" alt="Capture" src="https://user-images.githubusercontent.com/51778059/155213847-12e60f0c-0b87-4134-b28f-eaeaad3b4091.PNG">

  For most problems, it is impractical to represent the Q-function as a table containing values for each combination. Instead, we can train a function approximator, such as a neural network with parameters to estimate the Q-values.
  
  ![DQN alg](https://user-images.githubusercontent.com/51778059/155216061-8f8c5313-89d0-4ab1-bf7a-7bdb5afd7e51.png)
  
  <h4>Experience replay</h4>
  To avoid computing the full expectation in the DQN loss, we can minimize it using stochastic gradient descent. If the loss is computed using just the last transition , this reduces to standard Q-Learning.
  
  <h4>Hyperparameters</h4>
  
  In this project, the deep Q-learning algorithm code given in Udacity ND program was modified. The selected hyperparameters were given below. 
  
 Replay buffer size: 100000<br />
 Batch size: 64<br />
 Gamma (discount factor): 0.99<br />
 Tau (soft update of target parameters): 0.001<br />
 Learning rate: 0.0005<br />
 How often to update the network: 4

   <h4>Model</h4>
The following architecture was used for training the agent:
  
 ```
 Input nodes (37) -> Fully Connected Layer (256 nodes, Relu activation) -> Fully Connected Layer (128 nodes, Relu activation) -> Output nodes (4)
 ```
  
  <h2>Results</h2>
  
   In order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes. After implementing DQN method, the environment succesfully solved in 429 episodes with average score of 13.12.
  
  ![image](https://user-images.githubusercontent.com/51778059/155216270-f2589bf0-aa42-4c46-970b-60b74735ca11.png)

  ![indir](https://user-images.githubusercontent.com/51778059/155216792-b7c2267d-8b28-48e8-812a-5af1cdcba8c5.png)

 <h2>Ideas for Future Work</h2>
  
   I implemented DQN method and solved the environment succesfully. In order to improve the performance of the agents, some other methods and improvements can also be tried. <br />
- More effort can be spent for hyperparameter optimization to improve results.<br />
- Different algorithms can be implemented such as [duelling DQN](https://arxiv.org/abs/1511.06581), [double DQN](https://arxiv.org/abs/1509.06461v3), [distibutional DQN](https://arxiv.org/abs/1707.06887) or [A3C](https://arxiv.org/abs/1602.01783) to compare the performance of training. <br />
- Prioritized experience replay can also be tried to see if it improves the training time.<br />


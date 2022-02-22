<h1>Udacity Deep Reinforcement Learning Project 1<h1>
<h1>Navigation Report</h1>
  
  Navigation Project is the first project of the Udacity Deep Reinforcement Learning Nanodegree Program.
  
  <h2>Problem Statement</h2>
  
  In this project, an agent should be trained to navigate (and collect bananas!) in a large, square world. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.
  ![banana](https://user-images.githubusercontent.com/51778059/155200284-75c8f843-015c-4280-9dee-2814f17ba340.gif)
  
   <h2>Solving the Environment</h2>

  The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward.
1 - move backward.
2 - turn left.
3 - turn right.
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.
  
  <h2>Learning Algorithm</h2>
  
  In order to train multiple agents, I implemented Multi Agent Deep Deterministic Policy Gradient [(MADDPG) algorithm](https://arxiv.org/pdf/1706.02275.pdf) as it requires the training of two separate agents, and the agents need to collaborate under certain situations (like don’t let the ball hit the ground) and compete under other situations (like gather as many points as possible). A MADDPG is composed of multiple DDPG agents.
  
  In MADDPG, each agent’s critic is trained using the observations and actions from all the agents, whereas each agent’s actor is trained using just its own observations. This allows the agents to be effectively trained without requiring other agents’ observations during inference (because the actor is only dependent on its own observations).You can find the pseudocode of the MADDPG algorithm below. 
  
  <img width="427" alt="image" src="https://user-images.githubusercontent.com/51778059/154129979-fe786303-9596-4cec-b54e-1e7ee11937cb.png">
  
 
  <h4>Hyperparameters</h4>
 Replay buffer size: 10000<br />
 Batch size: 256<br />
 Gamma (discount factor): 0.99<br />
 Tau (soft update of target parameters): 0.001<br />
 Learning rate for actor: 0.0001<br />
 Learning rate for critic: 0.001<br />
 Weight decay: 0<br />
 Noise decay: 1<br />

   <h4>Model</h4>
- Actor<br />
  The Neural Network has two hidden layers with 256 and 256 neurons, respectively. The activation function used is ReLU for the input and first layer and tanh for the output The output layer has 4 values which corresponds to the dimension of each action.<br />
 - Critic<br />
  The Neural Network has two hidden layers with 256 and 256 neurons, respectively. The activation function used is ReLU for the input and first layer and none for the output. The output layer has just one value which corresponds to the assesment made by the critic of the action chosen by the actor.<br />
    
  <h2>Results</h2>
  
  After implementing MADDPG method, the score evolution can be seen below:
  
  <img width="356" alt="Screenshot 2022-02-19 211415" src="https://user-images.githubusercontent.com/51778059/154813625-ae2c893d-427f-40d1-9e37-81d1fee8792f.png">
  
  ![plot](https://user-images.githubusercontent.com/51778059/154815382-80d3e9d3-3f96-415c-8cfb-e74f64e5e1a4.png)

 The environment has been successfully solved in 2311 episodes.

 <h2>Ideas for Future Work</h2>
  
   I implemented MADDPG method and solved the environment. In order to improve the performance of the agents, some other methods and improvements can also be tried. <br />
- More effort can be spent for hyperparameter optimization to improve results.<br />
- Different algorithms can be implemented such as [A2C](https://medium.com/deeplearningmadeeasy/advantage-actor-critic-a2c-implementation-944e98616b), [PPO](https://openai.com/blog/openai-baselines-ppo/) or [D4PG](https://arxiv.org/pdf/1804.08617.pdf) to compare the performance of training. <br />
- Prioritized experience replay can also be tried to see if it improves the training time.<br />


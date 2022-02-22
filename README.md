<h1>Udacity Deep Reinforcement Learning Nanodegree Program</h1>
<h1>Project 1: Navigation</h1>

<h2>General Description</h2>
This project is the first project of Udacity Deep Reinforcement Learning Program. The aim of this project is to train an agent to navigate (and collect bananas!) in a large, square world. Repository contains the code that I used for training an agent, along with the trained model weights and a report describing my learning algorithm in which I described the details of my implementation, along with ideas for future work.<br />


![banana](https://user-images.githubusercontent.com/51778059/155196269-5980db90-ca32-4a27-94e6-585dc75bb64a.gif)

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

<h2>The Environment</h2>
In this environment, you should navigate an agent to collect yellow bananas while avoiding blue bananas. The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward<br />
1 - move backward<br />
2 - turn left<br />
3 - turn right<br />

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

<h2>Getting Started</h2>

- First step is to clone the DRLND repository by following the instructions in the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies) of Udacity to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels.

- For this project, you will not need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below. You need only select the environment that matches your operating system:

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)<br />
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)<br />
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)<br />
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)<br />

(For Windows users) Check out this [link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use this [link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to enable a virtual screen, and then download the environment for the Linux operating system above.)

 <h2>Insructions for training an agent</h2>

- After you have followed the instructions above, open Navigation.ipynb (located in caglajf/Udacity_DeepReinforcementLearning_Navigation repository) and follow the instructions to learn how to use the Python API to control the agent. 
  
 - In this project, Deep Q-Learning (DQN) method was employed and the main classes were defined in the dqn_agent.py file. The details of the method and the results were given in Report.md file. 

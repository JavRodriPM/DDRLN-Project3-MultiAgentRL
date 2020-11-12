[//]: # (Image References)

[image1]: https://raw.githubusercontent.com/JavRodriPM/DDRLN-Project3-MultiAgentRL/master/Videos/Trained_Agents_FS.gif "Trained Agent"


# Project 3: Collaboration and Competition

### Introduction

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained Agent][image1]

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

### Introduction

The algorithm is an implementation of the DDPG (Deep deterministic policy gradient) algorithm with soft updates. This algorithm is an Actor-critic method, these methods main characteristics are: 
-	The reduction the high-variance commonly associated to policy-based agent,
-	It learns faster than policy-based methods and 
-	have more consistent convergence than value-based agents

For this agents to be an Actor-critic, we have two learning neural networks: 
-	In a standard Actor-critic method, the Actor network will learn the probabilities of good and bad actions. Will take in states and outputs a distribution over the possible actions. But in the case of DDPG, the algorithm used in this project, the Actor will give us the best possible action based on the policy learnt, not a probability distribution.
-	The Critic network will learn how to estimate good actions and bad actions to help on the actor decisions. Technically it will learn to evaluate the state value function (Vpi), will take in states and outputs an expectation of the state value function of the policy, this state value function will update the actor network.

### Set up your environment	

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agents on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agents without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `DDRLN-Project3-MultiAgentRL/` folder,  unzip (or decompress) the file and change the path in the `Tennis.ipynb` file in the following line: `env = UnityEnvironment(file_name='.\Tennis_Windows_x86_64\Tennis.exe')`

3. Install the requirement defined in the requirements.txt via `pip` 

```
pip install -r requirements.txt

```
or follow the course instructions at: (https://github.com/udacity/deep-reinforcement-learning#dependencies).
.

### Instructions

Follow the instructions in `Tennis.ipynb` to get started with training your own agents or just see playing the already trained agents!   


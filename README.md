# DDPG-PRE-Tennis
DDPG-PRE to solve the Tennis environment in UNITY ML

[//]: # (Image References)

[image1]: Tennis.gif "Tennis Agent" 
![Trained Agent][image1]

# DDPG With Priority Replay Memory For Collaboration and Competition
Deep Deterministic Policy Gradient with Replay Memory


### Introduction

This repository contains a simple Neural Network driven DDPG algorithm running in Unity ML Agent. This model is sometimes called "Deep Deterministic Policy Gradient", but this is a misnomer since there is usually nothing deep in the model architecture. Typically Deep network are convolutional networks models using hundreds or thousands of layers. Our model uses a Multi Layer Perceptron with two small hidden layers of 64 nodes on each hidden layer.

The model is implemented in Python 3 using PyTorch.

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

# Goal

Thus, the goal of the 2 agents is to bounce the ball from inside the bounds while not letting it hit the ground it.

# Rewards

A reward of +0.1 is provided for bouncing the ball.
A reward of -0.01 is provided if the ball hits the ground or if the ball is bounced from outside the bounds.

# State space

The state space has 8 dimensions and contains the balls's and racket's velocity and position.  Given this information, the agent has to learn how to best select actions. 

# Action space

The state space is continuous and its scope encompasses the various positions the racket can take.

The task is episodic, and in order to solve the environment, the agent must get an average score of +0.5 over 100 consecutive episodes.

### Getting Started

1. Install Unity ML https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md


2. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
- Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

(_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


For instance, if you are using a Mac, then you downloaded Tennis.app. If this file is in the same folder as the notebook, then the line below should appear as follows:
env = UnityEnvironment(file_name="Tennis.app")

3. Download the project from github and place the file in the Collaboration Competition folder. 

4. Install Anaconda3.

Before you begin, you should have a non-root user with sudo privileges set up on your computer.

The best way to install Anaconda is to download the latest Anaconda installer bash script, verify it, and then run it.

Find the latest version of Anaconda for Python 3 at the Anaconda Downloads page.
https://www.anaconda.com/download/#macos
Install ANACONDA3 following instructions from the anaconda web site.

5. Create a virtual environment for python    

In a terminal type: 

conda create -n drlnd python=3.6

source activate drlnd

To stop the virtual environment once you are done, type deactivate in the terminal.

Always start the drlnd virtual environment before starting the jupyter notebook or the python script,
else you will get errors when running the code.



6. Install dependencies

cd python

python3 setup.py install -r requirements.txt


7. Start the notebook 

cd ../

jupyter notebook

8. Run the agent

To start training, simply open TennisPre.ipynb in Jupyter Notebook and follow the instructions given there.
You can either train the agent: this takes about 3 hours to reach a score of 0.5, however the training being stochastic it may take much longer. You can skip the training and watch a trained agent using the provided trained weights.





# CartPoleSwingUp
Swinging up and Stabilizing an Inverted Pendulum on a cart using Deep Reinforcement Learning
This project uses a Cartpole environment.

# Motivation
This project is the code for my thesis. I´m studying at the technological University in Kaiserslautern. My degree course is Mechanical Engineering with applied computer science. 
At the University there is a real life pendulum which aim it is to swing up an stabilize. The pendulum has one joint and is fixed on a cart which is adjustet to a megnetic levition axis.
The goal from this script is to simulate the upswing (and stabilasation). Afterwards the the trained data is used on the real life pendulum.

## Python
This project uses **python 3.5**. Anaconda installation includes python.
## Keras with TensorFlow Backend
This project uses Keras(version 2.0.8) with TensorFlow(version 1.7.0) backend.<br />
Instructions for installing packages inside anaconda environment can be found [here](https://conda.io/docs/user-guide/tasks/manage-pkgs.html)
## OpenAI Gym
This project uses OpenAI Gym's environment.<br />
Installation instructions for OpenAi Gym can be found [here](https://github.com/openai/gym#installation)

## Installing the environment
In order to use the custom built environment, it must be installed beforehand. The following [link](https://medium.com/@apoddar573/making-your-own-custom-environment-in-gym-c3b65ff8cdaa) shows an example how to install a custom environment. Follow the instructions with the appropriate environment from here.

# About the Environment
The environment in Gym usually consists of an initialisation and four methods. 
The initialisation specifies the parameters of the pendulum and the cart. These parameters are calculated according to the specifications of the real pendulum.
Furthermore, the boundary conditions are specified. These are:
- Maximum displacement of the cart in the X-axis
- Length of a time step (dt)
- Interval/ number of actions
- Number of states
- state space of the inverted pendulum
- cost function
These values can be adjusted as needed to replicate the pendulum.

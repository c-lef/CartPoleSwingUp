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
- equation of motion of the inverted pendulum
- cost function

These values can be adjusted as needed to replicate the pendulum.
The equation of motion in the environment is shown below. The used parameters can be seen in the code.

<img src="https://user-images.githubusercontent.com/84963025/148773083-ea268acd-38d8-453f-93ae-0c609ade8f9d.png" width="500">

The cost function of the environment was mapped after several trials as seen below in the three equations. The first part of the equation is composed of the reward for the shift in the x position. The further in the middle the cart is, the greater the reward.
A much larger factor on the reward is the second part, which involves weighting on the angular position. The smaller the angle, the greater the reward.
In addition, a larger part of the reward is added when the pendulum is in the vertical upward position.
Finally, there is an abort criterion if the pendulum moves over the lateral limits.

<img src="https://user-images.githubusercontent.com/84963025/151699804-aefd7957-ab89-489a-96a3-da96a98a239a.png" width="500">

The costfunction can be modified further to achieve an even better result.

# About the DQL-Algorithm
In the code for the DQL-Algorithm, several parameters can also be adjusted. One is the neural network that estimates the Q-values. It consists of three layers that use the ReLu activation function. The activation function has proven itself for reinforcement learning algorithms. The neural network can certainly be further adapted to work even more accurately. The learning rate can also be changed.

The Deep Q-learning algorithm is applied according to Sutton et al. The following pseudo code shows the procedure.

<img src="https://user-images.githubusercontent.com/84963025/151711678-eaca6e87-0cb8-488a-97d8-f64fd9af8aea.png" width="500">

# About the Training
The training starts with the previously defined number of episodes and steps. A window opens showing the simulated cart. The inverse pendulum selects the action according to the DQL-Algorithm. An episode is finished when the maximum number of steps has been completed, the cart reaches the limit or a swing-up is successful.
When the entire training is completed, another window opens showing the cumulative reward over the different episodes.
Furthermore, the weights of the neural networks are saved in a CVS file.

Please feel free to improve my code and enjoy Reinforcement Learning.




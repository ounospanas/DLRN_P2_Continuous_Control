[//]: # (Image References)

[image1]: https://raw.github.com/ounospanas/DLRN_P2_Continuous_Control/master/ddpg_score.png "scores"

### Learning Algorithm
This implementation is based on a DDPG (Deep Deterministic Policy Gradient) model, which is a Model-Free Off-policy RL algorithm applied mostly to continuous action spaces. The DDPG agent has 2 models called actor (for selecting actions) and critic (for judging how good are the actions taken by the actor), and its goal is to make both models perfom better over time by exploring and exploiting the environment. Noise is added to the output of the actor, so the selected actions are clipped (-1,1).
 
#### Hyperparameters
A deep fully connected neural network was used for both critic and actor, having 2 hidden layers. Their first layer contains 128 neurons, while the second 64. 
Some other hyperparameters are:
- replay buffer size: int(1e5)
- batch size: 128
- gamma: 0.99
- tau (soft update target parameter): 1e-3  
- learning rate for critic: 1e-4 
- learning rate for actor: 1e-4 
- weight decay: 0.0
- noise mu: 0.0
- noise theta: 0.15
- noise sigma: 0.2

### Plot of Rewards

![scores][image1]
As shown in the figure above, the environment was solved after 118 episodes.

### Ideas for Future Work
- use another policy-based algorithm for continuous control such as PPO or another actor-critic implementation such as A3C, A2C, IMPALA etc
- add noise directly to the agent's parameters, which can lead to more consistent exploration and a richer set of behaviors [OpenAI paper](https://arxiv.org/abs/1706.01905).
# Reinforcement Learning with TF-Agents

In this notebook, we will explore reinforcement learning (RL) using the TensorFlow Agents (TF-Agents) library. We will implement a Soft Actor-Critic (SAC) agent to solve a continuous control task (Lunar Landing) in the OpenAI Gym environment. The SAC algorithm is a state-of-the-art RL method that excels in environments requiring stability and efficient exploration.

The **Soft Actor-Critic (SAC)** method is a state-of-the-art reinforcement learning (RL) algorithm that excels in environments requiring stability and efficient exploration. It uses a combination of *actor* and *critic* neural networks to optimize both policy and value functions while maintaining a balance between exploration and exploitation.

- **Actor Neural Network**: The actor network generates the policy, which is a probabilistic mapping from states to actions. It aims to maximize both the expected cumulative reward and an entropy term, encouraging diverse actions to improve exploration and prevent premature convergence to suboptimal solutions.

- **Critic Neural Network**: The critic network evaluates the quality of the actions taken by estimating the Q-value, or the expected return from taking a specific action in a given state. This Q-value guides the actor in improving its policy.

SAC incorporates a temperature parameter to balance the trade-off between exploration and exploitation dynamically, ensuring robust learning in complex environments.



<!-- <p float="left" align="middle">
  <div>
    <p>Trained Agent</p>
    <img src="/LunarLander-v2-gif.gif?raw=true" width="40%">
  </div>

  <div align="center" display="inline";>
    <p>Random Agent</p>
      <img src="/LunarLander-v2_random-gif.gif?raw=true" width="40%">
  </div>
</p> -->


| Trained Policy Agent    | Random Policy Agent |
| -------- | ------- |
| <img src="./LunarLander-v2-gif.gif?raw=true" width="100%"> | <img src="./LunarLander-v2_random-gif.gif?raw=true" width="100%">   |


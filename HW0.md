# Homework 0

After you have done following [instruction](https://github.com/S-Tuchapong/FRA503-Deep-Reinforcement-Learning-for-Robotics), let us proceed to the homework section.

For the first homework, we will explore an *ideal* reinforcement learning (RL) example: training an agent to solve the classic `Cartpole` control problem. The objective of this homework is to provide an overview of RL components and the fundamental concepts of how these components relate to one another.

### Learning Objectives:

1.  Understand the RL training pipeline in IsaacLab:

    - Environment & Agent Setup
    - Training process
    - Performance evaluation

        - Viewing learning performance logs
        - Viewing trained agent play in environment

2. Understand the IsaacLab workflow `Manager-Based RL Environment` for implementation your RL project setup in IsaacLab:

    - Action
    - Observation
    - Event
    - Reward
    - Termination

3. Connect practical experience with theoretical RL knowledge.


Part 1: Take a Look at `Cartpole` Rl Agent
---

**Cartpole** is a fundamental example of an inverted pendulum, consisting of a pole with its center of gravity above the pivot point, which is attached to a cart. Despite its inherent instability in most configurations, it can be controlled by moving the cart along a frictionless track. In the `Cartpole-v0` environment, the pole starts in a position perpendicular to the ground, and the objective is to maintain this upright position by applying appropriate forces to the cart.

![](cartpole.png)

### Train the `Cartpole` RL Agent
According to the [Training with an RL Agent Tutorial](https://isaac-sim.github.io/IsaacLab/main/source/tutorials/03_envs/run_rl_training.html#training-with-an-rl-agent), the `Cartpole` RL Agent can be headlessly train with off-screen rendering by running the following command in the `IsaacLab` directory

    python source/standalone/workflows/sb3/train.py --task Isaac-Cartpole-v0 --num_envs 64 --headless --video

Note that you can adjust the video length and the interval between each records by specifying the parameters `--video_length` and `--video_interval` respectively. For more information, please check the [Recording video clips during training Guide](https://isaac-sim.github.io/IsaacLab/main/source/how-to/record_video.html).

### Visualize the Training Results
The mean of the episode cumulative reward (return) and the episode length for the first one hundred terminated agents with respect to the timesteps can be observed using `TensorBoard` by executing the following command:

    python -m tensorboard.main --logdir logs/sb3/Isaac-Cartpole-v0

The video recorded during training is located in `logs/sb3/Isaac-Cartpole-v0`.

### Questions

Submit the answers to the following questions:

1. According to the tutorials, if we want to edit the environment configuration, action space, observation space, reward function, or termination condition of the `Isaac-Cartpole-v0` task, which file should we look at, and where is each part located?
2. What are the action space and observation space for an agent defined in the `Isaac-Cartpole-v0` task?
3. How can episodes in the `Isaac-Cartpole-v0` task be terminated?
4. How many reward terms are used to train an agent in the `Isaac-Cartpole-v0` task?


Part 2: Playing with `Cartpole` Rl Agent
---
Let us adjust the weight of each reward term specified in the `Isaac-Cartpole-v0` task and train the agent. Which results will be affected by this adjustment, and why? Submit the answers.

You may further explore by modifying other aspects, such as the agent's action space, observation space, and termination conditions.

Part 3: Mapping RL Fundamentals
---
![](image-4.png)

Submit the answers to the following questions:

- What is reinforcement learning and its components according to your understanding? Giving examples of each component according to the diagram consider the `Cartpole` problem.

- What is the difference between the reward, return, and the value function?

- Consider policy, state, value function, and model as mathematical functions, what would each one take as input and output? 





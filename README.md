# Snake Game with Deep Reinforcement Learning


![snake_RL_1](https://github.com/Shrestha097/Snake-Game-with-Deep-Reinforcement-Learning/assets/78401805/a468cb6a-ba64-4aa6-87b8-59801f2d525c)


## Background
The snake game was created in the mid-1970s by a programmer named Gremlin. It became more popular in the 1990s when it was included as a standard feature on Nokia phones, in 1997 on the Nokia 6110.
The objective was to avoid colliding with the walls or the snake’s own body while eating as much food as possible. The game was so popular it was ported to many different devices and platforms, including PCs, consoles, and mobile devices. There were also many different versions of the game, with different graphics, levels, and gameplay mechanics. It was simple enough to be understood by beginners but presents interesting challenges for more advanced algorithms. It was used as a popular example in computer science, and AI research and also used to demonstrate various concepts, such as pathfinding, optimization, and machine learning.

## Objective
The objective of the snake is to eat as many apples as possible without hitting the walls or circling around and hitting its own body.


## Environment
The environment for the Snake Arcade game has been created with the snake as the agent and the position of the snake and the position of the snake’s head defined. There are 3 actions right, left, and forward. The step method is defined in the environment which gets the current location of the snake and the current location of the apple, then the snake will take a step and the position of the snake’s head is then changed according to the action taken, it also checks if the snake has collided into the wall or itself and terminates the episode. 


![image](https://github.com/Shrestha097/Snake-Game-with-Deep-Reinforcement-Learning/assets/78401805/b3b4ac54-6d3f-4b3c-b7ba-154fb6c60060)


## Rewards
If the snake hits with an apple that means it has eaten the apple and then the length of the snake will be increased and when the max length of the snake is reached the agent gets an additional reward of +500 and the agent wins the game.
The rewards given to the agent are dependent on a few factors. The reward is calculated such that the snake maximizes the cumulative reward in the end. First, the Euclidean distance between the snake and the apple is calculated then this distance is subtracted from 150 then divided by 10 and this is added to the apple rewards which is the reward the agent gets after eating an apple. This makes sure that as the distance between the snake and the apple decreases, the reward increases, which gives the snake motivation to travel towards the apple every time. The agent gets a reward of +500 when the snake eats the apple, -100 when it collides, and a positive reward to stay alive based on the Euclidean distance. The apples are spawned at certain spaces on the grid to help perform better rather than spawning them stochastically. The reset method in the environment resets the position of the snake and randomly places the apple somewhere in the observation space.


## Training the agent using Deep RL Algorithms

The agent was trained using Deep Q-Network (DQN), Double Deep Q Network (DDQN) and A2C algorithms. After 120,000 episodes, the snake achieved impressive results as follows:

**DQN:**

Training result: 12 apples per episode,
Test result: 10 apples per episode

<img width="846" alt="image" src="https://github.com/Shrestha097/Snake-Game-with-Deep-Reinforcement-Learning/assets/78401805/460661ca-17e1-472b-b320-6021c95b043d">


**DDQN:**

Training result: 10 apples per episode,
Test result: 7 apples per episode

<img width="846" alt="image" src="https://github.com/Shrestha097/Snake-Game-with-Deep-Reinforcement-Learning/assets/78401805/77290310-710a-4846-9b6f-40eb63d1d9cc">

**A2C:**

Training result: 1 apple per episode,
Test result: 1 apple per episode

<img width="846" alt="image" src="https://github.com/Shrestha097/Snake-Game-with-Deep-Reinforcement-Learning/assets/78401805/ea31ced9-779c-44bc-b6ee-730614db8487">


# Automating Pac-man with Deep Q-learning: An Implementation in Tensorflow.
Deep Q-learning and Epsilon Greedy Policies to tackle the OpenAI MsPacman environment.

For [Towards Data Science](https://towardsdatascience.com/automating-pac-man-with-deep-q-learning-an-implementation-in-tensorflow-ca08e9891d9c).

### Summary

1. We define our Deep Q-learning neural network. This is a CNN that takes in-game screen images and outputs the probabilities of each of the actions, or Q-values, in the Ms-Pacman gamespace. To acquire a tensor of probabilitieses, we do not include any activation function in our final layer.
2. As Q-learning require us to have knowledge of both the current and next states, we need to start with data generation. We feed preprocessed input images of the game space, representing initial states s, into the network, and acquire the initial probability distribution of actions, or Q-values. Before training, these values will appear random and sub-optimal.
3. With our tensor of probabilities, we then select the action with the current highest probability using the argmax() function, and use it to build an epsilon greedy policy.
4. Using our policy, we'll then select the action a, and evaluate our decision in the gym environment to receive information on the new state s', the reward r, and whether the episode has been finished.
5. We store this combination of information in a buffer in the list form <s,a,r,s',d>, and repeat steps 2–4 for a preset number of times to build up a large enough buffer dataset.
6. Once step 5 has finished,we move to generate our target y-values, R' and A', that are required for the loss calculation. While the former is simply discounted from R, we obtain the A' by feeding S' into our network.
With all of our components in place, we can then calculate the loss to train our network.
7. Once training has finished, we'll evaluate the performance of our agent graphically and through a demonstration

### Demonstration (1500 episodes)
<p align="center">
  <img width="" height="" src="https://media.giphy.com/media/L4SwDa2US0wCi7O8Hk/giphy.gif">
</p>


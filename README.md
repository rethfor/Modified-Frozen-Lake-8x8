# Modified-Frozen-Lake-8x8
Reaching 60% accuracy rate with OpenAI Gym's Frozen Lake environment's 8x8 map version.

I modified the learning rate as a linearly decreasing value because I thought while exploration shifts into exploitation, learning rate of implemented Bellman equation should be 
decreased as well since the agent should give more attention to previously learned values on each episode as it approaches to the end of training. 

This operation performed on line: ```lr_array = np.linspace(lr, 1e-4, num=num_episodes)```, so this creates an array with gradually decreased values of learning rate.
Assigning iteratively every value of this array to learning rate with line: ```learning_rate = lr_array[episode]```

So you can adjust learning rate initialization on line: ```lr = 0.75``` (0.75 is just an optimal value according to my experiments).
If you are training on a different number of episode, you can change ```num=num_episodes``` in ```lr_array = np.linspace(lr, 1e-4, num=num_episodes)``` according to your number 
of episode.

I modified the exploration rate's curve as well with a flat between certain episodes but that doesn't make a significant impact on results.
Initial value of exploration decay rate ```exploration_decay_rate = 0.0001492``` is also an experimental value.  

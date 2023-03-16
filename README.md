# Optimal Reset Policy simiulation

## Simulation Notebook

Our simulation is built up of three functions: run_one_simulation(), randomize_parameters(), and run_simulations().

### randomize_parameters()

This function provides random parameters for our simulation: mining rate of adversary, mining rate of honest miner, and the k value. All of the other parameters used in the simulation (such as mining rate and proportion of mining rate can be calulated using these paramters). We bounded the parameters in our simulation with a k-value between 2 and 25 and the adversarial mining proportion from 10% to roughly 49%. These bounds exist so the simulation will run within a reasonable amount of time

### run_one_simulation()

This function samples 30 trials from the distribution of trials given the parameters choosen from randomize_parameters(). Our while loop within each trial continues to run until we achieve a saftey violation which is define by the following equation: ![](/formula.png "current probablility")

![](/reset_prob.png "reset probablility")

![](/full.png "full")

### run_simulation()

This function randomizes the parameters, call run_one_simulation() and then logs the parameters and the number of blocks to a saftey violation on average to a csv. We then use this CSV to run analysis to see 


## Analysis Notebook

In the analysis notebook, we plot our parameters against different variables from our simulation. We experiment with different manipulations of the parameters into OLS models in order to find the relationship. We eventually find a model that has an R-squared value of .98 and even achieve a value of .99 after running ridge regression (all variables are statistically significant).
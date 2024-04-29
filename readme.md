# Tic Tac Toe using Reinforcement Learning

This project implements a Tic Tac Toe game using various reinforcement learning techniques, including Sparse Sampling, Rollout Policy Adaptation, and Temporal Difference Learning.

#Description 

Tic-Tac-Toe is a simple two-player game played on a 3x3 grid, where players take turns marking cells with "X" or "O" to form a line of three of their symbols either horizontally, vertically, or diagonally. The game ends in a win for the first player to achieve this or in a draw if the grid fills up without a winner.

* image -> https://upload.wikimedia.org/wikipedia/commons/thumb/3/32/Tic_tac_toe.svg/1200px-Tic_tac_toe.svg.png


## Here are the basic rules:
# Sparse Sampling
* Sparse Sampling is a reinforcement learning algorithm used in the context of decision making under uncertainty, particularly in stochastic environments with large state spaces. 
* It addresses the challenge of exploring and exploiting the state space efficiently by focusing on a subset of promising states rather than exhaustively exploring all possibilities.



#Basic Principles:

#Exploration-Exploitation Tradeoff:
 Similar to other reinforcement learning algorithms, Sparse Sampling aims to balance exploration of new states with exploitation of known information to maximize cumulative rewards.

#Selective Sampling:
 Instead of uniformly sampling from the entire state space, Sparse Sampling selectively focuses on a subset of states that are deemed promising based on certain criteria.

#Sampling Heuristics:
 * Sparse Sampling employs heuristics or sampling strategies to prioritize which states to explore further. 
 * These heuristics could be based on estimates of state value, uncertainty, or other domain-specific factors.

#Outcome Evaluation:
 After sampling states and taking actions, Sparse Sampling evaluates the outcomes to update its estimates of state values and refine its sampling strategy.

#Incremental Improvement:
 Through iterative sampling and evaluation, Sparse Sampling gradually improves its understanding of the state space and refines its decision-making policy over time.

#Key Components:

#Exploration Strategy:
* Sparse Sampling employs various exploration strategies to select which states to sample next.
* These strategies could include random sampling, uncertainty-based sampling, or prioritized sampling based on estimated state values.

#Evaluation Function:
* An evaluation function is used to assess the quality of sampled states and the potential value of taking actions in those states. 
* This function typically incorporates estimates of state values, action values, or other relevant metrics.

#Sampled State Storage:
Sparse Sampling maintains a data structure to store information about sampled states, their corresponding rewards, and any additional metadata needed for evaluation and decision-making.

#Update Mechanism:
* After sampling states and evaluating outcomes, Sparse Sampling updates its internal estimates of state values or action values based on observed rewards and predicted future rewards. 
* This update mechanism is crucial for learning and adapting the decision-making policy.

#Policy Improvement:
* Based on the updated estimates of state values, Sparse Sampling adjusts its decision-making policy to prioritize actions that lead to favorable outcomes.
* This policy improvement process is iterative and aims to converge to an optimal policy over time.

 #Code Execution :
 sparsesampling.py






## Rollout Policy Adaptation

Rollout Policy Adaptation is a technique commonly used in Monte Carlo Tree Search (MCTS) algorithms to guide the search process towards more promising regions of the game tree. It involves dynamically adjusting the rollout policy based on the outcomes of simulated playouts or rollouts, with the goal of improving the efficiency and effectiveness of the search.




#Basic Principles:

* Monte Carlo Tree Search (MCTS): Rollout Policy Adaptation is often applied within the framework of MCTS, which is a decision-making algorithm commonly used in games and optimization problems. 
* MCTS iteratively builds a search tree by simulating sequences of actions and evaluating their outcomes.

#Rollout Simulation:

* During each iteration of MCTS, a sequence of actions is simulated from the current state of the game until a terminal state or a predefined depth is reached. 
* These simulations, known as rollouts or playouts, provide estimates of the expected outcome from the current state.

#Policy Selection:

* Rollout Policy Adaptation involves selecting a rollout policy that guides the selection of actions during rollouts.
* This policy can be static or adaptive, with adaptive policies adjusting based on the outcomes of previous rollouts.

#Outcome Analysis:

 * After completing a rollout, the outcomes are analyzed to determine their quality or effectiveness.
 * This analysis may involve comparing the actual outcomes with the expected outcomes predicted by the rollout policy.


#Policy Adaptation
 * Based on the analysis of rollout outcomes, the rollout policy is adjusted to favor actions that have led to favorable outcomes in the past. 
 * This adaptation aims to improve the quality of future rollouts and guide the search towards more promising regions of the game tree.

#Key Components:

# Rollout Policy:

* The rollout policy defines how actions are selected during rollouts. It can be based on various criteria, such as randomness, domain knowledge, or learned heuristics.
* Adaptive rollout policies adjust their selection criteria based on the observed outcomes of previous rollouts.

#Outcome Evaluation:

* After completing a rollout, the outcomes are evaluated to assess their quality or effectiveness.
* This evaluation may involve comparing the actual rewards obtained from the rollout with the expected rewards predicted by the rollout policy.

#Policy Adjustment:

* Based on the outcome evaluation, the rollout policy is adjusted to favor actions that have led to favorable outcomes in the past.
* This adjustment can take various forms, such as updating probabilities, refining heuristics, or incorporating new information learned during the rollout.

#Exploration-Exploitation Tradeoff:

* Rollout Policy Adaptation aims to balance exploration of new actions with exploitation of known information about the game state. 
* Adaptive rollout policies dynamically adjust this tradeoff based on the observed outcomes of previous rollouts to guide the search effectively.

#Iterative Improvement:

* Rollout Policy Adaptation is an iterative process that continuously refines the rollout policy based on the outcomes of previous rollouts. 
* Over time, the rollout policy converges towards a strategy that leads to favorable outcomes in the game.

 ###Code Execution
 monteclaro.py
## Temporal Difference Learning

Temporal Difference (TD) Learning is a reinforcement learning technique that combines elements of dynamic programming and Monte Carlo methods to learn a value function or a policy from experience. It is particularly effective in environments with unknown transition dynamics and rewards, making it suitable for a wide range of applications, including game playing, robotics, and finance.

### Basic Principles:

#Temporal Difference:

 * TD Learning updates value estimates based on the difference between the predicted value of the current state and the estimated value of the next state. 
 * Unlike Monte Carlo methods, which require full trajectories to update values, TD Learning can update values incrementally after each time step.

###Value Function:

 * TD Learning aims to learn a value function that estimates the expected return (cumulative future reward) from each state. This value function can be used to derive a policy that selects actions to maximize cumulative rewards over time.
* Prediction and Control: TD Learning can be used for both prediction (estimating value functions) and control (improving policies). In prediction, TD methods estimate the value function given a fixed policy. 
* In control, TD methods iteratively improve the policy to maximize expected rewards.

###Bootstrapping: 

* TD Learning bootstraps estimates by using the estimated values of future states to update the value of the current state.
* This allows for more efficient updates compared to Monte Carlo methods, which rely solely on actual returns.

###Exploration-Exploitation Tradeoff:

 * Like other reinforcement learning algorithms, TD Learning faces the challenge of balancing exploration of new states with exploitation of known information to maximize cumulative rewards. Various exploration strategies can be employed to address this tradeoff.

##Key Components:

#Value Function:
* The value function estimates the expected return from each state under a given policy.
* In TD Learning, this function is updated iteratively based on observed rewards and transitions between states.

#Temporal Difference Error:

The temporal difference error, often denoted as δ (delta), represents the difference between the predicted value of the current state and the estimated value of the next state. It serves as the basis for updating the value function.

#Update Rule:

The update rule in TD Learning specifies how the value function is updated based on observed rewards and state transitions. The most common update rule is the TD(λ) algorithm, which combines TD updates with eligibility traces to assign credit to states that contribute to future rewards.

#Eligibility Traces:

Eligibility traces are used to track the eligibility of states for updates based on their temporal proximity to rewards. They allow TD Learning algorithms to assign credit to states that are relevant to the observed rewards, even if they are not immediately adjacent to the reward.

#Policy Improvement:

In TD Learning for control, the policy is iteratively improved based on the estimated value function. This improvement can be achieved using techniques such as policy iteration or value iteration, which adjust the policy to maximize expected rewards over time.

#Exploration Strategies:

TD Learning algorithms employ various exploration strategies to balance exploration and exploitation. These strategies include ε-greedy exploration, softmax exploration, and upper confidence bound (UCB) exploration, among others.

#Algorithms:

TD(0):
TD(0) is a simple form of TD Learning that updates the value function based on the difference between the predicted value of the current state and the estimated value of the next state. It is a special case of TD(λ) with λ set to 0, meaning only the immediately next state is considered for updates.

#TD(λ):
TD(λ) is a more general form of TD Learning that combines TD updates with eligibility traces. It assigns credit to states based on their temporal proximity to rewards and updates the value function accordingly. The parameter λ determines the degree of bootstrapping, with λ = 0 corresponding to TD(0) and λ = 1 corresponding to Monte Carlo methods.

##Code Execution
Temporallearning.py
## Acknowledgements

 This project draws inspiration from the following sources:

Sparse Tree Search Optimality Guarantees in POMDPs with Continuous Observation Spaces
Tic Tac Toe with Monte Carlo Tree Search
What is Reinforcement Learning?
Rollout and Approximate Policy Iteration
## Appendix



Additional Resources
* Books
Sutton, R. S., & Barto, A. G. (2018). Reinforcement Learning: An Introduction. MIT Press.

*  Online Courses
Reinforcement Learning Specialization by University of Alberta & Alberta Machine Intelligence Institute on Coursera

* Tutorials and Documentation
OpenAI Gym Documentation

*  Research Papers
Silver, D., et al. (2016). Mastering the game of Go with deep neural networks and tree search. Nature, 529(7587), 484-489. Link
Mnih, V., et al. (2015). Human-level control through deep reinforcement learning. Nature, 518(7540), 529-533. Link

* Tools and Libraries
OpenAI Gym: Toolkit for developing and comparing reinforcement learning algorithms.
TensorFlow: Open-source machine learning framework developed by Google.

## API Reference

* Sparse Tree Search Optimality Guarantees in POMDPs with Continuous Observation Spaces:  
- https://www.ijcai.org/proceedings/2020/0572.pdf
* https://martin-ueding.de/posts/tic-tac-toe-with-monte-carlo-tree-search/
* https://www.synopsys.com/ai/what-is-reinforcement-learning.html
* Rollout and Approximate Policy Iteration: https://web.mit.edu/dimitrib/www/RLTopics_Lecture3.pdf




## 🔗 Links

https://github.com/Kajaganesh/Tic-Tac-Toe-using-Reinforcement-Learning/tree/main
## Conclusion 
Temporal Difference Learning is a powerful reinforcement learning technique that combines aspects of dynamic programming and Monte Carlo methods to learn value functions or policies from experience. Its ability to update values incrementally and bootstrap estimates makes it well-suited for a wide range of applications where real-time learning and decision-making are required.






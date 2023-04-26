The entire theoretical background as well as the obtained results are explained in detail in the PDF [Theory_and_Results](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Theory_and_Results.pdf) of my Master Thesis.

Probem Formulation:
We treat Job Scheduling Problems on Unrelated Machines with an initial occupation and deterministic processing times.
Both, Jobs and Machines have deadlines and weights.
We want to minimize the sum of the makespan with the weigthed sum of the Job and Machine tardinesses.

Approach:
Our approach is to apply Deep Reinforcement Learning.
We will embed these problems into a reinforcement learning environment with every decision situation being a state.
We identify policies with scheduling rules.
Then we compute the true Q-values with brute force for Job Scheduling Problems with 8 Jobs and 4 Machines.
We exctract the data from these simulated states and use them to supervisedly train a Neural Network.
This Neural Network conts architectures of Natural Language Processing models to handle the variability of the dimension in the data due to changing numbers of Jobs and Machines.
By using it as a Target Network, we can then apply Deep Reinforcement Learning techniques.
Therefore, we iteratively estimate data of Job Scheduling Problems with higher Job numbers and uptrain the Network.

Results:
We compare the scheduling costs obtained by our Neural Network to the optimal costs.
We will find that they do not differ much.
We then compare them to a heuristic scheduling algorithm.
We will see that our Neural Network vastly outperforms it.

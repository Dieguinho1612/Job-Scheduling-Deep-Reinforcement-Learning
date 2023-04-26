# Theory:

The entire theoretical background as well as the obtained results are explained in detail in the PDF [Theory_and_Results](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Theory_and_Results.pdf) of my Master Thesis.

<ins>Probem:</ins><br>
We treat Job Scheduling Problems on Unrelated Machines with an initial occupation and deterministic processing times.<br>
Both, Jobs and Machines have deadlines and weights.<br>
We want to minimize the sum of the makespan with the weigthed sum of the Job and Machine tardinesses.<br>

<ins>Approach:</ins><br>
Our approach is to apply Deep Reinforcement Learning.<br>
We will embed these problems into a reinforcement learning environment with every decision situation being a state.<br>
We identify policies with scheduling rules.<br>
Then we compute the true Q-values with brute force for Job Scheduling Problems with 8 Jobs and 4 Machines.<br>
We exctract the [data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data) from these simulated states and use them to supervisedly train a Neural Network.<br>
This [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5) contains architectures of Natural Language Processing models to handle the variability of the dimension in the data due to changing numbers of Jobs and Machines.<br>
By using it as a Target Network, we can then apply Deep Reinforcement Learning techniques.
Therefore, we iteratively estimate [data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/EstimData) of Job Scheduling Problems with higher Job numbers and uptrain the Network.<br>

<ins>Results:</ins><br>
We compare the scheduling costs obtained by our Neural Network to the optimal costs.<br>
We will find that they do not differ much.<br>
We then compare them to a heuristic scheduling algorithm.<br>
We will see that our Neural Network vastly outperforms it.<br>

# Code

The Notebook "Main" goes through the entire process listed above and guides the user through
- how everything was constructed and we obtained the Neural Network. This enables him to reproduce everything.
- how to use the given code to apply the Neural Network as a scheduling rule to any Job Scheduling Problem of choice and analyze the results.

It makes use of the following [Notebooks](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Notebooks) in which all necessary classes, functions and Network layer were defined:

- [Global_Variables](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Global_Variables.ipynb):
  -- Helper Notebook to make global variables accessible for all other Notebooks

- [Jobs_and_Machines](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Jobs_and_Machines.ipynb):
  -- Definition of classes for Jobs and Machines

- [States_and_Policies](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/States_and_Policies.ipynb):
  -- Definition of class of states
  -- Function to compute initial state which represents Job Scheduling Problem
  --Function to iteratively compute all states
  --Function to recursively calculate all Q-values
  --Function to create optimal policy and random policy
  
  - [Data_for_NN](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Data_for_NN.ipynb):
    -- Function to extract data from states
    
 - [Random_Generator](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Random_Generator.ipynb):
  -- Function to generate random Job Scheduling Problems with random Jobs and Machines
  
- [Action_Pointer](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Action_Pointer.ipynb):
  -- Layers for Neural Network
  -- Loss function and metric for Neural Network
  
- [Scheduling_Decisions](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Scheduling_Decisions.ipynb):
  -- Function to deduce policy from Neural Network
  -- Function to calculate policy costs
  -- Function to use Neural Network as Target Network to estimate data from Scheduling Problems with higher numbers of Jobs
  -- Function to apply heuristic algorithm as scheduling rule
  -- Function to compare average scheduling costs for random Job Scheduling Problems between optimal policy, Neural Network policy and heuristic policy  
  
- [Visualizations](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Visualizations.ipynb):
  -- Functions to visualize schedules. In specific, to print schedule as gantt chart

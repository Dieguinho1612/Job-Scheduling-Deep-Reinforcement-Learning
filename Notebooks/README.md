### Main Notebook

The Notebook "Main" goes through the entire process listed above and guides the user through
* how everything was constructed and how we obtained the Neural Network. This enables him to reproduce everything.
* how to use the given code to apply the Neural Network as a scheduling rule to any Job Scheduling Problem of choice and analyze the results.

It makes use of the following Notebooks in which all necessary classes, functions and Network layer were defined:

- [Global_Variables](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Global_Variables.ipynb):
  - Helper Notebook to make global variables accessible for all other Notebooks

- [Jobs_and_Machines](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Jobs_and_Machines.ipynb):
  - Definition of classes for Jobs and Machines

- [States_and_Policies](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/States_and_Policies.ipynb):
  - Definition of class of states
  - Function to compute initial state which represents Job Scheduling Problem
  -Function to iteratively compute all states
  -Function to recursively calculate all Q-values
  -Function to create optimal policy and random policy
  
- [Data_for_NN](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Data_for_NN.ipynb):
  - Function to extract data from states
    
- [Random_Generator](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Random_Generator.ipynb):
  - Function to generate random Job Scheduling Problems with random Jobs and Machines
  
- [Action_Pointer](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Action_Pointer.ipynb):
  - Layers for Neural Network. In specific Action-Pointer Decoder
  - Loss function and metric for Neural Network
  
- [Scheduling_Decisions](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Scheduling_Decisions.ipynb):
  - Function to deduce policy from Neural Network
  - Function to calculate policy costs
  - Function to use Neural Network as Target Network to estimate data from Scheduling Problems with higher numbers of Jobs
  - Function to apply heuristic algorithm as scheduling rule
  - Function to compare average scheduling costs for random Job Scheduling Problems between optimal policy, Neural Network policy and heuristic policy  
  
- [Visualizations](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Visualizations.ipynb):
  - Functions to visualize schedules. In specific, to print schedule as gantt chart


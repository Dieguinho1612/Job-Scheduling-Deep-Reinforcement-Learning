# Main Notebook

The Notebook [Main.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Main.ipynb) guides the user through the entire process of implementing the problem and our approach to it. It illustrates how we obtained our Neural Network and explains how to use it and how to analyse its performance. This enables the user to reproduce everything and to use the code of this git repository to apply the Neural Network to any Job Scheduling Problem of choice.<br>

It makes use of the following Notebooks in which all necessary classes, functions and Network layers were defined:

- [Global_Variables.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Global_Variables.ipynb):
  - Helper Notebook to make global variables accessible for all other Notebooks

- [Jobs_and_Machines.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Jobs_and_Machines.ipynb):
  - Definition of classes for Jobs and Machines

- [States_and_Policies.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/States_and_Policies.ipynb):
  - Definition of class of states
  - Function to compute initial state which represents Job Scheduling Problem
  -Function to iteratively compute all states
  -Function to recursively calculate all Q-values
  -Function to create optimal policy and random policy
  
- [Data_for_NN.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Data_for_NN.ipynb):
  - Function to extract data from states
    
- [Random_Generator.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Random_Generator.ipynb):
  - Function to generate random Job Scheduling Problems with random Jobs and Machines
  
- [Action_Pointer.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Action_Pointer.ipynb):
  - Layers for Neural Network. In specific Action-Pointer Decoder
  - Loss function and metric for Neural Network
  
- [Scheduling_Decisions.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Scheduling_Decisions.ipynb):
  - Function to deduce policy from Neural Network
  - Function to calculate policy costs
  - Function to use Neural Network as Target Network to estimate data from Scheduling Problems with higher numbers of Jobs
  - Function to apply heuristic algorithm as scheduling rule
  - Function to compare average scheduling costs for random Job Scheduling Problems between optimal policy, Neural Network policy and heuristic policy  
  
- [Visualizations.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Visualizations.ipynb):
  - Functions to visualize schedules. In specific, to print schedule as gantt chart


# Scripts

We have computed large data sets and tested the Neural Network on a large set of Job Scheduling Problems. To do so more efficiently, we have used a cluster. The following Notebooks are the scripts that have been used for this.

- [Script_Compute_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compute_Data.ipynb): This is the script to compute and save the data sets that that have been used to train, validate and test the Neural Networks by simulating random Job Scheduling Problem according to some conditions chosen by the user.

- [Script_Estimate_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Estimate_Data.ipynb): This is the script to estimate and save data for a chosen quantity of randomly simulated Job Scheduling Problems whose number of Jobs has been increased by 1.

- [Script_Compare_Schedules.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compare_Schedules.ipynb): In this script, the average scheduling costs arising by different versions of the Neural Network, the heuristic algorithm and the optimal policy have been compared. The respective ratios got printed.


# Side Notebooks

These Notebooks have been run through already. They can be reused to reproduce, vary or adapt our applied approach.

- [LSTM_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/LSTM_Data.ipynb): Transforms all saved dictionaries of data points from any data set directory into the correct form for the Neural Network to read. Whenever data has been created (even if the data has been estimated), this Notebook has to be rerun from the start and the respective directory of this data has to be selected.

- [Neural_Network.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Neural_Network.ipynb): In this Notebook we have loaded the transformed data and defined, supervisedly trained, validated, tested and finally saved our principal [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5).

- [Uptrain_Neural_Network.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Uptrain_Neural_Network.ipynb): In this Notebook we uptrained the previous version of our Neural Network on the estimated data whose number of Jobs has been increased by 1. Its updated version then got saved. We have done so for Job numbers from 9 up to 12.

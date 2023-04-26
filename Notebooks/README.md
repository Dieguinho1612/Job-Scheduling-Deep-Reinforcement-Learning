# Main Notebook

The Notebook [Main](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Main.ipynb) goes through the entire process listed above and guides the user through
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

# Scripts

We have computed large data sets and tested the Neural Network on a large set of Job Scheduling Problems. To do so more efficiently, we have used a cluster. The following Notebooks are the scripts that have been used for this.

- [Script_Compute_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compute_Data.ipynb): This is the script to compute the data sets that we have used to train, validate and test the Neural Networks. It simulates a Job Scheduling Problem according to some conditions given by the user and computes all their states together with the real Q-values. Then, it extracts the corresponding [dictionary of data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Data/DataSet_01/data_01_0000.pickle), indexes it and saves inside the the [data directory](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data) within a [sub-directory](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/DataSet_01) that is defined as an indexed set of data.

- [Script_Estimate_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Estimate_Data.ipynb): This is the script to simulate a chosen quantity of Job Scheduling Problems consisting of a number of Jobs which has been increased by 1. For each of these problems it then creates the initial state in which all Jobs and Machines still remain as well as iteratively all successor states in which a Machine has been turned off until only 2 Machines are active. For these states it then estimates the Q-values by using the previous version of our Neural Network as Target Network. Subsequently, it turns their information into a [dictionary of data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Data/EstimData/9_Jobs/estim_data_9_Jobs_1.pickle). All these dictionaries are then saved in a [sub-directory](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/EstimData/9_Jobs) of the directory [EstimData](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/EstimData) corresponding to the increased number of Jobs.

- [Script_Compare_Schedules](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compare_Schedules.ipynb): In this script a chosen quantity of Job Scheduling Problems is simulated. For each of them, schedules are created by using the Neural Network, the heuristic algorithm and, optionally, the optimal policy. The ratios between their produced scheduling costs is calculated. In the end, the average of these ratios gets printed for every policy used. The user can give a list of numbers of Jobs and Machines. The entire process gets applied to every combination of them.

# Side Notebooks

These Notebooks have been run through already. They can be reused to reproduce, vary or adapt our applied approach.

- [LSTM_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/LSTM_Data.ipynb): Transforms all saved dictionaries of data points from any data set directory into the correct form for the Neural Network to read, since its base layer are paralelly run LSTMs. So whenever data has been created (even if the data has been estimated), this Notebook has to be rerun from the start and the directory of this data has to be selected. A a new folder called [LSTM_Data_RR_xx](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/DataSet_01/LSTM_Data_RR_01) is then created within the original directory of the data set <i>xx</i>. In there, it stores the transformed data in several [files](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Data/DataSet_01/LSTM_Data_RR_01/8-jobs-4-machines_01.pickle), one for every combination of reamining numbers of Jobs and Machines. Each of these files is a dictionary of the transformed data from the corresponding states.

- [Neural_Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Neural_Network.ipynb): In this Notebook we have loaded the transformed data and defined, supervisedly trained, validated, tested and finally saved our principal [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5).
- [Uptrain_Neural_Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Uptrain_Neural_Network.ipynb): In this Notebook we have loaded the [transformed estimated data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data/EstimData/9_Jobs/LSTM_EstimData_RR) for an increased number of Jobs and the [version](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Uptrained_Neural_Network_11_Jobs.h5) of our Neural Network from the previous iteration. We have then uptrained it on all so far estimated data and [saved it](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Uptrained_Neural_Network_12_Jobs.h5) with its updated parameters. The last time it has been run on 12 Jobs. If this number shall be further increased, the entire Notebook has to be run again, using the corresponding set of estimated data.


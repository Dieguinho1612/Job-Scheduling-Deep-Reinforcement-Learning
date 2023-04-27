# Data

The following directories are data sets of Job Scheduling Problems. The included files are dictionaries. Every item is the data from a state whose amount of remaining Jobs and Machines defines the assigned key.<br>

The Notebook [LSTM_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/LSTM_Data.ipynb) has been run of each directory to merge all included dictionaries. It did so by saving the concatenation of all lists belonging to the same key in the sub-directory <i>LSTM_Data_RR</i>. Thereby, the immanent data got transformed into a compatible form to train, validate, test and uptrain our [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5).<br>

### Data Set 1-10

Used as Training Set.<br>
Created by running [Script_Compute_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compute_Data.ipynb) on a cluster. Random Job Scheduling Problems consisting of 8 Jobs and 4 Machines have been simulated with regards to some chosen conditions. Each of them resulted in a data dictionary, balanced in the distribution of optimality over the feasible actions. Here, the true target values have been computed by brute force. Every directory contains 10.000 such data dictionaries.

### Data Set 98 + 99

Used as Validation and Test set respectively.<br>
Created analogously but without being balanced. Each of them contains 10.000 data dictionaries as well.

### EstimData

Used to train the Neural Network on successively increasing numbers of Jobs.<br>
Created by running [Script_Estimate_Data.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Estimate_Data.ipynb) on a cluster. For every such increased number of Jobs <i>n</i>, 100.000 Jobs Scheduling Problems with <i>n</i> Jobs and 4 Machines have been simulated. The target values of the corresponding states have been estimated by using the Neural Network of the previous iteration as Target Network. The resulting data has then been safed as dictionaries in the respective sub-directory for Job numbers from 9 to 12. Unlike in the supervised case, every dictionary contains the data of 125 different Job Scheduling Problems of the same <i>n</i>.

# Data

The following data has been used to train, validate, test and uptrain our [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5). After their creation, the Notebook [LSTM_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/LSTM_Data.ipynb) has been run of each of these directories, merging the corresponding immanent data dictionaries, transforming them accordingly, splitting them into subsets and saving them in the respective sub-directory <i>LSTM_Data_RR</i>. Each of these subsets is defined by the number of remaining Jobs and Machines of the states whose data it contains.<br>

### Data Set 1-10

Used as Training Set.<br>
Created by running [Script_Compute_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compute_Data.ipynb) on a cluster. Random Job Scheduling Problems consisting of 8 Jobs and 4 Machines have been simulated with regards to some chosen conditions. Each of them resulted in data dictionary, balanced in the distribution of optimality over the feasible actions.<br>
Every directory contains 10.000 such data dictionaries.

### Data Set 98 + 99

DataSet98 is the validation set, DataSet99 the test test.<br>
Created analogously but without being balanced. Each of them contain 10.000 data dictionaries as well.

### EstimData

Used to train the Neural Network on successively increasing numbers of Jobs.<br>
Created by running [Script_Compute_Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Script_Compute_Data.ipynb) on a cluster. For every such increased number of Jobs <i>n</i>, 100.000 Jobs Scheduling Problems with <i>n</i> Jobs and 4 Machines have been simulated. The Q-values of the corresponding states have been estimated by using the Neural Network of the previous iteration as Target Network. The estimated data has been safed in the respective sub-directory for Job numbers from 9 to 12.

# Theory

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
We exctract the data from these simulated states and use them to supervisedly train a Neural Network.<br>
This Neural Network contains architectures of Natural Language Processing models to handle the variability of the dimension in the data due to changing numbers of Jobs and Machines.<br>
By using it as a Target Network, we can then apply Deep Reinforcement Learning techniques.
Therefore, we iteratively estimate data of Job Scheduling Problems with higher Job numbers and uptrain the Network.<br>

<ins>Results:</ins><br>
We compare the scheduling costs obtained by our Neural Network to the optimal costs.<br>
We will find that they do not differ much.<br>
We then compare them to a heuristic scheduling algorithm.<br>
We will see that our Neural Network vastly outperforms it.<br>

# Code

All the code is written in Python 3 and uploaded as Jupyter [Notebooks](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Notebooks). The principal Notebook is [Main.ipynb](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Notebooks/Action_Pointer.ipynb).

# Files

Besides the directory of Notebooks, there are two more directories containing files:

- [Neural Networks](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Neural_Networks): Contains the <i>h5</i> file of the principal [Neural Network](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/blob/main/Neural_Networks/Neural_Network.h5) after it has been trained supervisedly. It also contains its <i>h5</i> files after having been uptrained to higher numbers of Jobs by using the corresponding estimated data sets.
- [Data](https://github.com/Dieguinho1612/Job-Scheduling-Deep-Reinforcement-Learning/tree/main/Data): Contains all the data we computed to train, validate and test the Neural Network. It also contains all the estimated data that we have used to uptrain it.


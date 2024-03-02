# ARC-Solver10
By: Somayyeh Gholami & Mehran Kazeminia
<div>
    <img src='https://cdn-images-1.medium.com/max/1000/1*7s_cV4TLZ1L31MJNj2Rk5w.png'> 
</div>

## Abstraction and Reasoning Challenge :

- The ARC challenge was first launched on Kaggle in February 2020. Mr. François Chollet and his colleagues had prepared and arranged the corpus of tasks as well as the rules and regulations of the competition. We and the rest of the participants tried hard to get a good score, but it did not happen and most of the participants did not succeed. Various types of neural networks, different machine learning algorithms and other efforts such as using the Z3 programming language did not have good results.

- After the challenge time was over, most of the participants published their notebooks. The successes were relatively limited, but different views can be seen in these notebooks. Of course, we started our work again and using our new ideas and the ideas in the public notebooks, we managed to solve at least thirty percent of the tasks.

- In 2023, the ARC challenge was again held at ["Lab42"](https://lab42.global/) and we managed to get the best score in that competition. Our method was a combination of "Sklearn tree" and "Genetic Algorithm" as well as several solvers that solve tasks with specific characteristics. Finally, we combined our results with the results of the ["icecuber"](https://www.kaggle.com/code/icecuber/arc-1st-place-solution) notebook. Our notebook was called "Solver 7".
<div>
    <img src='https://cdn-images-1.medium.com/max/1000/1*P6RH0HLuzKFw4DAGxIVdEw.png'> 
</div>

## Explanation for "Solver 10" method :

- ARC is more than a competition for us and our main goal is not just to get a better score. Rather, it is interesting for us to understand how and with what process the machine takes the initial steps of "Abstraction and Reasoning" and we are interested in being a part of this story. That's why we designed and implemented "Solver 10" and are still developing it.

- Two parts can be imagined for "Solver 10", the first part includes hundreds of solvers, each of which can solve one or more types of tasks. When a solver can correctly solve all "train_inputs" of a task (that is, return exactly "train_output" for each "train_input"), it will definitely return the correct "test_output" if it receives "test_input".

- Please note that this is the definition of a standard task. That is, if a function succeeds in solving all "train_input" of a standard task, this function will surely solve "test_input" as well. This is exactly like the human performance in front of the same type of questions.

- The second part of "Solver 10" is to create an algorithm using machine learning. We have hundreds and thousands of solvers (keys) in "Solver 10", but when facing a task (a lock), the machine does not know which solver (which key) to use. That is, the winning solver (golden key) is not known. We created an algorithm that by seeing a task and checking its specifications, the machine can prepare a list of available solvers. In this list, the solvers are sorted according to the probability of winning.

- The method of operation is that the machine checks the specifications of all "train_inputs" and "train_outputs" and "test_inputs" of a task and considers about a hundred binary features for this task. In addition, the machine has already assigned the same features to each and every solver (that is, it has calculated about a hundred features for each solver). It is enough to sort the solvers based on their proximity to the desired task with one of the machine learning methods. We have used the "NearestNeighbors" algorithm to do this.

- To assign features to the solver, the features must be calculated based on the "input" specifications and the "output" specifications of the solver. If we have a suitable number of "input" and "output" for each solver, we can calculate their features and assign the average of these features to the solver.

- However, we do not have enough "input" and "output" for each solver. For this reason, each solver tried all the "inputs" in the "Training file" and "Evaluation file" and, if successful, created an "output" for the "input". Then it calculates features for each pair of "input" and "output" and assigns the average of these features to this solver.

- It is always possible to improve the accuracy of the features of the solvers. That's why we wrote the "upgrade_solvers()" function. When a solver gives a correct answer to a task, this function calculates new values for the features based on the inputs and outputs of this task, and then replaces the values of the features of this solver with the average of the new and old values.

- Fortunately, Solver 10's performance in finding the winning solver (for each task) was even better than our initial prediction. Meanwhile, feature calculations for solvers seem complicated. If you directly read the codes in the "Setting tasks and solvers" section, it might help you.

## Advantages of the "Solver 10" method :

- The number and variety of solvers in the "Solver 10" method has no limits. That is, for the machine to answer any question (open any lock), it is enough that its solver (its key) has already been stored. In addition, new solvers can always be created for new questions.

- Another advantage is that "Solver 10" answers are definitely correct, provided that the question is standard (we explained the specifications of a standard task above).

- The third advantage is the very good speed of the "Solver 10" method. As we explained above, if assigning features to solvers is done carefully, the winning solver will definitely be in the first ten to twenty percent of the list. That is, for each task, only the first ten to twenty percent of the sorted list of solvers should be tried (whether the winning solver is found or not).

- The above advantages do not exist in any of the other methods such as decision trees or genetic algorithms. These methods can only answer some questions by spending a lot of time. At the same time, there is no certainty of the correctness of their answers.

- Let's not forget that learning "Abstraction and Reasoning" for machines is a broad topic. But in this connection, the first and most essential topic for machines is learning "Core Knowledge". Our estimate is that if we create about ten thousand solvers, we can answer all the tasks related to "Core Knowledge" and of course, it is obvious that the number of solvers can always be increased. We have created more than six hundred solvers in the first step.

## Last Explanation : 

- Machines typically go through three steps to answer ARC tasks (as well as humans to answer intelligence questions). In the first stage, all the information of a task, including inputs and outputs, is checked, and based on these observations, several "hypotheses" are considered to perform the task correctly. In the second stage, these hypotheses are tested, so that the correct theory is chosen. In the third stage, the best theory is implemented for ARC, or for human intelligence questions, the correct option is selected among several options.

- Humans are much better than machines in the first stage. But in the second and third stages, the matter can be exactly the opposite. That is, if all the basic keys are given to the machine, the power and speed of the machine will be thousands of times human. And this great power in the second and third stages can overcome the weaknesses of the first stage.

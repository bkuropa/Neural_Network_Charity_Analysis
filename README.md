# Neural_Network_Charity_Analysis

## Analysis Overview
The company Alphabet Soup has provided some initial data which is hoped to be well-processed by a (basic) neural network to gain stronger understanding of what drives a successful loan based on such information as application types, ammount of funding asked/provided, industry affiliation, or organization type.  At the end of the model, it is hoped that a true/false classifier (sigmoid here) can determine if an application will pass or not.

## Results

All models were tested with input columns that were heavily binned to accomodate small groups in one input.  The same models were run on columns where binned data was very rare, including tests where less driving columns were elinated all together.  Model 1 is very straight foward involving 3 relu layers (80:50:20 nodes) ending in a sigmoid layer.  A simple Adam optimizer is used in compiling.

![Model_1](https://user-images.githubusercontent.com/19878877/169559047-a020b99a-134f-41cd-988e-245b1faaaac6.png)
After 10 itterations, the model is largely compliled but is left to run for 40 epochs for good measure.  The model finishes with a (large) loss of 0.5714 and an underwhelming accuracy of 0.7295.  Test data is reflected with a loss = 0.5649 and an accuracy = 0.7320.

Model 2 attempts to optimize the nature of linear unit refinements using LeakyReLU to deal with potential negative behaviours, elu for even stronger negative inputs, and at one point the more refined PreLu.  Combinations of the different functions introduced to the hidden layers caused little to no positive behaviour on the model which again flattened around 73%.  The numbers are negligably changed with respect to model one.
![Model_2](https://user-images.githubusercontent.com/19878877/169559090-e58f75d0-d6bb-419a-b058-8289418e2da2.png)

Model 3 carried the strongest potential by introducing the non-linear approach of a Tanh activation function and in fact performed "the best" with a 74% model in combination with LeakyReLu.  The performance however is still negligably improved and the test data again shows an accuracy of around 72 to 73%.
![Model_3](https://user-images.githubusercontent.com/19878877/169559120-d37d4bf4-f86c-43f2-8e8b-c832bbbc7fc8.png)
For added thoroughness in understanding and analysis, model 3 also attempts to study Adam vs. Nadam vs. Adamax optimizers.  In this particular dataset, there is little to no change from 73% with optimization refinement either.

Model 4 is a curiosity due to the emerging popularity of Gelu linear unit activation function.  The Gaussian Error Linear Unit uses a gated approach instead of a simple negative or positive.  Behind the scenenes, there should also be a Tanh portion incorporated into its function as well. 
![Model_4](https://user-images.githubusercontent.com/19878877/169559154-61dbb41e-1a8c-42cb-99b1-46beae9f0815.png)
Although, quite efficient at reaching 0.739, it unsurprisingly flattens out like those attemps made before it.  This dataset in its current form, cannot show much improvement without perhaps a backwards propigation or hopefully a larger set of input data.


An UNRELIABLE dataset experiment is also run:  re-insert the **Names** column from the dataset.  The model training in this case can actually excel up to a **loss of 8% and show an accuracy of 96%**!!  This transfers awkwardly to the testing data which shows a high loss (0.62) and accuracy of 79.28%.  Showing as the only major mechanism for improvement, implies something strange.  The input dataset appears to be leaning heavily on the applications from "repeat customers".  Now in charity environments, applications are often evaluated with influence of the name holding (or should be holding) little to no influence!
![Names_model](https://user-images.githubusercontent.com/19878877/169559179-8e26a811-0f06-4563-be45-3c60fed9205c.png)

![Names_output](https://user-images.githubusercontent.com/19878877/169559211-e2950741-8e19-48a8-aaea-660975db34d1.png)


## Summary
The data is quite curious in the sense that this neural network can make little performance changes short of outright eliminating (for terrible results) one of three influential columns such as the application type submitted.  Likewise, binning and un-binning the same columns makes little change of the performance as does modification of the neural networks hidden layer sizes, activation functions, or optimization algorithms.  In short, my only recommendation is to introduce a different style of netowrk such as back propigation perhaps or ideally intruce further training data that has a wider breadth of applications and results.  For a base-level investigation into chartiy networks a 73% may be useful but proper use of a neural network and satisfactory reports should not be generated at this point without further refinement.


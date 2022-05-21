# Neural_Network_Charity_Analysis

## Analysis Overview


## Results

All models were tested with input columns that were heavily binned to accomodate small groups in one input.  The same models were run on columns where binned data was very rare, including tests where less driving columns were elinated all together.  Model 1 is very straight foward involving 3 relu layers (80:50:20 nodes) ending in a sigmoid layer.  A simple Adam optimizer is used in compiling.

![Model_1](https://user-images.githubusercontent.com/19878877/169559047-a020b99a-134f-41cd-988e-245b1faaaac6.png)
After 10 itterations, the model is largely compliled but is left to run for 40 epochs for good measure.  The model finishes with a (large) loss of 0.5714 and an underwhelming accuracy of 0.7295.  Test data is reflected with a loss = 0.5649 and an accuracy = 0.7320.

Model 2 attempts to optimized the 
![Model_2](https://user-images.githubusercontent.com/19878877/169559090-e58f75d0-d6bb-419a-b058-8289418e2da2.png)


![Model_3](https://user-images.githubusercontent.com/19878877/169559120-d37d4bf4-f86c-43f2-8e8b-c832bbbc7fc8.png)


![Model_4](https://user-images.githubusercontent.com/19878877/169559154-61dbb41e-1a8c-42cb-99b1-46beae9f0815.png)


![Names_model](https://user-images.githubusercontent.com/19878877/169559179-8e26a811-0f06-4563-be45-3c60fed9205c.png)
![Names_output](https://user-images.githubusercontent.com/19878877/169559211-e2950741-8e19-48a8-aaea-660975db34d1.png)


## Summary



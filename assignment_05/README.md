
# Assignment 5


Continue the in-class exercise using the script 
```data_mining_A5.R``` in RStudio, 
which is a modified version of the script 
```data_mining_demo.R```.  
In this exercise, we generate simulated data for car prices, 
which depend on mileage, 
whether the car has been in an accident, 
and whether the car has sustained major structural damage, 
which can happen only as a result of an accident. 



Run the entire script and observe the output from the 
series of models.


		
a) Verify that damage occurs in both the samples. 
	Observe the output under the code blocks in lines 123-139
	to verify that the bottom right numbers 
	(the number of observations with accidents with damages) are not zero.
	If one of these bottom-right numbers is zero, run the script again. 
	
```

  # Check that damages occurred only in accidents:
> table(car_data[, 'accident'], car_data[, 'damage'])
   
      0   1
  0 120   0
  1  66  14
> # Data errors are the largest cause of problems in model-building.
> 
> # Check the subsamples for estimation and testing.
> # Estimation sample:
> table(car_data[obsns_for_estimation, 'accident'],
+       car_data[obsns_for_estimation, 'damage'])
   
     0  1
  0 61  0
  1 31  9
> # Testing sample:
> table(car_data[!obsns_for_estimation, 'accident'],
+       car_data[!obsns_for_estimation, 'damage'])
   
     0  1
  0 59  0
  1 35  5
```

		
b) Copy and paste the table of selected models and R-squared values, 
	under the command ```print(best_models)``` on line 315. 
	
```
 print(best_models)
   num_vars best_new_variable R2_in_sample R2_out_sample
1         1            damage    0.6349735     0.3863638
2         2          accident    0.7129361     0.5197799
3         3         mileage_2    0.7630518     0.6478417
4         4       rainfall_15    0.7688119     0.6474577
5         5       rainfall_14    0.7767440     0.6161432
6         6       rainfall_12    0.7826869     0.6015658
7         7       rainfall_11    0.7883343     0.6178075
8         8        rainfall_2    0.7944362     0.6172759
9         9        rainfall_3    0.7973633     0.6282831
10       10         mileage_1    0.7987095     0.6421702
11       11        rainfall_8    0.7994644     0.6419398
12       12        rainfall_4    0.7990477     0.6234630
13       13        rainfall_6    0.7983493     0.6175945
14       14        rainfall_9    0.7974578     0.6087890
15       15        rainfall_7    0.7963443     0.5999830
16       16       rainfall_13    0.7949009     0.6043113
17       17       rainfall_20    0.7932647     0.6017820
18       18       rainfall_10    0.7914524     0.5986398
19       19       rainfall_16    0.7891630     0.6013813
20       20       rainfall_17    0.7867610     0.5916317
21       21       rainfall_19    0.7842403     0.5935735
22       22       rainfall_18    0.7815478     0.5927403
23       23        rainfall_1    0.7787873     0.5942940
24       24        rainfall_5    0.7758772     0.5940798

```

		
c) Compare the models according to the in-sample ```R-bar-squared``` 
		under the column ```R2_in_sample```. 
		Which model is best under this criterion? 
		The variables in the model are listed in the column ```best_new_variable```
		up to the row of the chosen model. 

```

"The best model with 10 variables is "
[1] "car_price ~  damage + accident + mileage_2 + rainfall_15 + rainfall_14 + rainfall_12 + rainfall_11 + rainfall_2 + rainfall_3 + mileage_1"
[1] "with an R-squared of 0.798710."

THE BEST NEW VARIABLE IS MILEAGE_1

```
		
d) Compare the models according to the out-of-sample ```R-bar-squared``` 
		under the column ```R2_out_sample```. 
		Which model is best under this criterion? 
		The variables in the model are listed in the column ```best_new_variable```
		up to the row of the chosen model. 

```

"The best model with 4 variables is "
[1] "car_price ~  damage + accident + mileage_2 + rainfall_15"
[1] "with an R-squared of 0.768812."
[1] "" The best new variable is RAINFALL_15


```
		
e) Compare the differences between the two models.
		Do any variables appear in one model and not the other?
		Which model do you recommend on the basis of this data? 
		Is your recommended model the same as the true model? 



```
The model incorporating "in Sample" includes rainfall_14 + rainfall_12 + rainfall_11 + rainfall_2 + rainfall_3 + mileage_1"
which are not included in the "out of Sample" model

I would recommend to use the "in sample " model for accuracy due to a higher R squared (.798)


```

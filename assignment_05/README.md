
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

> summary(car_data)
    obsn_num        car_price        mileage         accident  
 Min.   :  1.00   Min.   :10197   Min.   :25883   Min.   :0.0  
 1st Qu.: 50.75   1st Qu.:33975   1st Qu.:42875   1st Qu.:0.0  
 Median :100.50   Median :37461   Median :49049   Median :0.0  
 Mean   :100.50   Mean   :36594   Mean   :50240   Mean   :0.4  
 3rd Qu.:150.25   3rd Qu.:40575   3rd Qu.:57494   3rd Qu.:1.0  
 Max.   :200.00   Max.   :49057   Max.   :75642   Max.   :1.0  
     damage        epsilon           mileage_1       mileage_2    
 Min.   :0.00   Min.   :-12707.5   Min.   :26309   Min.   :20473  
 1st Qu.:0.00   1st Qu.: -2743.2   1st Qu.:43205   1st Qu.:42620  
 Median :0.00   Median :  -124.6   Median :50230   Median :49214  
 Mean   :0.06   Mean   :  -158.0   Mean   :50603   Mean   :50319  
 3rd Qu.:0.00   3rd Qu.:  2345.7   3rd Qu.:57677   3rd Qu.:59015  
 Max.   :1.00   Max.   : 12080.0   Max.   :82016   Max.   :78763  
   rainfall_1     rainfall_2     rainfall_3     rainfall_4      rainfall_5  
 Min.   :0.00   Min.   :0.00   Min.   :0.00   Min.   :0.000   Min.   :0.00  
 1st Qu.:0.00   1st Qu.:0.00   1st Qu.:0.00   1st Qu.:0.000   1st Qu.:0.00  
 Median :0.00   Median :0.00   Median :0.00   Median :0.000   Median :0.00  
 Mean   :0.29   Mean   :0.27   Mean   :0.25   Mean   :0.235   Mean   :0.25  
 3rd Qu.:1.00   3rd Qu.:1.00   3rd Qu.:0.25   3rd Qu.:0.000   3rd Qu.:0.25  
 Max.   :1.00   Max.   :1.00   Max.   :1.00   Max.   :1.000   Max.   :1.00  
   rainfall_6      rainfall_7     rainfall_8     rainfall_9     rainfall_10  
 Min.   :0.000   Min.   :0.00   Min.   :0.00   Min.   :0.000   Min.   :0.00  
 1st Qu.:0.000   1st Qu.:0.00   1st Qu.:0.00   1st Qu.:0.000   1st Qu.:0.00  
 Median :0.000   Median :0.00   Median :0.00   Median :0.000   Median :0.00  
 Mean   :0.285   Mean   :0.26   Mean   :0.21   Mean   :0.285   Mean   :0.26  
 3rd Qu.:1.000   3rd Qu.:1.00   3rd Qu.:0.00   3rd Qu.:1.000   3rd Qu.:1.00  
 Max.   :1.000   Max.   :1.00   Max.   :1.00   Max.   :1.000   Max.   :1.00  
  rainfall_11    rainfall_12     rainfall_13     rainfall_14    rainfall_15  
 Min.   :0.00   Min.   :0.000   Min.   :0.000   Min.   :0.00   Min.   :0.00  
 1st Qu.:0.00   1st Qu.:0.000   1st Qu.:0.000   1st Qu.:0.00   1st Qu.:0.00  
 Median :0.00   Median :0.000   Median :0.000   Median :0.00   Median :0.00  
 Mean   :0.21   Mean   :0.265   Mean   :0.215   Mean   :0.26   Mean   :0.27  
 3rd Qu.:0.00   3rd Qu.:1.000   3rd Qu.:0.000   3rd Qu.:1.00   3rd Qu.:1.00  
 Max.   :1.00   Max.   :1.000   Max.   :1.000   Max.   :1.00   Max.   :1.00  
  rainfall_16    rainfall_17     rainfall_18     rainfall_19  
 Min.   :0.00   Min.   :0.000   Min.   :0.000   Min.   :0.00  
 1st Qu.:0.00   1st Qu.:0.000   1st Qu.:0.000   1st Qu.:0.00  
 Median :0.00   Median :0.000   Median :0.000   Median :0.00  
 Mean   :0.26   Mean   :0.235   Mean   :0.235   Mean   :0.22  
 3rd Qu.:1.00   3rd Qu.:0.000   3rd Qu.:0.000   3rd Qu.:0.00  
 Max.   :1.00   Max.   :1.000   Max.   :1.000   Max.   :1.00  
  rainfall_20   
 Min.   :0.000  
 1st Qu.:0.000  
 Median :0.000  
 Mean   :0.245  
 3rd Qu.:0.000  
 Max.   :1.000  
> table(car_data[, 'accident'], car_data[, 'damage'])
   
      0   1
  0 120   0
  1  68  12
> table(car_data[obsns_for_estimation, 'accident'],
+       car_data[obsns_for_estimation, 'damage'])
   
     0  1
  0 60  0
  1 22  4


```

		
b) Copy and paste the table of selected models and R-squared values, 
	under the command ```print(best_models)``` on line 315. 
	
```

print(best_models)
   num_vars best_new_variable R2_in_sample R2_out_sample
1         1            damage    0.5371096     0.5250311
2         2          accident    0.6050222     0.6477931
3         3         mileage_1    0.6248664     0.6890266
4         4        rainfall_2    0.6359661     0.6944811
5         5       rainfall_10    0.6415186     0.6848077
6         6       rainfall_11    0.6437760     0.6813003
7         7       rainfall_15    0.6468490     0.6798764
8         8       rainfall_18    0.6476759     0.6852436
9         9       rainfall_20    0.6469862     0.6843336
10       10        rainfall_6    0.6457145     0.6966894
11       11        rainfall_3    0.6443728     0.7074315
12       12       rainfall_17    0.6427472     0.7058917
13       13       rainfall_12    0.6407168     0.7030997
14       14       rainfall_16    0.6377721     0.6996130
15       15        rainfall_9    0.6344697     0.6970422
16       16       rainfall_14    0.6309816     0.6909611
17       17        rainfall_1    0.6271784     0.6921585
18       18        rainfall_5    0.6233277     0.6914719
19       19        rainfall_8    0.6190883     0.6968408
20       20       rainfall_13    0.6146974     0.6939723
21       21        rainfall_7    0.6101416     0.6906500
22       22       rainfall_19    0.6051635     0.6909402
23       23        rainfall_4    0.6000434     0.6907710
24       24         mileage_2    0.5947881     0.6907984


```

		
c) Compare the models according to the in-sample ```R-bar-squared``` 
		under the column ```R2_in_sample```. 
		Which model is best under this criterion? 
		The variables in the model are listed in the column ```best_new_variable```
		up to the row of the chosen model. 

```

Type your response here.


```
		
d) Compare the models according to the out-of-sample ```R-bar-squared``` 
		under the column ```R2_out_sample```. 
		Which model is best under this criterion? 
		The variables in the model are listed in the column ```best_new_variable```
		up to the row of the chosen model. 

```

Type your response here.


```
		
e) Compare the differences between the two models.
		Do any variables appear in one model and not the other?
		Which model do you recommend on the basis of this data? 
		Is your recommended model the same as the true model? 



```

Type your response here.


```

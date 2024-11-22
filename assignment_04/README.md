# Assignment 4

Complete the exercise described in the pdf above and enter your answers in 
the spaces below.

## Running the Script as Given

Run the entire script and observe the output from the simulation.
In particular, observe the statistics printed at the bottom.



a. Copy and paste the means and standard deviations from the output after the commands
```sapply(reg_results[, full_list_of_variables], mean)``` 
and ```sapply(reg_results[, full_list_of_variables], sd)```. 


```

 sapply(reg_results[, full_list_of_variables], mean)
    intercept       mileage      accident        damage 
 4.998649e+04 -2.000312e-01 -5.009490e+03 -2.002515e+04 
> 
> # Calculate the standard deviation of the estimates.
> print('Standard Deviations of the coefficients are:')
[1] "Standard Deviations of the coefficients are:"
> sapply(reg_results[, full_list_of_variables], sd)
   intercept      mileage     accident       damage 
1.916253e+03 3.800438e-02 8.686180e+02 1.984927e+03 
> 


```

b. For each parameter, calculate the distance between the mean estimate and the true value, in terms of the number of standard deviations of that variable. 
The true values of the coefficients are listed in lines 74 to 78 in the script ```OLS_on_repeat_A4.R```.


```
beta_0          <-   (50000-49986)/1.916253e+03 = 0.007305925
beta_mileage    <- -  (-0.20--.20003)/3.800438e-02 = 0.0007893827 
beta_accident   <- -  (5000--5009)/8.686180e+02   = 11.5229
Beta_Damage     <- -  (20000--20025)/1.984927e+03 = 20.16447

```


c. Now compare the average values of each of the estimated coefficients with their true values.
Are they biased or unbiased?
Keep in mind that with an unbiased estimator 
a difference of less than $2$ standard deviations could often happen by chance.


```

Mileage and accident are the two biased values > than 2
Intercept and Damage are biased < than 2


```



## Running the Script after Modification


d. Copy and paste the means and standard deviations from the output 
after the commands 
```sapply(reg_results[, full_list_of_variables], mean)```

and ```sapply(reg_results[, full_list_of_variables], sd)```.


```

> print('Average value of the coefficients are:')
[1] "Average value of the coefficients are:"
> sapply(reg_results[, full_list_of_variables], mean)
    intercept     mileage_1      accident        damage 
 4.611166e+04 -1.220284e-01 -4.639186e+03 -2.081211e+04 
> 
> # Calculate the standard deviation of the estimates.
> print('Standard Deviations of the coefficients are:')
[1] "Standard Deviations of the coefficients are:"
> sapply(reg_results[, full_list_of_variables], sd)
   intercept    mileage_1     accident       damage 
1.575104e+03 2.967397e-02 8.220657e+02 2.414760e+03 


```


e. For each parameter, calculate the distance between the mean estimate and the true value, in terms of the number of standard deviations of that variable. 


```
> beta_0          <-   (50000-46112)/1.575104e+03=2.468408
> beta_mileage    <- -  (-0.20--.12203)/2.967397e-02= -2.627555  
> beta_accident   <- -  (5000--4639)/8.220657e+02 = 11.72534
> beta_damage     <- - (20000--20812)/2.414760e+03 = 16.90106

```


f. Now compare the average values of each of the estimates 
with their true values when the true 
```mileage``` is unobserved 
but inaccurate ```mileage_1``` is observed instead.
Are they biased or unbiased?
Again, keep in mind that with an unbiased estimator 
a difference of less than $2$ standard deviations could often happen by chance. 


```
> beta_0          <-   (50000-46112)/1.575104e+03=2.468408
> beta_mileage    <- -  (-0.20--.12203)/2.967397e-02= -2.627555  
> beta_accident   <- -  (5000--4639)/8.220657e+02 = 11.72534
> beta_damage     <- - (20000--20812)/2.414760e+03 = 16.90106

All variables are biased due to being >| 2|


```


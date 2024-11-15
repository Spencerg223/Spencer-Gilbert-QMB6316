# Assignment 2

Complete the exercise described in the pdf above and enter your answers in 
the spaces below.

## Running the Script as Given

Run the entire script and compare 
the output from ```summary(lm_full_model)```, 
which includes all variables, 
with that from ```summary(lm_no_damage)```, 
which omits the damage indicator. 
If there are no cars with damage in your simulation, 
run the script again to take another draw.


a. Copy and paste the regression model estimates after the commands
```summary(lm_full_model)``` and ```summary(lm_no_damage)```. 

```
> summary(lm_full_model)

Call:
lm(formula = car_price ~ mileage + accident + damage, data = car_data)

Residuals:
     Min       1Q   Median       3Q      Max 
-11748.7  -2903.0   -176.3   2572.4  12648.7 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  5.095e+04  2.260e+03  22.544  < 2e-16 ***
mileage     -2.160e-01  4.406e-02  -4.902 3.85e-06 ***
accident    -4.630e+03  9.638e+02  -4.804 5.74e-06 ***
damage      -2.042e+04  1.741e+03 -11.734  < 2e-16 ***

> summary(lm_no_damages)

Call:
lm(formula = car_price ~ mileage + accident, data = car_data)

Residuals:
     Min       1Q   Median       3Q      Max 
-24578.3  -2503.5    472.7   4350.4  15489.0 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  5.153e+04  3.507e+03  14.693  < 2e-16 ***
mileage     -2.277e-01  6.836e-02  -3.330  0.00123 ** 
accident    -8.709e+03  1.395e+03  -6.242 1.14e-08 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 


```


b. Compare the estimated coefficient for ```ACCIDENT``` 
with and without the damage variable. 
How does this relate to the coefficient for ```DAMAGE```?

```
The estimated coefficient for accident without damages(-8.7) is larger that the coefficient for accidents including damage (-4.63) 

```


c. Compare the values of 
```Multiple R-squared``` and ```Adjusted R-squared``` for the two models. 
Which model do you recommend (pretending that you don't know the true model)? 

```
I would suggest the Model inclusive of damages Due to a higher R squared being a more precisee gauge of accuracy
```




## Running the Script after Modification


d. Copy and paste the new regression model estimates after the commands
```summary(lm_full_model)``` and ```summary(lm_no_damage)```. 

```
> summary(lm_full_model)

Call:
lm(formula = car_price ~ mileage + accident + damage, data = car_data)

Residuals:
    Min      1Q  Median      3Q     Max 
-9975.8 -2852.6   138.6  2984.7 11962.1 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) 52318.9751  2404.3050  21.761  < 2e-16 ***
mileage        -0.2530     0.0492  -5.142 1.43e-06 ***
accident    -5380.9746   900.0428  -5.979 3.84e-08 ***
damage       1805.2839  2557.6011   0.706    0.482    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 4260 on 96 degrees of freedom
Multiple R-squared:  0.4324,	Adjusted R-squared:  0.4147 
F-statistic: 24.38 on 3 and 96 DF,  p-value: 8.179e-12


> summary(lm_no_damages)

Call:
lm(formula = car_price ~ mileage + accident, data = car_data)

Residuals:
    Min      1Q  Median      3Q     Max 
-9975.3 -2851.8   182.6  2916.9 11959.9 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  5.233e+04  2.398e+03  21.825  < 2e-16 ***
mileage     -2.533e-01  4.907e-02  -5.162  1.3e-06 ***
accident    -5.245e+03  8.768e+02  -5.982  3.7e-08 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 4249 on 97 degrees of freedom
Multiple R-squared:  0.4295,	Adjusted R-squared:  0.4177 
F-statistic: 36.51 on 2 and 97 DF,  p-value: 1.509e-12
```


e. For this new set of regressions, compare the estimated coefficient 
for ```ACCIDENT``` with and without the damage variable. 
How does this relate to the new coefficient for ```DAMAGE```?

```
The accident coefficient when incorporating damages is almost twice as large in comparison to the coefficient without.
```


f. Compare the values of 
```Multiple R-squared``` and ```Adjusted R-squared``` for the two models. 
Now which model do you recommend (pretending that you don't know the true model)? 

```
THe data set not incorporating Damages has a higher R squared, thus deducing the idea that the No Damages data is a more accurate representation
```


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
Type your response here.
```


c. Compare the values of 
```Multiple R-squared``` and ```Adjusted R-squared``` for the two models. 
Which model do you recommend (pretending that you don't know the true model)? 

```
Type your response here.
```




## Running the Script after Modification


d. Copy and paste the new regression model estimates after the commands
```summary(lm_full_model)``` and ```summary(lm_no_damage)```. 

```
Copy your results here.
```


e. For this new set of regressions, compare the estimated coefficient 
for ```ACCIDENT``` with and without the damage variable. 
How does this relate to the new coefficient for ```DAMAGE```?

```
Type your response here.
```


f. Compare the values of 
```Multiple R-squared``` and ```Adjusted R-squared``` for the two models. 
Now which model do you recommend (pretending that you don't know the true model)? 

```
Type your response here.
```


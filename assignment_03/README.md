# Assignment 3

Following the instructions in the document ```QMB6316_assignment_03.pdf``` above, 
enter your responses in the code blocks shown below.


In this exercise, we will follow an approach different than that taken in class. 
We will first estimate a model with our choices of functional form, then consider exclusions of insignificant variables from the full model. 
Note that this approach allows for inclusion of possibly irrelevant variables and avoids excluding any relevant variables. 


At each stage, use the best model that you have found so far, 
incorporating the findings from the answer to the previous question.




a. Estimate a regression model that uses all available variables, 
except for the indicator for an enclosed cab.
	Make sure to choose a reasonable transformation of the dependent variable, 
	such as the logarithmic transformation, if necessary.
	
```
Call:
lm(formula = log(saleprice) ~ horsepower + age + enghours + diesel + 
    fwd + manual + johndeere + spring + summer + winter, data = tractor_sales_specs)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.40551 -0.32922  0.03705  0.36518  1.08651 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  8.770e+00  1.353e-01  64.825  < 2e-16 ***
horsepower   6.536e-03  4.186e-04  15.615  < 2e-16 ***
age         -2.754e-02  4.460e-03  -6.175 2.47e-09 ***
enghours    -2.117e-05  1.184e-05  -1.788   0.0750 .  
diesel       4.992e-01  1.196e-01   4.173 4.08e-05 ***
fwd          3.567e-01  7.266e-02   4.909 1.60e-06 ***
manual      -1.217e-01  7.744e-02  -1.571   0.1173    
johndeere    1.725e-01  8.920e-02   1.934   0.0541 .  
spring      -3.210e-02  8.130e-02  -0.395   0.6933    
summer      -1.188e-01  7.947e-02  -1.494   0.1363    
winter       4.009e-02  8.924e-02   0.449   0.6536    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.4983 on 265 degrees of freedom
Multiple R-squared:  0.6971,	Adjusted R-squared:  0.6857 
F-statistic: 60.99 on 10 and 265 DF,  p-value: < 2.2e-16


```

Does this seem to be a reasonable model, as opposed to using average tractor prices? 
	That is, is the R-squared or the R-bar-squared reasonably high?

```
This is a reasonable model! the Rsquared is much higher .68 instead of .24



```


b. Which variables seem to help explain used tractor prices? 
	Which have positive and negative relationships with tractor prices?
	Did you find any variables that do not have statistically significant coefficients under this specification?

```
Diesel,FWD, John Deere are all variables that positively impact the tractor prices. Factors like AGE MANUAL AND ENGHOURS all negatively impact the tractor price.

```



c. Before making any reductions to your model, revise the model specification first
	by considering nonlinear specifications.
	A used tractor dealer tells you that overpowered used tractors are hard to sell, since they consume more fuel. 
      Tractor prices often increase with horsepower, up to a point, but beyond that they decrease. 
      To incorporate this advice, you create and include a variable for squared horsepower and include that in a new regression model. 
      

```
> hist(tractor_full[, 'saleprice'])
> tractor_full[, 'log_saleprice'] <- log(tractor_full[, 'saleprice'])
> hist(tractor_full[, 'log_saleprice'])
> tractor_full[, 'squared_horsepower'] <- tractor_full[, 'horsepower']^2
> lm_model_1 <- lm(data = tractor_full,
+                  formula = saleprice ~ horsepower + age + enghours +
+                    diesel + fwd + manual + johndeere +
+                    cab +
+                    spring + summer + winter)
> summary(lm_model_1)

Call:
lm(formula = saleprice ~ horsepower + age + enghours + diesel + 
    fwd + manual + johndeere + cab + spring + summer + winter, 
    data = tractor_full)

Residuals:
   Min     1Q Median     3Q    Max 
-48532  -6089   -645   6263  92806 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) 13015.7894  4468.2593   2.913  0.00389 ** 
horsepower    226.5840    15.1670  14.939  < 2e-16 ***
age          -699.7279   146.8462  -4.765 3.12e-06 ***
enghours       -1.9344     0.3934  -4.917 1.55e-06 ***
diesel        444.3901  4000.6502   0.111  0.91164    
fwd          1491.0701  2413.9374   0.618  0.53731    
manual      -4214.1008  2550.8076  -1.652  0.09971 .  
johndeere   13709.8757  2972.6862   4.612 6.22e-06 ***
cab          8072.0643  2597.6376   3.107  0.00209 ** 
spring      -1815.2076  2672.9042  -0.679  0.49766    
summer      -4923.8739  2620.8553  -1.879  0.06138 .  
winter      -1579.6222  2933.8039  -0.538  0.59074    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 16380 on 264 degrees of freedom
Multiple R-squared:  0.6599,	Adjusted R-squared:  0.6457 
F-statistic: 46.57 on 11 and 264 DF,  p-value: < 2.2e-16



```


  c.i) Hypothesize the signs for the coefficients on horsepower 
	under this scenario. 
		What should be the sign of the coefficient for horsepower? 
		What sign do you expect for squared horsepower?
      
```
Under this scenario, the coefficients on horsepower will be positive. Due to being squared the coefficients will be a positive number overall. As directed, horsepower can have negative effects on the price due to gas consumption once getting to a certain point.


```

  c.ii) Perform 1-sided t-tests of the hypotheses for each of the horsepower coefficients. 
That is, are the t-statistics higher than 1.96, with the same sign as you hypothesized?

```

Enter your response here.
Use the coefficients from the regression output for this model to draw your conclusions.



```

  c.iii) Compare the model with or without the quadratic functional form for horsepower.
            Which model do you recommend? 
		Be sure to cite evidence to support your choice. 
		Specifically, check the four specification criteria: 
		statistical significant $t$-statistics, 
		an increase in R-squared, 
		a good theoretical justification, and 
		no large change in the other coefficients.

```
Enter your response here.



```


d. Again, use the best model that results from the answer to the previous question to address further questions.
	Use the model you have so far to test that the time of year has no effect on the sale of tractors.
	That is, test whether the t-statistics on the seasonal indicators are statistical significant. 
	Is there evidence that tractor prices follow a seasonal pattern? 

```
Enter your response here.
Use the coefficients from the regression output for this model to draw your conclusions.



```
	
	
e. Finally, consider another modification to your model. 
	Some say that John Deere tractors hold their value longer than other tractors. 
      This raises the question of whether an additional hour of use affects the value of a John Deere tractor 
	differently than for tractors of other brands. 
	You can test this by including an interaction with ```age:johndeere``` in the regression.
	
```
Enter your regression results here.



```

Test the hypothesis, at the 5 percent level of significance, that the slope for engine hours differs by brand. 

Does an additional hour of use affect the price of a John Deere tractor
differently than tractors of other brands?
	
```
Enter your response here.



```
	
	
	

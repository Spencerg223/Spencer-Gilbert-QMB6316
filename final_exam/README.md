# Final Examination

## Due Friday, December 6, 2024 at 11:59 PM in your GitHub repository.

Complete the exercise described in the pdf above and enter your answers in 
the spaces below.

*Please see the revised version of the pdf copy of the question paper, uploaded Nov. 23, 2024.*

## Part A: Data Handling and Preliminary Regression Modelling

### Question 1

a) Read in the ```airplane_sales.csv``` dataset and store it in a data frame called ```airplane_sales``` in your workspace. 


```

airplane_sales <- read.csv("airplane_sales.csv")

```

b) Calculate and copy the printed output from a ```summary``` of the data. 
Use this to get familiar with the contents of the dataset. 


```

 print(summary(airplane_sales))
   X0Sale_ID          age            price       
 Min.   :101.0   Min.   :13.00   Min.   :  9000  
 1st Qu.:149.5   1st Qu.:19.00   1st Qu.: 19250  
 Median :198.0   Median :22.00   Median : 33500  
 Mean   :198.0   Mean   :24.61   Mean   : 50237  
 3rd Qu.:246.5   3rd Qu.:30.00   3rd Qu.: 73500  
 Max.   :295.0   Max.   :44.00   Max.   :254000 



```

c) Estimate a regression model to predict ```price``` as a function of ```age```. 
Copy the printed estimation output from the ```summary``` command. 


```

 regression_model <- lm(price ~ age, data = airplane_sales) 
> regression_summary <- summary(regression_model)
> print(regression_summary)

Call:
lm(formula = price ~ age, data = airplane_sales)

Residuals:
   Min     1Q Median     3Q    Max 
-58685 -19747  -6039  15903 170846 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 144322.9     8426.0   17.13   <2e-16 ***
age          -3823.0      329.5  -11.60   <2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 31910 on 193 degrees of freedom
Multiple R-squared:  0.4108,	Adjusted R-squared:  0.4078 
F-statistic: 134.6 on 1 and 193 DF,  p-value: < 2.2e-16



```


### Question 2

a) Read in the ```airplane_specs.csv``` dataset and store it 
in a data frame called ```airplane_specs``` in your workspace. 


```

airplane_specs <- read.csv("airplane_specs.csv")
> print(airplane_specs)
    X0Sale_ID pass wtop fixgear tdrag
1         105    2    1       0     0
2         106    2    1       0     0
3         107    2    1       0     0
4         108    2    1       0     0
5         109    2    1       0     0
6         110    2    1       0     0
7         135    4    1       0     0
8         136    4    1       0     0
9         137    4    1       0     0
10        138    4    1       0     0
11        139    4    1       0     0
12        140    4    1       0     0
13        141    4    1       0     0
14        142    4    1       0     0
15        143    4    1       0     0
16        144    4    1       0     0
17        145    4    1       0     0
18        146    4    1       0     0
19        147    4    1       0     0
20        148    4    1       0     0
21        149    4    1       0     0
22        150    4    1       0     0
23        151    4    1       0     0
24        152    4    1       0     0
25        153    4    1       0     0
26        154    4    1       0     0
27        155    4    1       0     0
28        156    4    1       0     0
29        157    4    1       0     0
30        158    2    1       0     0
31        159    2    1       0     0
32        160    2    1       0     0
33        161    2    1       0     0
34        162    2    1       0     0
35        163    2    1       0     0
36        164    2    1       0     0
37        165    2    1       0     0
38        166    2    1       0     0
39        167    2    1       0     0
40        168    2    1       0     0
41        182    4    1       0     0
42        183    4    1       0     0
43        184    4    1       0     0
44        185    4    1       0     0
45        186    4    1       0     0
46        187    4    1       0     0
47        188    4    1       0     0
48        189    4    1       0     0
49        190    4    1       0     0
50        191    4    1       0     0
51        192    4    1       0     0
52        193    4    1       0     0
53        194    4    1       0     0
54        195    4    1       0     0
55        196    4    1       0     0
56        209    4    1       1     0
57        210    4    1       1     0
58        211    4    1       1     0
59        212    4    1       1     0
60        213    4    1       1     0
61        214    4    1       1     0
62        215    4    1       1     0
63        216    4    1       1     0
64        257    6    1       1     0
65        258    6    1       1     0
66        259    6    1       1     0
67        260    6    1       1     0
68        261    6    1       1     0
69        262    6    1       1     0
70        263    6    1       1     0
71        264    6    1       1     0
72        265    6    1       1     0
73        266    6    1       1     0
74        267    6    1       1     0
75        275    6    1       1     0
76        276    6    1       1     0
77        277    6    1       1     0
78        278    6    1       1     0
79        279    6    1       1     0
80        197    6    1       0     1
81        198    6    1       0     1
82        199    6    1       0     1
83        200    6    1       0     1
84        201    6    1       0     1
85        202    6    1       0     1
86        203    6    1       0     1
87        204    6    1       0     1
88        205    6    1       0     1
89        206    6    1       0     1
90        207    6    1       0     1
91        101    2    0       0     0
92        102    2    0       0     0
93        103    2    0       0     0
94        104    2    0       0     0
95        111    2    0       0     0
96        112    2    0       0     0
97        113    2    0       0     0
98        114    2    0       0     0
99        115    2    0       0     0
100       116    2    0       0     0
101       117    2    0       0     0
102       118    2    0       0     0
103       119    2    0       0     0
104       120    2    0       0     0
105       121    4    0       0     0
106       122    4    0       0     0
107       123    4    0       0     0
108       124    4    0       0     0
109       125    4    0       0     0
110       126    4    0       0     0
111       127    4    0       0     0
112       128    4    0       0     0
113       129    4    0       0     0
114       130    4    0       0     0
115       131    4    0       0     0
116       132    4    0       0     0
117       133    4    0       0     0
118       134    4    0       0     0
119       169    4    0       0     0
120       170    4    0       0     0
121       171    4    0       0     0
122       172    4    0       0     0
123       173    4    0       0     0
124       174    4    0       0     0
125       175    4    0       0     0
126       176    4    0       0     0
127       177    4    0       0     0
128       178    4    0       0     0
129       179    4    0       0     0
130       180    4    0       0     0
131       181    4    0       0     0
132       208    6    0       1     0
133       217    4    0       1     0
134       218    4    0       1     0
135       219    4    0       1     0
136       220    4    0       1     0
137       221    4    0       1     0
138       222    4    0       1     0
139       223    4    0       1     0
140       224    4    0       1     0
141       225    4    0       1     0
142       226    4    0       1     0
143       227    4    0       1     0
144       228    4    0       1     0
145       229    4    0       1     0
146       230    4    0       1     0
147       231    4    0       1     0
148       232    4    0       1     0
149       233    4    0       1     0
150       234    4    0       1     0
151       235    4    0       1     0
152       236    4    0       1     0
153       237    4    0       1     0
154       238    4    0       1     0
155       239    4    0       1     0
156       240    4    0       1     0
157       241    4    0       1     0
158       242    4    0       1     0
159       243    4    0       1     0
160       244    4    0       1     0
161       245    4    0       1     0
162       246    4    0       1     0
163       247    6    0       1     0
164       248    6    0       1     0
165       249    6    0       1     0
166       250    6    0       1     0
167       251    6    0       1     0
168       252    6    0       1     0
169       253    6    0       1     0
170       254    6    0       1     0
171       255    6    0       1     0
172       256    6    0       1     0
173       268    6    0       1     0
174       269    6    0       1     0
175       270    6    0       1     0
176       271    6    0       1     0
177       272    6    0       1     0
178       273    4    0       1     0
179       274    4    0       1     0
180       280    6    0       1     0
181       281    6    0       1     0
182       282    6    0       1     0
183       283    6    0       1     0
184       284    6    0       1     0
185       285    6    0       1     0
186       286    6    0       1     0
187       287    6    0       1     0
188       288    6    0       1     0
189       289    6    0       1     0
190       290    6    0       1     0
191       291    6    0       1     0
192       292    6    0       1     0
193       293    6    0       1     0
194       294    6    0       1     0
195       295    6    0       1     0

```

b)  Form a dataset ```airplane_sales_specs.csv``` 
by ```merge```ing the data frames 
```airplane_sales.csv``` and ```airplane_specs.csv```. 
Store the new dataset in a data frame called 
```airplane_sales_specs``` in your workspace. 


```

> airplane_sales_specs <- merge (airplane_sales,airplane_specs, by = "X0Sale_ID")
> 
> summary(airplane_sales_specs)

```


c) Calculate and copy the printed output from a ```summary``` of the data. 
Use this to get familiar with the contents of the dataset. 


```

> summary(airplane_sales_specs)
   X0Sale_ID          age            price             pass            wtop       
 Min.   :101.0   Min.   :13.00   Min.   :  9000   Min.   :2.000   Min.   :0.0000  
 1st Qu.:149.5   1st Qu.:19.00   1st Qu.: 19250   1st Qu.:4.000   1st Qu.:0.0000  
 Median :198.0   Median :22.00   Median : 33500   Median :4.000   Median :0.0000  
 Mean   :198.0   Mean   :24.61   Mean   : 50237   Mean   :4.287   Mean   :0.4615  
 3rd Qu.:246.5   3rd Qu.:30.00   3rd Qu.: 73500   3rd Qu.:6.000   3rd Qu.:1.0000  
 Max.   :295.0   Max.   :44.00   Max.   :254000   Max.   :6.000   Max.   :1.0000  
    fixgear           tdrag        
 Min.   :0.0000   Min.   :0.00000  
 1st Qu.:0.0000   1st Qu.:0.00000  
 Median :0.0000   Median :0.00000  
 Mean   :0.4513   Mean   :0.05641  
 3rd Qu.:1.0000   3rd Qu.:0.00000  
 Max.   :1.0000   Max.   :1.00000  


```


d) Estimate a regression model to predict ```price``` as a function of 
```age```, ```pass```, ```wtop```, ```fixgear```, 
and ```tdrag```. 
Copy the printed estimation output from the ```summary``` command. 


```

> model <- lm(data = airplane_sales_specs, formula = price ~ age + pass + wtop + fixgear + tdrag)
> summary(model)

Call:
lm(formula = price ~ age + pass + wtop + fixgear + tdrag, data = airplane_sales_specs)

Residuals:
   Min     1Q Median     3Q    Max 
-34133 -13201  -2957   8476 145275 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  42071.7     9364.6   4.493 1.22e-05 ***
age          -2544.7      256.1  -9.935  < 2e-16 ***
pass         15635.9     1690.8   9.248  < 2e-16 ***
wtop         -1809.3     3459.7  -0.523  0.60161    
fixgear      13552.4     4794.3   2.827  0.00521 ** 
tdrag       -27030.8     8402.5  -3.217  0.00152 ** 
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 22040 on 189 degrees of freedom
Multiple R-squared:  0.7249,	Adjusted R-squared:  0.7176 
F-statistic:  99.6 on 5 and 189 DF,  p-value: < 2.2e-16


```




### Question 3

a) Read in the ```airplane_perf.csv``` dataset and store it 
in a data frame called ```airplane_perf``` in your workspace. 


```

 View(airplane_sales_specs)
> airplane_perf <- read.csv("airplane_perf.csv")

```

b) Form a dataset ```airplane_full.csv``` 
by ```merge```ing all three datasets. 
Store the new dataset 
in a data frame called ```airplane_full``` in your workspace. 


```

> airplane_full <- merge(airplane_sales_specs, airplane_perf)

```

c) Calculate and copy the printed output from a ```summary``` 
of the new variables. 
Use this to get familiar with the contents of the dataset. 


```

 summary(airplane_full)
   X0Sale_ID          age            price             pass            wtop       
 Min.   :101.0   Min.   :13.00   Min.   :  9000   Min.   :2.000   Min.   :0.0000  
 1st Qu.:149.5   1st Qu.:19.00   1st Qu.: 19250   1st Qu.:4.000   1st Qu.:0.0000  
 Median :198.0   Median :22.00   Median : 33500   Median :4.000   Median :0.0000  
 Mean   :198.0   Mean   :24.61   Mean   : 50237   Mean   :4.287   Mean   :0.4615  
 3rd Qu.:246.5   3rd Qu.:30.00   3rd Qu.: 73500   3rd Qu.:6.000   3rd Qu.:1.0000  
 Max.   :295.0   Max.   :44.00   Max.   :254000   Max.   :6.000   Max.   :1.0000  
    fixgear           tdrag             horse            fuel           ceiling     
 Min.   :0.0000   Min.   :0.00000   Min.   :108.0   Min.   : 29.00   Min.   : 8500  
 1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:180.0   1st Qu.: 51.00   1st Qu.: 9700  
 Median :0.0000   Median :0.00000   Median :210.0   Median : 68.00   Median :13000  
 Mean   :0.4513   Mean   :0.05641   Mean   :219.2   Mean   : 67.79   Mean   :14007  
 3rd Qu.:1.0000   3rd Qu.:0.00000   3rd Qu.:285.0   3rd Qu.: 84.00   3rd Qu.:16800  
 Max.   :1.0000   Max.   :1.00000   Max.   :310.0   Max.   :130.00   Max.   :28000  
     cruise     
 Min.   : 97.0  
 1st Qu.:119.0  
 Median :144.0  
 Mean   :144.7  
 3rd Qu.:170.0  
 Max.   :221.0  


```


d) Estimate a regression model to predict ```price``` as a function of 
```age```, ```pass```, ```wtop```, ```fixgear```, 
and ```tdrag```, 
as well as ```horse```, ```fuel```, ```ceiling```, and ```cruise```.
Copy the printed estimation output from the ```summary``` command. 


```

 model <- lm(data = airplane_full, formula = price ~ age + pass + wtop + fixgear + tdrag + horse + fuel + ceiling + cruise)
> summary(model)

Call:
lm(formula = price ~ age + pass + wtop + fixgear + tdrag + horse + 
    fuel + ceiling + cruise, data = airplane_full)

Residuals:
   Min     1Q Median     3Q    Max 
-40971  -9653  -1189   7035 127745 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) -4.189e+04  1.440e+04  -2.910  0.00406 ** 
age         -2.354e+03  2.338e+02 -10.070  < 2e-16 ***
pass         5.586e+03  2.218e+03   2.518  0.01264 *  
wtop        -9.928e+03  3.118e+03  -3.184  0.00170 ** 
fixgear     -3.096e+04  6.802e+03  -4.552 9.62e-06 ***
tdrag       -4.925e+04  7.909e+03  -6.226 3.13e-09 ***
horse        2.241e+02  6.720e+01   3.335  0.00103 ** 
fuel        -3.038e+01  1.264e+02  -0.240  0.81033    
ceiling      1.525e+00  5.261e-01   2.899  0.00420 ** 
cruise       5.460e+02  1.117e+02   4.886 2.22e-06 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 18840 on 185 degrees of freedom
Multiple R-squared:  0.8032,	Adjusted R-squared:  0.7936 
F-statistic:  83.9 on 9 and 185 DF,  p-value: < 2.2e-16


```






## Part B: Advanced Regression Modelling


### Question 4

a) Create new variables 
	```log_price```, ```log_age```, ```log_horse```, 
	```log_fuel```, ```log_ceiling```, and ```log_cruise```
	from the variables 
	```price```, ```age```, ```horse```, 
	```fuel```, ```ceiling```, and ```cruise```, 
	using the logarithm function ```log()``` in ```R``` 
	to create these new variables. 


```

> airplane_full[ 'log_price'] <-log(airplane_full[ 'price'])
> airplane_full[ 'log_age'] <-log(airplane_full[ 'age'])
> airplane_full[ 'log_horse'] <-log(airplane_full[ 'horse'])
> airplane_full[ 'log_fuel'] <-log(airplane_full[ 'fuel'])
> airplane_full[ 'log_ceiling'] <-log(airplane_full[ 'ceiling'])
> airplane_full[ 'log_cruise'] <-log(airplane_full[ 'cruise'])

```

b) Calculate and copy the printed output from a ```summary``` 
of the new variables. 
Use this to get familiar with the contents of the dataset. 


```

> summary(airplane_full)
   X0Sale_ID          age            price             pass            wtop       
 Min.   :101.0   Min.   :13.00   Min.   :  9000   Min.   :2.000   Min.   :0.0000  
 1st Qu.:149.5   1st Qu.:19.00   1st Qu.: 19250   1st Qu.:4.000   1st Qu.:0.0000  
 Median :198.0   Median :22.00   Median : 33500   Median :4.000   Median :0.0000  
 Mean   :198.0   Mean   :24.61   Mean   : 50237   Mean   :4.287   Mean   :0.4615  
 3rd Qu.:246.5   3rd Qu.:30.00   3rd Qu.: 73500   3rd Qu.:6.000   3rd Qu.:1.0000  
 Max.   :295.0   Max.   :44.00   Max.   :254000   Max.   :6.000   Max.   :1.0000  
    fixgear           tdrag             horse            fuel           ceiling     
 Min.   :0.0000   Min.   :0.00000   Min.   :108.0   Min.   : 29.00   Min.   : 8500  
 1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:180.0   1st Qu.: 51.00   1st Qu.: 9700  
 Median :0.0000   Median :0.00000   Median :210.0   Median : 68.00   Median :13000  
 Mean   :0.4513   Mean   :0.05641   Mean   :219.2   Mean   : 67.79   Mean   :14007  
 3rd Qu.:1.0000   3rd Qu.:0.00000   3rd Qu.:285.0   3rd Qu.: 84.00   3rd Qu.:16800  
 Max.   :1.0000   Max.   :1.00000   Max.   :310.0   Max.   :130.00   Max.   :28000  
     cruise        log_price         log_age        log_horse        log_fuel    
 Min.   : 97.0   Min.   : 9.105   Min.   :2.565   Min.   :4.682   Min.   :3.367  
 1st Qu.:119.0   1st Qu.: 9.865   1st Qu.:2.944   1st Qu.:5.193   1st Qu.:3.932  
 Median :144.0   Median :10.419   Median :3.091   Median :5.347   Median :4.220  
 Mean   :144.7   Mean   :10.519   Mean   :3.166   Mean   :5.349   Mean   :4.169  
 3rd Qu.:170.0   3rd Qu.:11.205   3rd Qu.:3.401   3rd Qu.:5.652   3rd Qu.:4.431  
 Max.   :221.0   Max.   :12.445   Max.   :3.784   Max.   :5.737   Max.   :4.868  
  log_ceiling       log_cruise   
 Min.   : 9.048   Min.   :4.575  
 1st Qu.: 9.180   1st Qu.:4.779  
 Median : 9.473   Median :4.970  
 Mean   : 9.499   Mean   :4.953  
 3rd Qu.: 9.729   3rd Qu.:5.136  
 Max.   :10.240   Max.   :5.398  


```


c) Estimate a regression model to predict ```log_price``` as a function of 
	```log_age```, ```pass```, ```wtop```, ```fixgear```, 
	and ```tdrag```, 
	as well as 
	```log_horse```, ```log_fuel```, ```log_ceiling```, 
	and ```log_cruise```. 
	Copy the printed estimation output from the ```summary``` command. 


```

> summary(model)

Call:
lm(formula = log_price ~ log_price + log_age + log_horse + log_fuel + 
    log_ceiling + log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.52718 -0.14189  0.01641  0.10615  0.64710 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  5.69547    0.61223   9.303  < 2e-16 ***
log_age     -1.59205    0.06678 -23.839  < 2e-16 ***
log_horse    1.07844    0.11251   9.585  < 2e-16 ***
log_fuel     0.16538    0.09113   1.815   0.0711 .  
log_ceiling -0.18728    0.08608  -2.176   0.0308 *  
log_cruise   1.04677    0.15725   6.657 2.95e-10 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2054 on 189 degrees of freedom
Multiple R-squared:  0.9326,	Adjusted R-squared:  0.9309 
F-statistic: 523.4 on 5 and 189 DF,  p-value: < 2.2e-16


```


d) If you notice that any coefficients are statistically insignificant, 
	estimate the model by removing them one at a time. 
	For each variable removed, 
	determine whether the variable should be removed 
	by considering the four specification criteria: 
		statistically significant $t$-statistics, 
		an increase in ```R-bar-squared```, 
		a good theoretical justification, and 
		no large change in the other coefficients.


```

Enter a description of your sequence of adjustments
to the regression model here.
Be sure to address the four specification criteria
described above.

The coefficients "Log_Fuel and Log_Cruise" should be removed on the basis of being insignificant figures. 
with t T-Value less than 2 according to the regression the coefficient should be removed from the regression.
By removing the two coefficients individually, both R and Rsquared decreased slightly.These changes are justified due to
improving the regression as a whole but also fuel efficiency and cruising ability should not be heavily weighted in 
airplane sales, in comparison to the other criteria.

```

Next regression model:

```

> summary(model)

Call:
lm(formula = log_price ~ log_price + log_age + log_horse + log_ceiling + 
    log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.56522 -0.13234  0.00568  0.10912  0.68936 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  5.59326    0.61331   9.120  < 2e-16 ***
log_age     -1.60870    0.06655 -24.173  < 2e-16 ***
log_horse    1.20713    0.08788  13.735  < 2e-16 ***
log_ceiling -0.19450    0.08650  -2.249   0.0257 *  
log_cruise   1.09213    0.15619   6.993 4.47e-11 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2067 on 190 degrees of freedom
Multiple R-squared:  0.9315,	Adjusted R-squared:   0.93 
F-statistic: 645.6 on 4 and 190 DF,  p-value: < 2.2e-16



```

Next regression model, if necessary:

```

> summary(model)

Call:
lm(formula = log_price ~ log_price + log_age + log_horse + log_fuel + 
    log_ceiling, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.55953 -0.13165 -0.02852  0.16379  0.58027 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  7.03761    0.64059  10.986  < 2e-16 ***
log_age     -1.79458    0.06588 -27.240  < 2e-16 ***
log_horse    1.30641    0.11876  11.000  < 2e-16 ***
log_fuel     0.26181    0.09970   2.626  0.00934 ** 
log_ceiling  0.11399    0.08114   1.405  0.16167    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2276 on 190 degrees of freedom
Multiple R-squared:  0.9168,	Adjusted R-squared:  0.9151 
F-statistic: 523.8 on 4 and 190 DF,  p-value: < 2.2e-16


```

Next regression model, if necessary:

```

Copy your regression results here.


```

Next regression model, if necessary:

```

Copy your regression results here.


```



e) Print the output from a ```summary``` of the regression results
of your final regression model.


```

> summary(model)

Call:
lm(formula = log_price ~ log_price + log_age + log_horse + log_ceiling, 
    data = airplane_full)

Residuals:
    Min      1Q  Median      3Q     Max 
-0.5520 -0.1343 -0.0170  0.1687  0.5838 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  6.96608    0.64981   10.72   <2e-16 ***
log_age     -1.83588    0.06496  -28.26   <2e-16 ***
log_horse    1.53146    0.08349   18.34   <2e-16 ***
log_ceiling  0.12346    0.08230    1.50    0.135    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2311 on 191 degrees of freedom
Multiple R-squared:  0.9138,	Adjusted R-squared:  0.9125 
F-statistic: 675.2 on 3 and 191 DF,  p-value: < 2.2e-16



```

f) Finally, for each of the variables in the datasets, 
	list those that are positively related to airplane prices,
	negatively related to airplane prices, 
	and statistically unrelated to airplane prices. 


```

Enter your response here.


```




## Part C: Version Control

### Question 5

Push your completed files to the ```final_exam``` folder 
in your private GitHub repository.
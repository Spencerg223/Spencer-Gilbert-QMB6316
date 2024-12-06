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

>  airplane_full <- merge(airplane_sales_specs, airplane_perf, by = "X0Sale_ID")

```

c) Calculate and copy the printed output from a ```summary``` 
of the new variables. 
Use this to get familiar with the contents of the dataset. 


```

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
Call:
lm(formula = log_price ~ log_age + pass + wtop + fixgear + tdrag + 
    log_horse + log_fuel + log_ceiling + log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.50754 -0.11123  0.00186  0.11226  0.53375 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept)  3.786112   1.067378   3.547 0.000494 ***
log_age     -1.527922   0.063521 -24.054  < 2e-16 ***
pass         0.048006   0.021645   2.218 0.027776 *  
wtop        -0.048649   0.031384  -1.550 0.122823    
fixgear     -0.179043   0.075662  -2.366 0.018998 *  
tdrag       -0.459069   0.081906  -5.605 7.47e-08 ***
log_horse    1.021321   0.135777   7.522 2.27e-12 ***
log_fuel     0.167589   0.084245   1.989 0.048141 *  
log_ceiling -0.005037   0.088651  -0.057 0.954748    
log_cruise   1.086126   0.195242   5.563 9.18e-08 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.1896 on 185 degrees of freedom
Multiple R-squared:  0.9438,	Adjusted R-squared:  0.9411 
F-statistic: 345.5 on 9 and 185 DF,  p-value: < 2.2e-16


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

By removing each of The coefficients with a T-score less than .05, it is proven that 
(Log_age, Tdrag, Log_horse and Log Cruise) should be removed on the basis of being insignificant figures. 
while removing these variables adjusted R squared decreased slightly in each iteration of the regression.
The removal of these coefficients are justified due to improving the regression as a whole.

```

Next regression model:

```

Call:
lm(formula = log_price ~ pass + wtop + fixgear + tdrag + log_horse + 
    log_fuel + log_ceiling + log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.83317 -0.26988 -0.01682  0.25043  1.00168 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -3.43813    2.07530  -1.657 0.099268 .  
pass         0.16359    0.04276   3.826 0.000178 ***
wtop        -0.05763    0.06358  -0.906 0.365899    
fixgear     -0.21299    0.15328  -1.390 0.166318    
tdrag       -0.69316    0.16478  -4.207 4.03e-05 ***
log_horse   -0.19324    0.25537  -0.757 0.450184    
log_fuel     0.45631    0.16895   2.701 0.007555 ** 
log_ceiling -0.03642    0.17960  -0.203 0.839529    
log_cruise   2.60365    0.37437   6.955 5.82e-11 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.3841 on 186 degrees of freedom
Multiple R-squared:  0.7682,	Adjusted R-squared:  0.7582 
F-statistic: 77.06 on 8 and 186 DF,  p-value: < 2.2e-16



```

Next regression model, if necessary:

```
 Call:
lm(formula = log_price ~ log_age + pass + wtop + fixgear + log_horse + 
    log_fuel + log_ceiling + log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.54774 -0.14318  0.01873  0.12605  0.63077 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  6.54040    1.02207   6.399 1.24e-09 ***
log_age     -1.57022    0.06803 -23.081  < 2e-16 ***
pass         0.02360    0.02287   1.032   0.3035    
wtop        -0.04551    0.03385  -1.345   0.1804    
fixgear      0.04295    0.06954   0.618   0.5376    
log_horse    1.02013    0.14646   6.965 5.48e-11 ***
log_fuel     0.16550    0.09087   1.821   0.0702 .  
log_ceiling -0.19485    0.08837  -2.205   0.0287 *  
log_cruise   0.91952    0.20815   4.418 1.69e-05 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2045 on 186 degrees of freedom
Multiple R-squared:  0.9343,	Adjusted R-squared:  0.9315 
F-statistic: 330.7 on 8 and 186 DF,  p-value: < 2.2e-16


```

Next regression model, if necessary:

```

Call:
lm(formula = log_price ~ log_age + pass + tdrag + wtop + fixgear + 
    log_fuel + log_ceiling + log_cruise, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.64150 -0.10855  0.00014  0.13650  0.48131 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  4.60627    1.21009   3.807 0.000191 ***
log_age     -1.35023    0.06720 -20.093  < 2e-16 ***
pass         0.14820    0.01944   7.622 1.24e-12 ***
tdrag       -0.45811    0.09334  -4.908 2.01e-06 ***
wtop        -0.01333    0.03536  -0.377 0.706749    
fixgear     -0.18540    0.08622  -2.150 0.032832 *  
log_fuel     0.49515    0.08219   6.025 8.90e-09 ***
log_ceiling  0.03966    0.10080   0.393 0.694431    
log_cruise   1.45916    0.21521   6.780 1.54e-10 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2161 on 186 degrees of freedom
Multiple R-squared:  0.9267,	Adjusted R-squared:  0.9235 
F-statistic: 293.8 on 8 and 186 DF,  p-value: < 2.2e-16


```

Next regression model, if necessary:

```

Call:
lm(formula = log_price ~ log_age + pass + tdrag + wtop + fixgear + 
    log_fuel + log_ceiling + log_horse, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.57922 -0.14200  0.00888  0.15574  0.50178 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  7.21565    0.93887   7.686 8.51e-13 ***
log_age     -1.64210    0.06477 -25.352  < 2e-16 ***
pass         0.04272    0.02330   1.834   0.0683 .  
tdrag       -0.38970    0.08722  -4.468 1.37e-05 ***
wtop        -0.03095    0.03364  -0.920   0.3588    
fixgear      0.07859    0.06447   1.219   0.2244    
log_fuel     0.21867    0.09023   2.423   0.0163 *  
log_ceiling  0.09669    0.09347   1.034   0.3023    
log_horse    1.21317    0.14150   8.574 3.84e-15 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2043 on 186 degrees of freedom
Multiple R-squared:  0.9344,	Adjusted R-squared:  0.9316 
F-statistic: 331.4 on 8 and 186 DF,  p-value: < 2.2e-16



```



e) Print the output from a ```summary``` of the regression results
of your final regression model.


```

Call:
lm(formula = log_price ~ log_age + pass + tdrag + wtop + fixgear + 
    log_fuel + log_cruise + log_horse, data = airplane_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.50764 -0.11136  0.00149  0.11191  0.53199 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  3.75306    0.89258   4.205 4.06e-05 ***
log_age     -1.52798    0.06334 -24.122  < 2e-16 ***
pass         0.04793    0.02155   2.224   0.0273 *  
tdrag       -0.46085    0.07549  -6.105 5.87e-09 ***
wtop        -0.04893    0.03090  -1.584   0.1150    
fixgear     -0.18054    0.07073  -2.553   0.0115 *  
log_fuel     0.16775    0.08397   1.998   0.0472 *  
log_cruise   1.08384    0.19053   5.689 4.90e-08 ***
log_horse    1.02080    0.13511   7.555 1.83e-12 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.1891 on 186 degrees of freedom
Multiple R-squared:  0.9438,	Adjusted R-squared:  0.9414 
F-statistic: 390.8 on 8 and 186 DF,  p-value: < 2.2e-16



```

f) Finally, for each of the variables in the datasets, 
	list those that are positively related to airplane prices,
	negatively related to airplane prices, 
	and statistically unrelated to airplane prices. 


```

Variables (Pass, Wtop, fixgear, log_cruise, log_fuel,tdrag, log_horse)
all negatively effect the overall adjusted Rsquared,thus increase the price
of a plane positively.

Variable (Log_Ceiling) has a significant T-stat but with an insignificant
coefficient the effect is negligable


```




## Part C: Version Control

### Question 5

Push your completed files to the ```final_exam``` folder 
in your private GitHub repository.
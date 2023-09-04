#sas 
# Jednovýběrový test o průměru v proceduře MEANS

Pouze H0:  = 0

```sas
proc means data = priklad t probt;
var cena;
run;
```
---
# Jednovýběrový test o průměru v proceduře UNIVARIATE

```sas
ods select TestsForLocation;
proc univariate data = priklad mu0 = 10000;
var cena;
run;
```
---
# Jednovýběrový test o průměru v proceduře TTEST

```sas
proc ttest data = priklad H0 = 10000;
var cena;
run;
```


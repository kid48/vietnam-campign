# Průzkumová analýza v proceduře MEANS

```sas
proc means data = test n mean stddev cv skewness kurtosis maxdec=2;
var zapocet zkouska;
run;
```
---
# Procedura TTEST
```sas
proc ttest data = test;
paired zapocet * zkouska;
run;
```
---
# Nezavisle
---
# Průzkumová analýza dat pomocí schematického boxplotu (BOXSTYLE = schematic) a pomocí zářezového boxplotu (NOTCHES)

```sas
proc boxplot data = priklad;
plot cena * system / boxstyle = schematic;
plot cena * system / notches;
run;
```
---
# Neparametrická obdoba dvouvýběrového t-testu Dvouvýběrový Wilcoxonův test
```sas
proc npar1way data = priklad wilcoxon;
class system;
var cena;
run;
```
---

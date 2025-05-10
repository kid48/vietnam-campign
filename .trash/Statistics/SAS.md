---
undefined: ""
sticker: emoji//1f4c8
---
```sas
proc means data = priklad n mean median q1 q3 std cv skewness kurtosis maxdec=2; 
run;
```
# Intervalový odhad v proceduře means
```sas
proc means data = priklad mean clm; 
run;
```
# Procedura UNIVARIATE
```sas
proc univariate data = priklad normal plot; 
histogram cena / normal;
qqplot cena / normal (mu = est sigma = est); 
var cena; 
run;
```
- *NORMAL*– výpočet testů normality. Testuje se nulová hypotéza, že data mají normální rozdělení. 
- *HISTOGRAM*–konstrukce histogramu. 
- *QQPLOT*– konstrukce kvantilového grafu (za předpokladu normality rozdělení by se body v grafu neměly systematicky odchylovat od tzv. referenční přímky).
- Pokud Pr < 0,05 (zvolená hladina významnosti $\alpha$), => nulová hypotéza se zamítá.
# Procedura UNIVARIATE– výpočet intervalů spolehlivosti pro průměr, směrodatnou odchylku a rozptyl
```sas
proc univariate data = priklad cibasic; 
var cena; 
run;
```
# Jednovýběrový test o průměru v proceduře TTEST
```sas
proc ttest data = priklad H0 = 10000; 
var cena; 
run;
```
# Průzkumová analýza v proceduře MEANS
```sas
proc means data = priklad maxdec = 2; 
class system; 
var cena; 
run;
```
# Průzkumová analýza v proceduře UNIVARIATE
```sas
ods select Moments BasicMeasures Testsfornormality;
proc univariate data = priklad normal;
class system; 
var cena;
run;
```
# Průzkumová analýza pomocí histogramů
```sas
proc univariate data = priklad noprint;
class system;
histogram cena; 
run;
```
# Ověření normality rozdělení porovnávaných souborů
Na základě výsledků testů normality bude poté vybrán konkrétní test (parametrický nebo neparametrický).
```sas
proc univariate data = priklad noprint; class system;
histogram cena / normal;
qqplot cena / normal;
run;
```
# Procedura TTEST
Oba soubory mají normální rozdělení => parametrický dvouvýběrový t-test
```sas
proc ttest data = priklad; 
class system; 
var cena; 
run;
```
# Neparametrická obdoba dvouvýběrového t-testu -> Dvouvýběrový Wilcoxonův test
```sas
proc npar1way data = priklad wilcoxon;
class system; 
var cena; 
run;
```
# Procedura TTEST
Soubor diferencí má normální rozdělení => parametrický párový t-test
```sas
proc ttest data = test; 
paired zapocet * zkouska; 
run;
```
# Neparametrická obdoba párového t-testu => Wilcoxonův test (jednovýběrový)
```sas
data test; 
set test; 
dif = zapocet- zkouska; 
ods select testsforlocation; 
proc univariate data = test; 
var dif; run;
```
# Ověření normality rozdělení souboru diferencí
```sas
proc univariate data = test noprint; 
histogram dif / normal; 
qqplot dif / normal (mu = est sigma = est); 
run;
```
# Regresní analýza včetně testů významnosti
```sas
proc reg data = byty;
model cena = plocha;
run;
```
# Korelační analýza
```sas
proc corr data = byty; 
var plocha;
with cena;
run;
```
# Výpočet matice korelačních koeficientů
```sas
proc corr data = byty pearson spearman; 
var plocha cena;
run;
```

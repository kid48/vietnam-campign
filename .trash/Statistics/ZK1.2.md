 1) Pro dobu jízdy mezi městy A a B se předpokládá čas 45 minut. Pro ověření tohoto času byla provedena kontrolní měření s následujícími výsledky.
 40 56 47 64 39 55 44 42 40 55 38 51 44 50
```sas
data jizda;
input mereni@@;
datalines;
40 56 47 64 39 55 44 42 40 55 38 51 44 50 
;
```

a) Vyhodnoťte (číselně i slovně) základní statistické charakteristiky tohoto souboru.
```sas
proc univariate data = jizda normal plot; 
histogram mereni / normal;
qqplot mereni / normal (mu = est sigma = est); 
var mereni; 
proc means data = jizda n mean max q1 q3 median std cv qrange skewness kurtosis maxdec=2; 
var mereni; 
run;
```

Kurtosis (špičatost) = -0,44 což ukazuje, že rozdělení je plošší než normální 
Skewness (šikmost) = 0,633, šikmost je kladná, a to znamená že většina hodnot se nachází pod průměrům a značí asymetrii pravostrannou v rozloženi četnosti 
(N) soubor ma 14 hodnot 
Mean (průměr) je 47,5 
Min je 38 
Max je 64 
Dolni kvartil je 40 
Horni kvartil je 55 
Median (stredni hodnoty) je 45,5 
Variacni koeficient je 16,57 
Směrodatna odchylka je 7,87 
Rozpěti kvartilů je 15

![[../../../../../Assets/Pasted image 20240419024144.png]]

b) V jakém rozmezí se pohybuje průměrná doba jízdy s pravděpodobností 0,95?

```sas
proc univariate data=jizda cebasic; 
var mereni; 
run;
```

![[../../../../../Assets/Pasted image 20240419024504.png]]

95% oboustranné intervaly spolehlivosti 
Mean (průměr) = (42,95 ; 52,04) 
Std.deviation (směrodatná odchylka) = (5,70652 ; 12,68143) 
Variance (rozptyl) = (32,56439 ; 160,81855)

c) Je možné tvrdit, že je doba jízdy mezi městy A a B skutečně 45 minut? Je možné tento předpoklad potvrdit nebo zamítnout? Volbu vhodného postupu odpovídajícím způsobem zdůvodněte, uveďte také číselný důkaz včetně slovního zhodnocení.
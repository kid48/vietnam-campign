# PSYHOLOGICKY TEST
Psychologicky test byl vypracován ve dvou variantách/ Aby se autoři přesvědčili, že obě varianty jsou vyrovnané (stejně obtížné), absolvovala pokusná skupina oba testy (v různém pořadí)  s následujícími výsledky: 

| Osoba č. | Test A | Test B |
| -------- | ------ | ------ |
| 1        | 105    | 107    |
| 2        | 107    | 109    |
| 3        | 120    | 131    |
| 4        | 115    | 110    |
| 5        | 104    | 118    |
| 6        | 108    | 105    |
| 7        | 102    | 100    |
| 8        | 125    | 130    |
| 9        | 106    | 125    |
| 10       | 128    | 121    |
| 11       | 108    | 125    |
| 12       | 116    | 100       |

## a) Mají výsledky testů symetrické či [[Základní statistické charakteristiky#^293655|špičaté]] rozdělení? Vyhodnoťte obě charakteristiky a proveďte srovnání

```sas
data test;

input test$ body@@;

datalines;

testA 105 testA 107 testA 120 testA 115 testA 104 testA 108 testA 102 testA 125 testA 106 testA 128 testA 108 testA 116

testB 107 testB 109 testB 131 testB 110 testB 118 testB 105 testB 100 testB 130 testB 125 testB 121 testB 125 testB 100

;

proc means data=test n mean median min max stddev cv skewness kurtosis;

class test;

var body;

run;
```

![[Pasted image 20230901170534.png]]

Kurtosis = [[Základní statistické charakteristiky#^293655|Špičatost]]
Skewness = [[Základní statistické charakteristiky#Šikmost|Šikmost]]

Špičatost pro TestA je -0,7026, což znamena plošší rozdělení
Špičatost pro testB je -1,5608, což znamena plošší rozdělení

>[!tip]
>Как видно на табличке и как сказано здесь (Если меньше нуля, то пишем ==ploché==)
>То есть значения ближе к краям.

Šikmost pro testA je 0,777 je kladna a ukazuje na levostranná asymetrii v rozlozeni četnosti
Šikmost pro testB je 0,057 je kladna a ukazuje na levostranná asymetrii v rozlozeni četnosti

>[!tip]
>Тут видим, что коеф асимметрии меньше нуля - пишем (по идее левостороннюю), что означает больше малых значений, чем - больших.

## **b)** **Je třeba zjistit, zda jsou oba testy stejné náročné. Jaký postup bude použit, uveďte jej a výběr zdůvodnit**

- Dvouvyběrový neparametrický/parametrický test o středních hodnotách, záleži na rozdělení souborů
- Stanovit H0
- Kontrola rozdělení souboru
- Provedeni testu
- Vysledek zamitnuti nebo přijmutí H0

## **c)** **Jsou splněny základní podmínky pro použiti Vámi zvolené metody?**

>[!tip] Мысли Ильи 
>теперь нужно проверить, является ли здесь нормальное распределение. Используем для определения Shapiro-Wilkův test 

```sas
proc univariate data=test normal;
class test;
var body;
run;
```

### TEST B
![[Pasted image 20230904000748.png]]

Provedeme Shapiro-Wilkův test, test normality Testu B je vetší než kriterium 0,05, proto se nulova hypoteza přijma a proměnna má normální rozdělení
 
  ---
### TEST A
![[Pasted image 20230904000926.png]]

Provedeme Shapiro-Wilkův test, test normality Testu A je vetší než kriterium 0,05, proto se nulova hypoteza přijma a proměnna má normální rozdělení

---
Budeme dale pouzivat Ttest, podminky normalniho rozdeleni jsou splněny

>[!tip] Мысли Ильи
>Так как мы доказали, то что здесь нормальное распределение, то дальше будем использовать **Ttest**

## d) **Je možné konstatovat, že testy jsou stejné náročné?**

```sas
proc ttest data = test;
Class test;
Var body;
```

![[Pasted image 20230904002253.png]]

Na základě **ttestu** P hodnota = **0,4607**, přijmáme nulovou hypotezu a mezi soubory dle zvolené metody nesou statisticky vyznamné rozdíly

----
# STROJE A NAKLADY

Při sledovaní výše ročních nakladu na údržbu strojů byla mimo jiné sledováno, do jake miry mohou byt tyto náklady (tis. Kč) ovlivněny stářím strojů (roky). Bylo provedeno výběrové šetření s následujícími výsledky:

| Stáří stroje (rok) | Náklady údržbu (tis. Kč) |
| ------------------ | ------------------------ |
| 2                  | 12                       |
| 1,2                | 8                        |
| 14,8               | 56,4                     |
| 8,3                | 17                       |
| 9,4                | 21,3                     |
| 3                  | 10                       |
| 4,8                | 12,5                     |
| 15,6               | 61                       |
| 16,1               | 62                       |
| 11,5               | 25                         |

## a) Na zaklade grafického zobrazeni byla jako nejvhodnější vybraná lineární funkce. Zapište její tvar (rovnici).  
```sas
data stroj;
input cena stari@@;
datalines;
12 2 8 1.2 56.4 14.8 17 8.3 21.3 9.4 10 3 12.5 4.8 61 15.6 62 16.1 25 11.5
;
proc reg data=stari;
model cena=stari/r influence spec;
plot cena*stari;
plot r.*p.;
symbol v=dot c=blue;
run;
```
$$cena=-2.558+3.5845*stari $$
>[!tip] Мысли Ильи
>Как видно по коду мы здесь делаем регрессный анализ 
>![[Pasted image 20230904004822.png]]
>

![[Pasted image 20230904004859.png]]

## b) **Jaký závěr učiníte pokud budete testovat hypotézu H0**

P = 0,001, zamítáme H0, regresní koeficient je významný
## с) **Jaka je sila zavislosti mezi uvedenymi proměnnymi? Uveďte všechny miry**

```sas
proc corr data=stroj pearson spearman;
var cena stari;
```
![[Pasted image 20230904005634.png]]
>[!tip] Мысли Ильи
>Тут надо чекнуть коэффициенты **Пирсона** и **Спирмана** 
>**Пирсона**: 0,92652
>**Спирмана**: 0,98788
>Итого эти 2 коэффициента показывают сильную линейную зависимость.
>После этого чекаем на коэффициент детерминации **R-Square** (0,8584)
>![[Pasted image 20230904010201.png]]
>То есть 86% процентов случаев можно объяснить изменения зависимой переменны от независимой.

## d) **Obsahuje model odlehle či vlivné hodnoty? Pokud ano, o jake hodnoty se jedna?**

**Содержит ли модель выбросы или влиятельные значения? Если да, то каковы эти значения?**

**Vybočující hodnoty**

Sloupec Hat Diag H nám říká, jestli se v množině vysvětlující proměnné objevuje vybočující hodnota. Hranice pro vybočující hodnotu se vypočítá 2*(2/10) a to se rovná 0,4. Tato hodnota nepřekračují pozorování, nemame vybočující hodnoty.

>[!tip] Мысли Ильи 
>Hat Diag H вычисляется по формуле $$2*p/n$$, где n -  число всех измерений (в нашем случае 10), а p - количество переменных (у нас 2). Итого **4/10=0.4**
>Исходя из этого у нас нету значений, которые превышают данный порог

**Odlehlé hodnoty**

Sloupec Student Residual nám říká, jestli se v množině vysvětlované proměnné objevuje odlehlá hodnota. Absolutní hodnota odlehlé hodnoty musí být větší než 2. Tato hodnota nepřekračují pozorování, nemame odlehle hodnoty.

>[!tip] Мысли Ильи 
>Просто ищем больше 2

**Vlivné pozorování**

Vlivné hodnoty můžeme určit pomocí sloupce Cook’s D nebo sloupce DFFITS. Kritérium pro posouzení celkové míry vlivnosti pozorování u sloupce Cook’s D je 4/10 = 0,4. Tato hodnota nepřekračují pozorování. Nemáme vlivnou hodnotu. Hranice u sloupce DFFITS pro určení míry vlivnosti vyrovnané hodnoty se vypočítá jako absolutní hodnota 2* odmocnina (2/10) = 0,8944. Tato hodnota nepřekračují pozorování, Nemame vlivnou hodnotu.

>[!tip] Мысли Ильи 
>Тут вычисляется по формуле $$2*\sqrt{p/n}$$
>Потом ищем, что больше 

---
**1) Při rozhodování o nákupu auta z autobazaru byla sledována závislost ceny auta (v tis. Kč) na jeho stáří (roky). Náhodným výběrem byly získány následující údaje:**

| cena | stari |
| ---- | ----- |
| 55   | 13    |
| 240  | 3     |
| 340  | 6     |
| 99   | 11    |
| 59   | 12    |
| 114  | 7     |
| 110  | 10    |
| 230  | 7     |
| 147  | 5     |
| 179  | 5     |
| 210  | 7     |
| 100  | 6      |

**a)**    **Na základě grafického zobrazení byl jako nejvhodnější vybrán lineární regresní model. Zapište jeho tvar.**
```sas
data auta;
input cena stari@@;
datalines;
55 13 240 3 340 6 99 11 59 12 114 7 110 10 230 7 147 5 179 5 210 7 100 6
;
proc reg data=auta;
model cena = stari / r influence spec;
run;
```
$$cena = 297.52813-18.34063*stari$$
![[Pasted image 20230904020604.png]]

>[!tip] Мысли Ильи
>Лежать + САСАТЬ! У меня получилось, осталось дальше по памяти  

b)  Je zvolený model statisticky významný?
Test významnosti pro absolutní člen je **0,0002** a pro regresní koeficient je **0,0170**. Jelikož je p-hodnota parametrů menší než **α = 0,05**, zamítáme se nulovou hypotézu a můžeme tento model považovat za významný.

>[!tip] Мысли Ильи
>Тут все просто: чекаем Pr>|t|. Если все меньше альфы (то есть меньше 0,05), то все *чики-бамбони*

**c) Z kolika procent lze vysvětlit cenu ojetého auta pomocí proměnné věk?**
45%
![[Pasted image 20230904021518.png]]

>[!tip] Мысли Ильи
>Тут все изи: Смотрим на столбик R-Square = 0,4497

**e) Jaká je síla závislosti mezi uvedenými proměnnými?**

```sas
proc corr data=auta pearson spearman;  
var cena stari;  
run;
```

>[!tip] Мысли Ильи
>Тут чекаем нашего любимого **Пирсона**, **Спирмана**
>**Пирсон**: -0,67063
>**Спирман**: -0,72442 
>Итого: **негативная средняя зависимость**

Pearsonův (-0,67) i Spearmanův (-0,72) korelační koeficient značí negativní středně silnou lineární závislost. To potvrzuje předpoklad, nepřímé úměrnosti těchto proměnných – čím větší je cena, tím nižší bude stáři auta.

---

1) Pro dobu jízdy mezi městy A a B se předpokládá čas 45 minut. Pro ověření tohoto času byla provedena kontrolní měření s následujícími výsledky

| 40  | 56  | 47  | 64  | 39  | 55  | 44  | 42  | 40  | 55  | 38  | 51  | 44  | 50  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


**a)** **Vyhodnoťte (číselně i slovně) [[Základní statistické charakteristiky|základní statistické charakteristiky]] tohoto souboru.**

```sas
data jizda;
input mereni@@;
datalines;
40 56 47 64 39 55 44 42 40 55 38 51 44 50
;
proc univariate data=jizda;
run;
```

- Kurtosis ([[Základní statistické charakteristiky#Špičatost|Špičatost]]) = -0,44 což ukazuje, že rozdělení je **plošší než normální**
- Skewness ([[Základní statistické charakteristiky#Šikmost|šikmost]]) = 0,633, šikmost je kladná, a to znamená že většina hodnot se nachází pod průměrům a značí asymetrii pravostrannou (levostranna?) v rozloženi četnosti
- (N) soubor ma 14 hodnot
- Mean (průměr) je 47,5
- Min je 38
- Max je 64
- Dolni kvartil je 40
- Horni kvartil je 55
- Median (stredni hodnoty) je 45,5
- Variacni koeficient je 16,57
- Směrodatna odchylka je 7,87
- Rozpěti kvartilů je 15

**b) V jakém rozmezí se pohybuje průměrná doba jízdy s pravděpodobností 0,95?**

```sas
proc univariate data=jizda cibasic;
var mereni;
run;
```
![[Pasted image 20230904093114.png]]

95% oboustranné intervaly spolehlivosti 
Mean (průměr) = (42.955; 52.04491);
Std. deviation (směrodatná odchylka) = (5.70; 12.68;)
Variance (rozptyl) = (32.56439; 160.81855)
>[!tip] Мысли Ильи
>Короче весь прикол находиться в cibasic. Он как раз и занимается хуйней в расчете при а=0,05 


**с)** **Je možné tvrdit, že je doba jízdy mezi městy A a B skutečně 45 minut? Je možné tento předpoklad potvrdit nebo zamítnout? Volbu vhodného postupu odpovídajícím způsobem zdůvodněte, uveďte také číselný důkaz včetně slovního zhodnocení.**
```sas
proc univariate data=jizda mu0=45;
var mereni;
run;
```

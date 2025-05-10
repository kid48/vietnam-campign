## 1) Při rozhodování o nákupu auta z autobazaru byla sledována závislost ceny auta (v tis. Kč) na jeho stáří (roky). Náhodným výběrem byly získány následující údaje:
cena 55 240 340 99 59 114 110 230 
stáří 147 13 3 6 11 12 179 210 100 7 10 7 5 5 7 6
```sas
data auta;
input cena stari@@;
datalines; 
55 13 240 3 340 6 99 11 59 12 114 7 110 10 230 7 147 5 179 5 210 7 100 6 
; 
proc reg data = work.auta; 
model cena = stari / r influence spec; 
run;
```
#### a) Na základě grafického zobrazení byl jako nejvhodnější vybrán lineární regresní model. Zapište jeho tvar.
![[../../../../../Assets/Pasted image 20240419010349.png]]
Tvar přímky $y= 297.52812-18.34062x$
>[!info]
>Короче после этого смотрим на параметры и строим по формуле $y=nezavisla+zavisla*x$

#### b) Je zvolený model statisticky významný?

Test významnosti pro absolutní člen je 0,0002
a pro regresní koeficient je 0,0170. 
Jelikož je p-hodnota parametrů menší než α = 0,05, zamítáme se nulovou hypotézu a můžeme tento model považovat za významný.
>[!info]
>Проверка значимости для абсолютного члена 0,0002, для регрессного коэффициента 0,0170, что меньше, чем 0,05. Что означает мы отвергаем нулевую гипотезу и можем считать эту модель значимой.

c) Z kolika procent lze vysvětlit cenu ojetého auta pomocí proměnné věk?

![[../../../../../Assets/Pasted image 20240419011551.png]]

Intenzita závislosti mezi proměnnou cena a proměnnou obsah je 44% (R-Square) a 
Korelační koeficient se vypočítá jako odmocnina 0.4497 a to se rovná 0.6705. 
Hodnota korelačního koeficientu je větší než 0.3, tudíž se jedná o střední silnou závislost mezi závislou proměnnou cena a nezávislou proměnnou stari.

>[!info]
>Интенсивность зависимости ровняется 44%. А корень с этого числа ровняется коэффициенту корреляции $\sqrt{0.4497}=0.6705$, которая больше чем 0,3 средняя сильная корреляция
>

### d) V rámci hodnocení kvality regresního modelu se provádí regresní diagnostika. Jaké jsou její závěry?
![[../../../../../Assets/Pasted image 20240419013101.png]]
V tabulce máme výsledky Whiteova testu, který ověřuje splnění předpokladu homoskeadasticity reziduí neboli konstantnosti rozptylu reziduí. P-hodnota je větší než α = 0,05, tudíž se H0 přijímá. To v našem případě je, protože p-hodnota testu je 0,2243 a to znamená, že rezidua mají konstantní rozptyl.

>[!tip] **heteroskedastičnost** ve statistice je definovaná tak, že podmíněný [rozptyl](https://cs.wikipedia.org/wiki/Variance "Variance") náhodné veličiny není konstantní, (je [nehomogenní](https://cs.wikipedia.org/wiki/Nehomogenita "Nehomogenita")). 
>![](https://upload.wikimedia.org/wikipedia/commons/a/a5/Heteroscedasticity.png)
>То есть **Гетероскедасти́чность**, означающее неоднородность наблюдений, выражающуюся в неодинаковой (непостоянной) дисперсии случайной ошибки регрессионной (эконометрической) модели.

>[!tip] **Homoskedasticita** nebo **homoskedastičnost** ve statistice znamená, že podmíněný [rozptyl](https://cs.wikipedia.org/wiki/Rozptyl_(statistika) "Rozptyl (statistika)") dané [náhodné veličiny](https://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%A1_veli%C4%8Dina "Náhodná veličina") je konstantní (je homogenní).
>![](https://upload.wikimedia.org/wikipedia/commons/9/93/Homoscedasticity.png)
>**Гомоскедастичность** ([англ.](https://ru.wikipedia.org/wiki/%D0%90%D0%BD%D0%B3%D0%BB%D0%B8%D0%B9%D1%81%D0%BA%D0%B8%D0%B9_%D1%8F%D0%B7%D1%8B%D0%BA "Английский язык") homoscedasticity) — свойство, означающее постоянство условной дисперсии вектора или последовательности случайных величин.

>[!info]
>Итого если Вероятность ChiSq больше 0,05,то že rezidua mají konstantní rozptyl. (Дисперсия постоянная). Иначе непостоянный!

**Vybočující hodnoty**
Sloupec Hat Diag H – diagonální prvky projekční matice nám říká, jestli se v množině vysvětlující proměnné objevuje vybočující hodnota. Hranice pro vybočující se rovná 0,333. Tuto hodnotu překračují pozorování 1, jedná se tedy o vybočující hodnoty. 
>[!info] То есть, есть ли в этой таблице значение больше 0,33 то это значение выбивается

**Odlehlé hodnoty** 
Sloupec Student Residual nám říká, jestli se v množině vysvětlované proměnné objevuje odlehlá hodnota. Absolutní hodnota odlehlé hodnoty musí být větší než 2. Tato hodnota překročena pozorováním 3. 
>[!info] Колонка "Остаток Стьюдента" показывает, есть ли в наборе объясняемой переменной выброс. Абсолютное значение выброса должно быть больше 2. Это значение превышено в наблюдении 3. 


**Vlivné pozorování** 
Vlivné hodnoty můžeme určit pomocí sloupce Cook’s D nebo sloupce DFFITS. Kritérium pro posouzení celkové míry vlivnosti pozorování u sloupce Cook’s D je 0,333. Hranici překračuje pozorování 3. Jedná se tedy o vlivnou hodnotu. Hranice u sloupce DFFITS pro určení míry vlivnosti vyrovnané hodnoty se vypočítá jako absolutní hodnota 2* odmocnina (2/12) = 0,816. Tato hranici není překročena pozorováním a nemáme vlivnou hodnotu.


**Влиятельные наблюдения**. 
Влиятельные значения могут быть определены с помощью колонки Кука D или колонки DFFITS. Критерий оценки общего уровня влияния наблюдения для столбца D Кука составляет 0,333. Порог превышен наблюдением 3, поэтому оно является влиятельным. Пороговое значение для столбца DFFITS для определения уровня влияния сбалансированного значения рассчитывается как абсолютное значение 2*квадратный корень (2/12) = 0,816. Этот порог не пересекается наблюдениями, и у нас нет влиятельного значения.


### e) Jaká je síla závislosti mezi uvedenými proměnnými?

```sas
proc corr data=auta pearson spearman;
var cena stari; 
run; 
```

![[../../../../../Assets/Pasted image 20240419015718.png]]

Pearsonův (-0,67) i Spearmanův (-0,72) korelační koeficient značí negativní středně silnou lineární závislost. To potvrzuje předpoklad, nepřímé úměrnosti těchto proměnných – čím větší je cena, tím nižší bude stáři auta.

>[!info] Итого смотря на коэффициент спиермана и пирсона они негативные, что означает негативную среднее сильную зависимость. Чем выше цена тем менее старое авто


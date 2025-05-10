---
undefined: ""
---
**Závislost příčinná** (kauzální) – jeden jev (příčina) vyvolává existenci (vznik, změnu, zánik apod.) jevu druhého.
**Závislost pevná** – výskytu jednoho jevu nutně odpovídá výskyt druhého jevu (a naopak).
**Volná závislost** – jeden jev podmiňuje jev jiný jen s určitou pravděpodobností a v různé intenzitě.

**Regrese** – charakterizuje průběh závislosti a změny závisle proměnného znaku na základě změn jedné či více nezávisle proměnných.

**Korelace** – měří těsnost korelační závislosti. Měření těsnosti spočívá ve zjištění, jak těsně se jednotlivé skutečně napozorované hodnoty přimykají regresní čáře, kterou jsme vystihli průběh závislosti.

>[!info] **Корреляция** - измеряет тесноту корреляционной зависимости. Измерение тесноты заключается в том, насколько точно фактические наблюдаемые значения соответствуют линии регрессии, которую мы использовали для построения зависимости.

# Druhy závislostí

## podle počtu kvantitativních znaků 
- závislost jednoduchá 
- závislost vícenásobná 
## podle typu regresní funkce
- lineární závislost 
- nelineární závislost 
## podle směru změn kvantitativních znaků 
- závislost pozitivní (kladná, přímá) 
- závislost negativní (záporná, nepřímá)

# Dvourozměrná analýza dat
Základní postup dvourozměrné analýzy:
- Nejdříve se pokusíme zobrazit data graficky.
- Hledáme základní konfigurace a tendence v datech.
- Přidáváme numerické charakteristiky různých aspektů dat.
- Stručným způsobem vystihnout základní konfiguraci dat se často podaří pomocí pravděpodobnostního modelu.


# Regresní analýza

Statistické problémy, které nás v regresní analýze zajímají, jsou:
- získání statistických parametrů regresní funkce,
- testování hypotéz o těchto parametrech,
- ověřování předpokladů regresního modelu.

>[!info] Статистические проблемы, интересующие нас в регрессионном анализе, таковы:
>- получение статистических параметров функции регрессии,
>- проверка гипотез об этих параметрах,
>- проверка предположений регрессионной модели.

**Reziduální odchylka** – rozdíl mezi naměřenou a teoretickou hodnotou.
>[!tip] Разница между измеренным и теоретическим значением 

# Postup při stanovení nejvhodnější funkce

- logické posouzení daného vztahu – věcný rozbor vztahů mezi proměnnými
- vytvoření tzv. korelačního pole
- volba nejvhodnější regresní funkce na základě matematicko-statistických kritérií

>[!info] 
>- логическая оценка заданных отношений - фактический анализ связей между переменными
>- построение так называемого корреляционного поля
>- выбор наиболее подходящей функции регрессии на основе математических и статистических критериев

# Lineární regresní model
Jednostranná závislost – proměnná X je nezávisle proměnná a Y závisle proměnná.
Oboustranná závislost – nelze přesně rozhodnout, která proměnná je závislá a která nezávislá (sdružené přímky).

Jestliže graf ukáže *lineární* vztah mezi proměnnými, usilujeme o zachycení vztahu tím, že body proložíme přímku ve tvaru $y'=a+b*x$.

**regresní koeficienty** - udávají, o kolik jednotek se v průměru změní závisle proměnná, změní-li se nezávisle proměnná o jednotku.

# Odhady v regresní analýze
Interpolace – předmětem zájmu je některá z použitých kombinací vysvětlujících proměnných 
Extrapolace – pozornost je upřena na hodnotu proměnné Y pro předpokládanou budoucí hodnotu proměnné X

>[!info]
>Интерполяция - интересующая переменная является одной из комбинаций используемых объясняющих переменных 
>Экстраполяция - внимание сосредоточено на значении переменной Y для ожидаемого будущего значения переменной X

*odhad průměrné hodnoty* $y_i$ - k odhadu bude použit regresní koeficient,
*odhad konkrétní hodnoty* $y´_i$ – k odhadu bude se použije celá regresní funkce 

# Korelace
- vyjadřuje míru stupně (sílu) závislosti proměnných.

Často je zbytečné měřit závislost v případech, když je korelace způsobena:
- formálními vztahy mezi proměnnými, 
- nehomogenitou studovaného základního materiálu, 
-  působením společné příčiny.

>[!info] ситуациb, в которых измерение корреляции между переменными может быть неинформативным или даже вводящим в заблуждение
>- *Формальные взаимоотношения между переменными*. (как площадь круга, которая вычисляется через радиус)
>- *Негомогенность исследуемого материала* (если исследование включает данные по доходам в разных странах с сильно различающимся уровнем жизни, корреляция между доходом и уровнем образования может быть искажена из-за этих различий.)
>- *Действие общей причины* (потреблением мороженого и числом случаев утопления существует корреляция.)

Zdánlivé korelace – jsou způsobené časovým faktorem nebo faktorem modernizace u dvou řad údajů. 
„Nesmyslné“ korelace – vysoká hodnota korelace, nesmyslný je závěr o příčinném působení.
Matoucí (rušivé) proměnné – korelují jak s cílovou proměnnou, tak s proměnnou ovlivňující.

### 1. Koeficient korelace (Коэффициент корреляции)

Это статистическая мера, которая показывает степень и направление линейной зависимости между двумя переменными. Самый известный коэффициент корреляции — это коэффициент корреляции Пирсона, который измеряет линейную зависимость между двумя непрерывными переменными. Его значения находятся в диапазоне от -1 до 1
![[../../../../../Assets/Pasted image 20240507123923.png|500]]

### 3. Index determinace (Индекс детерминации, $R^2$)

Индекс детерминации, также известный как $𝑅^2$ (R-квадрат), это статистический показатель, который используется для оценки качества подгонки модели регрессии к наблюдаемым данным. Он показывает долю вариации зависимой переменной, объясненной независимыми переменными в модели. Значения $R^2$ находятся в диапазоне от 0 до 1, где:

- **0** означает, что модель не объясняет вариабельность данных,
- **1** означает, что модель идеально объясняет вариабельность данных.

# Spearmanův korelační koeficient pořadí

- používá se u méně rozsáhlých souborů nebo když chceme získat rychlou představu o intenzitě závislosti 
- zachycuje pouze monotónní vztahy 
- je rezistentní vůči odlehlým hodnotám 
- při výpočtu nahrazujeme původní hodnoty pořadovými čísly (при вычислениях мы заменяем исходные значения порядковыми номерами)
- jestliže r s = 1, resp. r s =-1, párové hodnoty (x i , y i ) leží na nějaké vzestupné, resp. klesající funkci

# Testy hypotéz o parametrech lineární regrese a odhady charakteristik regrese a korelace
## Test významnosti korelačního koeficientu
Сначала тестируем на нулевую годноту. То есть нулевая гипотеза заключается в том, что зависимости не существует

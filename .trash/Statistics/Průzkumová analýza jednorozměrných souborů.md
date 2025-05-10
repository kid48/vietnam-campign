---
undefined: ""
---
>Účelem průzkumové analýzy dat je odhalit jejich zvláštnosti a ověřit předpoklady pro následné statistické zpracování.

>[!info] То есть целью поискового анализа - выявить особенности данных для дальнейшей статистической обработки
>

- ==Blok A== představuje samotnou průzkumovou analýzu, kdy se vyšetřují statistické zvláštnosti dat.
- V ==bloku B== se ověřují základní předpoklady kladené na výběr jako jsou ==nezávislost prvků==, ==homogenita výběru==, ==dostatečný rozsah výběru== a ==rozdělení výběru==.
- ==Blok C== představuje tzv. konfirmatorní analýzu, která se zaměřuje na ověřování hypotéz.

Эта процедура может быть сведена до 3 блока:
- Блок А представляет собой сам поисковый анализ, в ходе которого изучается статистические особенности данных
- Блок Б проверяет основные предположения для отбора такие как независимость выборки, однородность выборки, достаточный размер и распределение
- Блок С подтверждающий анализ, который сосредоточен на проверку гипотез

# Blok A: průzkumová (exploratorní) analýza dat (EDA)
- odhalení stupně symetrie a špičatosti výběrového rozdělení, 
- indikace lokální koncentrace výběru dat, 
- nalezení vybočujících a podezřelých prvků ve výběru, 
- porovnání výběrového rozdělení dat s typickými rozděleními, 
- mocninná transformace výběru, 
- Boxova–Coxova transformace výběru

>[!info] В блоке А мы проверяем
>-  симметрию и пикообразность (шпичатост) выборочного распределения,
>- находим локальную концентрацию данных, 
>- ищем выбросы и подозрительные элементы
>- сравниваем распределение выборочных данных с типичными распределениями
>- преобразование силы выбора
>- Преобразование Бокса-Кокса для отбора

  
>Box-Cox преобразование — это метод преобразования данных для стабилизации дисперсии и приближения к нормальному распределению. Это полезно, потому что многие статистические методы работают лучше, если данные ближе к нормальному распределению.

## Metody průzkumové analýzy dat

>Cílem průzkumové analýzy EDA je nalezení zvláštností statistického chování dat.

Pro průzkumovou analýzu se užívají především ==grafické metody==, které umožňují komplexní posouzení statistických zvláštností dat.

>[!info] То есть проще всего ориентироваться на графические методы, так как там проще всего всесторонне оценить особенности данных
>

### Krabicový graf (Boxplot)
pro částečnou sumarizaci dat, graf umožňuje 
- znázornění robustního odhadu polohy, 
- posouzení symetrie v okolí kvantilů, 
- posouzení symetrie u konců rozdělení, 
- identifikaci odlehlých dat

>[!info] для частичного обобщения данных, диаграмма позволяет:
>- показать надежную оценку положения, 
>- оценить симметрию вокруг квантилей, 
>- оценка симметрии на концах распределения, 
>- выявление выходящих за рамки данных

![[../../../../../Assets/Pasted image 20240506161538.png|500]]

### Histogram
– sloupcový graf, kdy výšky sloupců odpovídají empirickým hustotám pravděpodobnosti.
![[../../../../../Assets/Pasted image 20240506161730.png|500]]

### Spojnicový graf
– prosté rozdělení četností, časovéřady

![[../../../../../Assets/Pasted image 20240506191826.png]]

### Bodový graf
– jednoduchý způsob zobrazení rozptýlení dat, posouzení shluků a odlehlých hodnot
![[../../../../../Assets/Pasted image 20240506191938.png]]

### Kvantilově–kvantilový graf (graf Q– Q)
– umožňuje posoudit shodu výběrového rozdělení, je charakterizováno kvantilovou funkcí QE(P) s kvantilovou funkcí zvoleného teoretického rozdělení QT(P).
![[../../../../../Assets/Pasted image 20240506192020.png|500]]
>позволяет оценить соответствие распределения выборки, оно характеризуется квантильной функцией QE(P) с квантильной функцией выбранного теоретического распределения QT(P).

![[../../../../../Assets/Pasted image 20240506192250.png|500]]
>**Основное различие** между этими графиками заключается в том, что Q-Q график сравнивает квантили, а P-P график сравнивает кумулятивные вероятности. Это делает Q-Q график более чувствительным к отклонениям в хвостах распределения, так как он акцентирует внимание на экстремальных значениях данных. P-P график может быть более информативен при оценке соответствия центральной части распределения.

# Blok B: ověření předpokladů o datech

- ověření nezávislosti prvků výběru, 
- ověření homogenity rozdělení výběru, 
- určení minimálního rozsahu výběru, 
- ověření normality rozdělení výběru

## 1. předpoklad: prvky výběru jsou vzájemně nezávislé

K identifikaci časové závislosti prvků výběru nebo závislosti související s pořadím jednotlivých měření testuje se významnost autokorelačního koeficientu prvního řádu podle testovacích ==von Neumannova kritérií==

Чтобы определить временную зависимость элементов выбора или зависимостей, связанных с порядком проведения отдельных измерений, проверяется значимость коэффициента автокорреляции первого порядка в соответствии с критерием ==фон Неймана==

## 2. předpoklad: výběr je homogenní

Homogenní výběr znamená, že všechny jeho prvky pocházejí ze stejného rozdělení s konstantním rozptylem.

>[!info] Гомогенность (Однородность) выбора - показывает, что элементы исходят из того же распределения с постоянной дисперсией (розптил) 

K nehomogenitě naměřených dat dochází všude tam, kde se vyskytuje výrazná nestejnoměrnost naměřených vlastností vzorků nebo se náhle mění podmínky experimentů. Speciálním případem jsou odlehlá měření.

>[!info] Неоднородность измеренных данных встречается повсеместно, где существует значительная неоднородность измеряемых свойств образца или резких изменений условий экспериментов. Особым случаем являются отклоняющиеся измерения.


### 3. předpoklad: rozdělení výběru je normální

Normalita výběrových rozdělení patří k ==základním předpokladům== většiny statistických metod.
Testy jsou obecně vždy méně citlivé na odchylky od normality než diagnostické grafy a navíc odchylka od normality může být mnohdy ==způsobena vybočujícími hodnotami==. 
Když není normalita rozdělení prokázána, je nutné hlouběji analyzovat data. 
Řada silných testů normality je odvozena z rankitových grafů. Příkladem je často užívaný test ==Shapirův– Wilkův==.

==Нормальность выборочных распределений== - одно из ==основных== предположений большинства статистических методов.
Тесты, как правило, всегда менее чувствительны к отклонениям от нормальности, чем диагностические графики, и, кроме того, отклонения от нормальности часто могут быть вызваны выбросами. 
Когда ==нормальность распределения не установлена==, необходимо провести более глубокий анализ данных. 
Многие сильные тесты на нормальность получаются из графиков ранжирования. Примером может служить часто используемый тест ==Шапиро-Уилка==.

#### Normální rozdělení N ($\micro,\gamma^2$)

Grafem hustoty pravděpodobnosti je „zvonovitá“ symetrická křivka, nabývající maxima v bodě x = , která se nazývá Gaussovou křivkou

![[../../../../../Assets/Pasted image 20240506195357.png|500]]
#### Distribuční funkce

Функция распределения нормального распределения не может быть выражена в виде элементарных функций, поэтому ее значение может быть определить с помощью таблиц

#### Výběrová rozdělení náhodných veličin

Při zobecňování výsledků mají mimořádný význam tzv. výběrová rozdělení spojitých náhodných veličin, jejichž tabelované hodnoty pomáhají vyhodnotit a interpretovat výsledky metod statistické indukce. Do této skupiny výběrových rozdělení patří např.: 
- Studentovo t-rozdělení, 
- $\chi^2$ rozdělení (chí-kvadrát rozdělení), 
- F-rozdělení (Fisher-Snedocorovo rozdělení)

>[!info] 
>- **Распределение Стьюдента (t-распределение)**: Используется для оценки средних значений генеральной совокупности, когда размер выборки невелик или дисперсия генеральной совокупности неизвестна.
>- **Распределение хи-квадрат (χ²-распределение)**: Применяется для анализа дисперсии и тестирования гипотез о независимости или согласии.
>- **F-распределение**: Используется в анализе дисперсии для сравнения дисперсий двух или более выборок.

### 4. předpoklad: určení minimálního rozsahu výběru

Stanovení dostatečné velikosti výběru je možné provést několika způsoby. Nejznámější postup vychází z intervalového odhadu průměru základního souboru.

>[!info] То есть задача определить достаточно ли у нас значений, чтобы делать выводы, что можно "доверять" этой выборке

# Blok C: konfirmatorní analýza dat (CDA) 
– odhady parametrů (polohy, variability a tvaru):

- klasické odhady (bodové a intervalové) z výběru, 
- robustní odhady (bodové a intervalové) z výběru.

Z nabídky odhadů parametrů vybírá uživatel uvážlivě ty, jež mají statistický smysl a odpovídají závěrům průzkumové analýzy dat a ověření předpokladů o výběru

Из меню оценок параметров пользователь выбирает те, которые имеют статистический смысл и согласуются с выводами исследовательского анализа данных и проверки предположений выбора

## Postup průzkumové analýzy

### Analýza rutinních dat
Zde předpokládáme, že známe rozdělení souboru dat. Rozdělení je obvykle normální a data splňují předpoklady nezávislosti a homogenity
>[!info] Здесь мы предполагаем, что нам известно распределение набора данных. Распределение обычно нормальное, а данные удовлетворяют предположениям о независимости и однородности
### Analýza neznámých dat
- průzkumová analýza dat EDA s využitím řady grafických metod
- určení výběrového rozdělení a jeho konstrukce
Текст, который вы привели, касается анализа неизвестных данных и описывает два ключевых метода или этапа в обработке и анализе данных:

 1. Процесс ==разведочного анализа данных (EDA)== с использованием графических методов
	Разведочный анализ данных (Exploratory Data Analysis, EDA) — это подход к анализу данных, который акцентируется на первичном исследовании и визуализации данных перед формулированием основных гипотез или построением моделей. EDA включает в себя использование различных графических методов, таких как ==гистограммы==, ==диаграммы размаха== (ящик с усами), ==диаграммы рассеяния== и т.д., чтобы помочь аналитикам лучше понять распределение, тенденции, аномалии и взаимосвязи в данных. Это позволяет:
	- Определить основные характеристики данных.
	- Обнаружить возможные аномалии или выбросы.
	- Понять взаимосвязи между различными переменными.
	- Выявить шаблоны и тенденции в данных.

2. Определение выборочного распределения и его конструкция
	После проведения EDA следующим шагом часто является определение выборочного распределения данных. Этот этап включает в себя анализ распределения данных для понимания, какие статистические модели или распределения могут быть применены для дальнейшего анализа и моделирования. Выборочное распределение помогает определить:
	- Как данные распределены (нормально, экспоненциально и т.д.).
	- Параметры распределения, которые могут включать среднее, медиану, стандартное отклонение и т.д.
	- Подходящие статистические тесты и методы анализа для проверки гипотез.
## *Postup při nesplnění požadavků o datech*
### **Nesplnění požadavku nezávislosti prvků**
Je třeba hlouběji analyzovat logické příčiny, zkontrolovat celý měřicí řetězec a provést nová měření. 
> Необходимо более глубоко проанализировать логические причины, проверить всю цепочку измерений и провести новые измерения. 
### **Nesplnění předpokladu normality výběru** 
Rozdělení dat je buď jiné než normální nebo jsou v datech vybočující měření. V případě nenormálního rozdělení dat může jít o odchylky pouze v délce konců nebo se jedná o zešikmená rozdělení. Lze zvážit použití transformace dat.
>Распределение данных либо отличается от нормального, либо в данных присутствуют отклонения от нормы. В случае ненормального распределения данных могут быть отклонения только по длине концов или перекосы. Можно рассмотреть возможность использования преобразования данных.
### **Přítomnost vybočujících hodnot**

Na základě logické analýzy je třeba nejdříve zvážit, zda nejde o zešikmené rozdělení.

Body, které se jeví jako vybočující pro symetrické rozdělení, mohou naopak být přijatelné pro zešikmená rozdělení. 
Pokud jde o vybočující pozorování, lze použít dvou alternativ. 
*První spočívá* v jejich vyloučení z další analýzy, což však není vždy zcela nejvhodnější. 
*Druhá alternativa spočívá* v použití robustních metod

>На основе логического анализа необходимо сначала определить, является ли это распределение асимметричным. И наоборот, точки, которые кажутся выброшенными для симметричных распределений, могут быть приемлемыми для перекошенных распределений. Когда речь идет об отклоняющихся наблюдениях, можно использовать две альтернативы. 
>- Первый вариант - исключить их из дальнейшего анализа, но он не всегда является наиболее подходящим. 
>- Вторая альтернатива - использовать робастные методы.
### **Nedostatečný rozsah výběru**

Nejjednodušší je v tomto případě provést dodatečná měření. Platí, že čím jsou data méně rozptýlená, tím menší počet jich stačí k zajištění dostatečné přesnosti odhadu

>Просто провести дополнительные измерения


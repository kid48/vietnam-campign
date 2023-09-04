
# Míry polohy (střední hodnoty)

- Udávají polohu středu rozdělení
- Průměry **prosté**
	- **Aritmetický průměr** (Mean) – _Sečtu všechny hodnoty a vydělím počtem hodnot_ (Среднее арифметическое)
	- **Geometrický průměr** – _Vynásobím všechny hodnoty a udělám odmocninu na počet hodnot_ Среднее геометрическое)
- Průměry **vážené** (tedy tříděné), **robustní** charakteristiky (nejsou náchylné na extrémy)
	- **Medián** – Prostřední hodnota v souboru uspořádaném podle velikosti (cреднее значение, если поставить значения по порядку)
	- **Modus** – Hodnota s největší četností (самое частое значение)

# Míry variability

- Hodnotí rozptýlenost hodnot daného souboru okolo středu
- **Variační rozpětí** (výběrové) – _Rozdíl nejvyšší a nejnižší hodnoty v souboru_  (Разница между самым высоким и низким значением)
- **Mezikvartilové rozpětí** – _Diference horního a dolního kvartilu_ 

>[!todo] 
>- Разобраться с квартилями [[Boxplot#Что такое Boxplot?|здеся]]

- Směrodatná odchylka – _Odmocnina z rozptylu_
	- Průměrná vzdálenost všech hodnot souboru od průměrné hodnoty 
	- ==Среднее расстояние всех значений набора от среднего значения==
- Rozptyl – _Směrodatná odchylka na druhou_ 
	- Není vhodná na interpretaci, lepší je směrodatná odchylka
- Variační koeficient – _Podíl směrodatné odchylky a absolutní hodnoty ze střední hodnoty_ 
	- Základní míra relativní variability, možno použít při porovnávání více souborů s rozdílnou velikostí průměru, či dokonce jednotky
	- Nad 50% naznačuje asymetrii dat a **porušení normality** 
	- Do 50 % není nijak významná variabilita, že by ovlivňovala výsledky

>[!quote] Максим M3ndax
>это величина равная отношению стандартного (среднеквадратичного) отклонения случайной величины к ее математическому ожиданию

>[!tip]
 >По идее он должен показывать насколько разная выборка
# Špičatost
- Špičatost (Kurtosis) - je charakteristika rozdělení náhodné veličiny, která porovnává dané rozdělení s normálním rozdělením pravděpodobnosti  ^293655
- Pomocí měr špičatosti hodnotíme koncentraci prvků souboru v blízkosti určité hodnoty znaku, představa o tvaru rozdělení četností

>[!info] 
>Куртозис в статистике — это как описать, насколько у нас "взлеты и падения" в данных. Представь, что у нас есть куча мячиков разных размеров и мы кидаем их на прыгающую доску. Если мячики часто прыгают очень высоко или очень низко, то у нас высокий куртозис — много "взлетов и падений".
>Если же мячики в основном прыгают на одинаковой, средней высоте, без сильных "взлетов и падений", то у нас низкий куртозис.
>Таким образом, куртозис помогает нам понять, насколько необычными или "интересными" могут быть наши данные. Хочется много взлетов и падений или всё на одном уровне — вот в чём вопрос!

>[!tip]
>То есть, насколько сильно отличается показатели от средних значений. Если коефициент больше 0, то значение ближе к среднему значению. Если ровно нулья  

>[!quote] Максим M3ndax
>При Б больше нуля все разделение мы обозначаем как заостренное
>при Б равно нулю нормальным разостренным
>и при б меньше нуля как плоское

| $$\beta^2>0$$                           | $$\beta=0$$                    | $$\beta<0$$                     |
| --------------------------------------- | ------------------------------ | ------------------------------- |
| Rozdělení hodnotíme jako špičaté        | Rozdělení normálně zašpičatělé | Rozdělení hodnotíme jako ploché |
| Hodnoty spíše blíže **střední hodnotě** |                                |   Hodnoty spíše blíže **okrajům**                              |
# Šikmost

- Šikmost (Skewness) - je charakteristika rozdělení náhodné veličiny, která popisuje jeho nesymetrii. 
- Charakterizují souměrnost (**symetrii**) rozložení četnosti ve statistickém souboru

>[!info] 
>Коэффициент асимметрии — это как описать, насколько наша кучка мячиков неровно распределена. Допустим, у тебя есть много мячиков, и ты хочешь узнать, больше ли их с одной стороны или с другой.
>Если все мячики кучкуются с одной стороны, например, все ближе к левому краю, то у нас есть "левосторонняя" асимметрия. А если мячики собрались с правой стороны, у нас "правосторонняя" асимметрия.
>Если же мячики распределены примерно одинаково с обеих сторон, значит, у нас нет асимметрии, и это как будто бы "идеальная" кучка мячиков.
>Так вот, коэффициент асимметрии помогает понять, с какой стороны у нас мячиков больше или меньше, и насколько это выражено.

| $$\alpha^1>0$$                          | $$\alpha=0$$                   | $$\alpha<0$$                    |
| --------------------------------------- | ------------------------------ | ------------------------------- |
| Data jsou **sešikmená zleva od průměru**   (pravostranna asymetrie)    |	Jedná se o souměrné rozdělení	 | Data jsou sešikmená zprava od průměru |
| Převládají malá čísla oproti velkým|                                | Převládají vyšší hodnoty oproti malým |


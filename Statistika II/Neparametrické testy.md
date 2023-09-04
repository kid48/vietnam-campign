- Pakliže není splněn požadavek, normality výběru, je nutné použít neparametrické testy
- Testy jsou založeny na obecnějších předpokladech, což testům snižuje přesnost, čímž pádem se zvyšuje riziko chyby
- Provádíme na základní soubory, které pocházejí z výrazně nenormálních souborů

>[!info] 
>- Если требование нормальности выборки не выполняется, необходимо использовать непараметрические тесты
>- Тесты основаны на более общих предположениях, что снижает точность тестов, увеличивая риск ошибки
>- Выполняются на базовых файлах, полученных из существенно ненормальных файлов

**Hlavní přednosti neparametrických testů**

·       **nezávislost** na tvaru rozdělení
·       použitelnost pro znaky **kvantitativní** i **kvalitativní**
·       jsou mnohem **jednodušší** a **rychlejší**

*Nedostatek – menší síla testu*

---
### **Znaménkový test** (jednovýběrový)

je nejjednodušší neparametrickou obdobou párového t–testu.

V testu **nepoužíváme žádné naměřené hodnoty**, stačí nám rozhodnutí, zda pokusný zásah „A“ zapůsobil více či méně než pokusný zásah „B“. Jde v podstatě o test, kdy **nepoužíváme hodnoty rozdílů, ale pouze jejich znaménka**.

>[!tip]
>Он используется для оценки парных испытаний в случаях, **когда мы не можем точно измерить изучаемую величину.** Мы не используем какие-либо измеренные значения в тесте, нам нужно только решить, оказывает ли экспериментальное вмешательство «А» большее или меньшее влияние, чем экспериментальное вмешательство «В». По сути, это тест, **в котором мы используем не значения разностей, а только их знаки**.

---
### **Mann-whitneuv test** (Dvouvýběrový závisly)

je neparametrickou obdobou dvouvýběrového t–testu pro závislé soubory.

Používá se pro hodnocení nepárových pokusů, kdy porovnáváme 2 různé soubory (pokusný zásah A, B). Testujeme hypotézu, že veličina X odpovídající pokusnému zásahu „A“ a veličina Y odpovídající pokusnému zásahu „B“  mají stejne rozdělení pravděpodobností.

>[!tip]
>Он используется **для оценки непарных испытаний**, когда мы сравниваем 2 разных набора образцов (пробное вмешательство A, B). Мы проверяем гипотезу о том, что величина X, соответствующая пробному вмешательству «А», и величина Y, соответствующая пробному вмешательству «В», имеют одинаковое распределение вероятностей. При этом величины X и Y не обязательно должны соответствовать гауссовскому нормальному распределению, достаточно считать их непрерывными

>[!info]
>Предположим, вы исследуете, как разные диеты влияют на уровень холестерина в крови. У вас есть две группы людей: одна следует диете с низким содержанием жиров, а другая — диете с высоким содержанием белка. После двух месяцев эксперимента вы замеряете уровень холестерина у всех участников.
>
>У вас есть два набора данных — один для каждой группы — но распределение не выглядит нормальным. Кроме того, в каждой группе всего 10 человек, что делает выборку довольно маленькой.
>
>В этом случае тест Манна-Уитни может быть очень полезным. Этот непараметрический тест не требует, чтобы данные были нормально распределены, и он подходит для маленьких выборок.

---

### **Wilcoxonův test** (Dvouvýběrový nezávisly)

je neparametrickou obdobou dvouvýběrového t–testu pro nezávislé soubory.

Používá se pro hodnocení párových pokusů, kdy sledovaná veličina neodpovídá Gaussovu normálnímu rozdělení. Porovnává 2 měření provedená u jednoho výběrového souboru. Testuje hypotézu rovnosti distribučních funkcí na základě ověření symetrického rozložení sledované náhodné veličiny

>[!tip]
>Он используется для оценки парных испытаний, **когда отслеживаемая переменная не соответствует нормальному распределению Гаусса**. Сравнивает 2 измерения, выполненные на одном наборе образцов. Проверяет гипотезу о равенстве функций распределения на основе проверки симметричности распределения контролируемой случайной величины

---
### **Kruskal – Wallisův test** (více výběrovy)

je neparametrickou obdobou analýzy rozptylu jednoduchého třídění.

nazývaný také **jednosměrný řádek** ANOVA. Tento test je zaměřen na [střední](https://cs.frwiki.wiki/wiki/M%C3%A9diane_(statistiques) "Medián (statistika)") části populace a nabízí jako [nulové hypotéze](https://cs.frwiki.wiki/wiki/Hypoth%C3%A8se_nulle "Hypothèse nulle") , že [vzorky](https://cs.frwiki.wiki/wiki/%C3%89chantillon_(statistiques) "Échantillon (statistiques)") nejsou stejné a pocházejí ze stejného vzorku populace.

>[!tip]
>также называемый однофакторным дисперсионным анализом — это непараметрический метод, используемый для проверки того, взяты ли образцы из одного и того же распределения. Этот тест ориентирован на медиану генеральной совокупности и предлагает в качестве нулевой гипотезы, что выборки не равны и взяты из одной и той же выборки генеральной совокупности.
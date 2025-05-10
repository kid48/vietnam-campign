---
undefined: ""
---
```sas
proc reg data = byty; 
model cena = plocha / r influence spec; 
run;
```
# Identifikace odlehlých pozorování
**Studentizovaná rezidua** - zaměřují se na odlehlé hodnoty v množině Y Odlehlé pozorování je identifikováno tehdy, jestliže $|SR|>2$
**Prvky projekční matice H** - zaměřuje se na hledání odlehlých hodnot v množině X Odlehlé pozorování je takové, které překročí kritérium $h_{ii}>2*\frac{p}{n}$ 
n – počet pozorování, p – počet parametrů regresní funkce.
# Zjištění vlivných bodů
Cookova vzdálenost – míra celkového vlivu i-tého pozorování Pozorování je vlivné, pokud $D_i>\frac{4}{n}$ 
Welschova – Kuhova vzdálenost - Používá se pro upřesnění existence vlivných bodů.
$|DFFITS|>2\sqrt{\frac{p}{n}}$ 

Vybočující hodnoty
Odlehlé hodnoty

vybočující pozorování, které se na ose y výrazně liší od ostatních 
extrémy, které se liší v hodnotách na ose x nebo v jejich kombinaci od ostatních bodů
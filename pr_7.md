## Задача 1
> _Реализовать с помощью математического языка LaTeX нижеприведенную формулу:_

<img width="800" alt="image" src="https://github.com/user-attachments/assets/04bcbd1d-a2b1-4332-863c-f2b16c3f092c">


--
```Latex
\newcommand\myeq{\mathrel{\overset{\makebox[0pt]{\mbox{\normalfont\tiny\sffamily (u=t^{-2m})}}}{=}}}

 \[ \int_{x}^{\infty} \frac{dt}{t(t^2-1)\log t} = \int_{x}^{\infty} \frac{1}{t\log t} (\sum_{m} t^{-2m}) dt = \sum_{m} \int_{x}^{\infty} \frac{t^{-2m}}{t\log t}dt \quad \myeq \quad - \sum_{m} \operatorname{li}(x^{-2m})\]
```

<!--
The latex template is in default.latex.

To render to PDF, install pandoc and latex. Then, run make.
-->
2)  ab.  Diagrams:

    ![Parts a) and b)](2ab.jpg) \clearpage
    
    cd. Diagrams:
    
    ![Parts c) and d)](2cd.jpg) \clearpage

3)  a.  \begin{align*}
            h_{lp}\left(t\right) &= 
                F^{-1}_t\left\{
                    \Pi\left(\frac{w}{2 \pi 1000}\right)
                \right\} \\
            &= \frac{1}{2 \pi} 
                \int^{\infty}_{-\infty} 
                    \Pi\left(\frac{w}{2 \pi 1000}\right) 
                    e^{j w t} 
                dw \\ 
            &= \frac{1}{2 \pi}
                \int^{\pi 1000}_{-\pi 1000} e^{jwt} dw \\ 
            &= \frac{1}{2\pi} 
                \left(\frac{
                    e^{jt 1000 \pi} - 
                    e^{-jt 1000 \pi}
                }{jt}\right) \\
            &= \boxed{
                    \frac{\sin\left(1000 \pi t\right)}{\pi t}
                }
        \end{align*}
    
    b.  \begin{align*}
            h_{win} &= F_w\left\{
                    \Pi\left(\frac{t}{0.004}\right) 
                    h_lp\left(t\right)
                \right\} \\
            &= \frac{1}{2 \pi} 
                F_w\left\{
                    \Pi\left(\frac{t}{0.004}\right)
                \right\} * 
                F_w\left\{
                    h_lp\left(t\right)
                \right\} \\
            &= \frac{1}{2 \pi} 
                \left(\Pi\left(\frac{w}{2 \pi 1000}\right)\right) * 
                \left(\frac{2 \sin\left(0.002 w \right)}{w}\right)
        \end{align*}

5) 
    ##'E' vowel
    
    $T_0 = 385$
    
    ```
    coefficients 0-7:
    [164.35584415584415,
     -472.99458177444677,
     189.82696043665248,
     -464.61698741809909,
     38.723679227233646,
     -14.360894271401728,
     -22.863808995835132]
    [0.0,
     -924.14319160457057,
     350.48167321839838,
     556.23898909631714,
     -21.425665870730082,
     -51.339242244930418,
     45.088399903764099]
    ```
    
    Visually, using 8 coefficients, the results are ok. A lot of the high-frequency content is 
    left out. This adversely affected the audio.
    
    By increasing the number of coefficients to 35, however, I got much
    better results. I chose 35 because the stem plot of coefficients beyond
    the 35th harmonic were close to zero.
    
    ##'O' vowel
    
    $T_0 = 371$
    
    ```
    coefficients 0-7:
    [66.129380053908349,
     -369.56522420390081,
     -178.69427021347292,
     319.1561017793619,
     248.78078634166738,
     246.76795678929508,
     60.394600722349381,
     -109.14107523896631]
    [0.0,
     699.98395654159572,
     -124.13754179002284,
     -788.53833379506273,
     -940.07679757973835,
     29.237006800314976,
     88.21753962123978,
     -51.593393444593303]
    ```
    
    My conclusions for O are the same as for E. With 8 coefficients, the 
    shape is roughly the same, but the high-frequency content is missing.
    Adding more coefficients (interestingly, the same number, 35, as for E)
    encompasses enough bandwidth to produce a recognizable vowel.
    

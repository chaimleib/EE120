<!--
The latex template is in default.latex.

To render to PDF, install pandoc and latex. Then, run make.
-->

1)  a.  The impulse response of the system $y(t) = x(t) + \alpha y(t - T)$ is simply: 
        $$
            h(t) = \sum_{k = 0}^\infty \alpha^k \delta(t - kT)
        $$
    
    b.  The system is BIBO stable if $\int_infty^\infty |h(t)|dt$ is bound. In our case we get that this integral is equal:
        $$
            \int_\infty^\infty \left| 
                \sum_{k = 0}^\infty \alpha^k \delta(t - kT)
            \right| dt
        $$
        
        If $\alpha$ is positive we get that:
        $$
            \sum_{k = 0}^\infty \int_0^\infty \alpha^k \delta(t - kT)dt  = 
                \sum_{k = 0}^\infty \alpha^k
        $$ 
        
        This is bound if $\alpha < 1$ and unbound otherwise. Hence, if $0 \leq \alpha < 1$ the system is BIBO stable, and it is unstable otherwise.
        
    c.  $$
            h(t) = \sum_{k = 0}^\infty \alpha^k \delta(t - kT)
        $$ 
        can also be inverted with the LTI system
        $$
            \boxed{h_1(t) = \delta(t) - \alpha \delta(t - T)}
        $$
        
        We can show this by looking at the properties of the convolution:
        \begin{align*}
            y(t) &= x(t) * h(t) \\
            h_1(t) * y(t) &= h_1(t) * \Big( x(t) * h(t) \Big) \\
            &= \Big( h_1(t) * h(t) \Big) * x(t)
        \end{align*}
        
        Therefore, if $(h_1(t) * h(t)) = \delta(t)$ (which is trivial) we get that 
        $$
            h_1(t) * y(t)  = x(t)
        $$

2)  a.  **[ADD Diagram]**
    
    b.  $$
            \ddot{y}(t) + 300\dot{y}(t) + 2 \times 10^4 y(t) = 10^3 \dot{x}(t)
        $$

        Since $e^{jwt}$ is an eigenfunction for the above LTI system, we get that 
        \begin{align*}
            y(t) &= A_w e^{jwt} \\
            \dot{y}(t) &= A_w (jw) e^{jwt} \\
            \ddot{y}(t) &= A_w (wj)^2 e^{jwt} \\
            \dot{x}(t) &= (jw) e^{jwt}
        \end{align*}
        
        Substituting all of these into the equation yields:
        \begin{align*}
            A_w (jw)^2 e^{jwt} + A_w 300 (jw) e^{jwt} + A_w 2 \times 10^4 e^{jwt} &= 
                10^3 e^{jwt} \\
            e^{jwt} A_w \Big( (jw)^2 + 300(jw) + 10^4 \Big) &= e^{jwt} 10^3
        \end{align*}
        \begin{align*}
            A_w &= \frac{10^3}{-w^2 + 10^4 + 300 w j} \\
                &= \boxed{\frac{10^3 (-w^2 + 10^4 - 300wj)}{ (-w^2 + 10^4)^2 + (300 w)^2}}
        \end{align*}

3)  a.  **[ADD Diagram]**

    b.  $$
            y[n] + 20 y[n - 1] + 1700 y[n - 2] = x[n] + 20x[n-1]
        $$ 
        
        Since $e^{jwn}$ is an eigenfunction for the above LTI system, we get that 
        \begin{align*}
            y[n] &= A_w e^{jwt} \\
            y[n - 1] &= A_w e^{jwn} e^{-jw} \\
            y[n - 2] &= A_w  e^{jwn} e^{-2jw} \\
            x[n] &= e^{jwn}
        \end{align*}
        
        Substituting all of these into the equation yields:
        \begin{align*}
            A_w e^{jwt} + A_w e^{jwt}20  e^{-jw} + A_w e^{jwt} 1700 e{-2jw} &= 
                e^{jwt} + e^{jwt} 20 e^{-jw} \\
            A_w e^{jwt}(1 +  20  e^{-jw} + 1700 e{-2jw}) &=
                e^{jwt}(1 + 20e^{-jw})
        \end{align*}
        $$
            \boxed{A_w = \frac{(1 + 20e^{-jw})}{(1 +  20  e^{-jw} + 1700 e{-2jw})}}
        $$

4)  a. $\Pi(t / 8) * comb(t / 10)$, by examination of the signal, we get that the period is $T_0  = 10$ and the fundamental frequency $\boxed{w_0 = \frac{\pi}{5}}$. We can compute $a_k$ by:

        $$\begin{aligned}
            a_k = 
                10\int_{-4}^{4} e^{-jw_0 k t} dt = 
                10 \frac{1}{-jw_0kt} \left(  e^{-jw_0k4}- e^{jw_0k4}\right) \\
            = \boxed{ \frac{20Sin(4w_0 k)}{10 w_0 k} } 
        \end{aligned}$$

    b.  $\Pi(4t) * comb(t / 10)$, by examination of the signal, we get that the period is $T_0  = 10$ and the fundamental frequency $\boxed{w_0 = \frac{\pi}{5}}$. We can compute $a_k$ by:

        $$\begin{aligned}
            a_k = 
                10 \int_{-\frac{1}{8}}^{\frac{1}{8}} e^{-jw_0 k t} dt  = 
                \frac{10}{-jw_0kt } \left( 
                    e^{-jw_0k\frac{1}{8}}- e^{jw_0k\frac{1}{8}}
                \right) \\
            = \boxed{ \frac{20Sin(\frac{1}{8}w_0 k)}{w_0 k} }
        \end{aligned}$$

    c.  **[TODO]**

5.  a.  **[TODO]** 
    
    b.  **[TODO]**

6.  a.  **[TODO]**
    
    b.  **[TODO]** 
    
    c.  **[TODO]** 
    
    d.  **[TODO]**

<!--
The latex template is in default.latex.

To render to PDF, install pandoc and latex. Then, run make.
-->

1)  a.  The impulse response of the system $y(t) = x(t) + \alpha y(t - T)$ is simply: 
        $$
            h(t) = \sum_{k = 0}^\infty \alpha^k \delta(t - kT)
        $$
    
    b.  The system is BIBO stable if $\int_{-\infty}^\infty |h(t)|dt$ is bound. In our case we get that this integral is equal:
        $$
            \int_{-\infty}^\infty \left| 
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

2)  a.  Starting with the problem
        $$
            \ddot{y}(t) + 300\dot{y}(t) + 2 \times 10^4 y(t) = 10^3 \dot{x}(t)
        $$
        
        we integrate it over time twice to yield
        \begin{align*}
            y(t) + 300\int y(t) dt + 2 \times 10^4 \iint y(t) dt^2 = 10^3 \int x(t) dt \\
            y(t) = 10^3 \int x(t) dt - 300\int y(t) dt - 2 \times 10^4 \iint y(t) dt^2
        \end{align*}
        
        For the diagram, see the attached.
    
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

4)  a.  $$
            \Pi(t / 8) * \text{comb}(t / 10)
        $$

        By examination of the signal, we get that the period is $T_0  = 10$ and the fundamental frequency is $\boxed{w_0 = \frac{\pi}{5}}$. We can compute $a_k$ by:
        \begin{align*}
            a_k &= 10\int_{-4}^{4} e^{-jw_0 k t} dt \\
                &= 10 \frac{1}{-jw_0kt} \left(  e^{-jw_0k4}- e^{jw_0k4}\right) \\
                &= \boxed{ \frac{20\sin(4w_0 k)}{10 w_0 k} }
        \end{align*}

    b.  $$
            \Pi(4t) * \text{comb}(t / 10)
        $$
    
        By examination of the signal, we get that the period is $T_0  = 10$ and the fundamental frequency is $\boxed{w_0 = \frac{\pi}{5}}$. We can compute $a_k$ by:
        \begin{align*}
            a_k &= 10 \int_{-\frac{1}{8}}^{\frac{1}{8}} e^{-jw_0 k t} dt \\
                &= \frac{10}{-jw_0kt } \left(
                    e^{-jw_0k\frac{1}{8}}- e^{jw_0k\frac{1}{8}}
                \right) \\
            &= \boxed{ \frac{20\sin(\frac{1}{8}w_0 k)}{w_0 k} }
        \end{align*}

    c.  $$
            \Big( \Pi(t - 1) * \Pi(t / 2) \Big) * \text{comb}(t / 10)
        $$
    
        By examination of the signal, we get that the period is $T_0 = 10$ and the fundamental frequency is $\boxed{w_0 = \frac{\pi}{5}}$. We can compute $a_k$ by:
        \begin{align*}
            a_k &= 10 \int_{-\frac{1}{2}}^{\frac{5}{2}} e^{-jw_0 k t} \Big( \Pi(t - 1) * \Pi(t / 2) \Big) dt \\
                &=  \int_{-\frac{1}{2}}^{\frac{1}{2}} e^{-jw_0 k t} \left( \frac{1}{2} + t \right) dt \, +
                    \int_{ \frac{1}{2}}^{\frac{3}{2}} e^{-jw_0 k t} dt\, +
                    \int_{ \frac{3}{2}}^{\frac{5}{2}} e^{-jw_0 k t} \left( \frac{5}{2} - t \right) dt
        \end{align*}
        
        $$
            \boxed{a_k = \frac{4 e^{j k w} \sin \left(\frac{k w}{2}\right) \sin (k w)}{k^2 w^2}}
        $$

5.  a.  $$
            a_k = \sum_{n = 0}^{8 - 1} (\delta[n - 1] + \delta[n - 2]) e^{-j n k \frac{2\pi}{8}}
        $$
        
        $$
            \boxed{a_k = e^{-jk\frac{\pi}{4}} + e^{-jk\frac{\pi}{2}}}
        $$
    
    b.  \begin{align*}
            a_k &= \sum_{n = 0}^{32 - 1} (-1)^n ~ e^{-j n k \frac{2\pi}{32}} \\
                &= \sum_{n = 0}^{32 - 1} (-e^{-j k \frac{2\pi}{32}})^n \\
                &= \frac{1 + e^{-jk(32) \frac{2\pi}{32} }}{1 + e^{-jk\frac{2\pi}{32}}}
        \end{align*}
        $$
            \boxed{a_k = \frac{1 + e^{-jk 2\pi}}{1 + e^{-jk\frac{\pi}{16}}}}
        $$

6.  a.  **[TODO]**
    
    b.  **[TODO]** 
    
    c.  **[TODO]** 
    
    d.  **[TODO]**


<!--
The latex template is in default.latex.

To render to PDF, install pandoc and latex. Then, run make.
-->
1)  a.  Radiosurgery

        Input:

        :   radiation beam

        System:

        :   patient

        Output:

        :   effect on patient

        System is partially-known, output is directly measured, input is
        designed

    b.  medical magnetic resonance imaging

        Input:

        :   magnetic beam

        System:

        :   patient

        Output:

        :   resonance measurements

        System is unknown, output is directly measured, input is known

    c.  reflection seismology

        Input:

        :   explosion

        System:

        :   earth

        Output:

        :   pressure wave measurements

        System is unknown, output is directly measured, input is known

    d.  digital camera

        Input:

        :   light from the scene

        System:

        :   CCD sensor

        Output:

        :   digital image

        System is known, output is directly measured, input is unknown

    e.  Facebook user experiments (6/14)

        Input:

        :   news feed stories

        System:

        :   Facebook users

        Output:

        :   tone of subsequent posts from the users

        System is unknown, output is measured, input is designed

2)  See attached sketch.

3)  a.  $\delta_1(t) = \lim_{a \to \infty} \frac{a}{2} e^{-a|t|}$\
        Property \#1\
        $\delta_1(t - t_0) = \lim_{a \to \infty} \frac{a}{2} e^{-a|t - t_0|}$

        Let’s explore two cases $|t - t_0| = 0$ and
        $|t - t_0| = m \neq 0$, in case 1, the limit takes the value of
        $\lim_{a \to \infty} \frac{a}{2} e^{0} = \lim_{a \to \infty} \frac{a}{2}$
        which is clearly non-zero.

        When $|t - t_0| = m \neq 0$ the limit is:
        $$\lim_{a \to \infty} \frac{a}{2} e^{-am} = 
                \lim_{a \to \infty} \frac{\frac{a}{2} }{e^{am}}$$ using
        L’Hopital’s rule we get that: $$=
                \lim_{a \to \infty} \frac{\frac{1}{2} }{me^{am}} = 0$$
        Property \#2
        $$\lim_{a \to \infty} \int_{-\infty}^{\infty}\frac{a}{2} e^{-a|t|}\,dt = 
                \lim_{a \to \infty} \frac{a}{2} 2 \int_{0}^{\infty} e^{-at}\,dt$$
        $$= \lim_{a \to \infty} \frac{1}{a} e^{-at} |_{0}^{\infty}
                = \lim_{a \to \infty} \frac{a}{a}$$ $$= 1$$

    b.  $\delta_2(t) = \lim_{a \to 0} \frac{1}{2a} \Pi(\frac{t - a}{2a})$\
        Property \#1
        $$\delta_2(t - t_0) = \lim_{a \to 0} \frac{1}{2a} \Pi(\frac{(t -t_0) - a}{2a})$$
        By using standard shifting and scaling we can write
        $\Pi(\frac{(t -t_0) - a}{2a})$ piecewise:
        $$\Pi(\frac{(t -t_0) - a}{2a}) = \left\{
                  \begin{array}{lr}
                    1 & : t \in [t_0, t_0 + 2a]\\
                    0 & : t \not\in [t_0, t_0 + 2a]
                  \end{array}
                \right.$$ As the $a \to 0$ the only value that stays
        consistantly non-0 is $t = t_0$ all the other values become
        zero.\
        Property \#2
        $$\lim_{a \to 0} \int_{-\infty}^{\infty}\frac{1}{2a} \Pi(\frac{t - a}{2a})dt = 
                \lim_{a \to 0} \frac{1}{2a} \int_{0}^{2a}dt 
                = \lim_{a \to 0} \frac{2a}{2a}$$ $$= 1$$

4)  a.  $$z \times z^* = (re^{j\theta})(re^{-j\theta}) = r^2 e^{j(\theta - \theta) = r^2}$$

    b.  $$\frac{z}{z^*} = \frac{re^{j\theta}}{re^{-j\theta}} = \frac{r}{r} e^{j (\theta + \theta)} = e^{2j\theta}$$

    c.  $$(z_1 z_2)^* = (r_1 e^{j \theta_1} r_2 e^{j \theta_2})^* = (r_1 r_2 e^{-j(\theta_1 + \theta_2)})^* = r_1 r_2 e^{-j(\theta_1 + \theta_2)}$$
        $$z_1^* z_2^* = (r_1e^{j\theta_1})^* (r_2e^{j\theta_2})^* = (r_1e^{-j\theta_1}) (r_2e^{-j\theta_2})  = r_1 r_2 e^{-j(\theta_1 + \theta_2)}$$
        $$\rightarrow z_1^* z_2^* = (z_1 z_2)^*$$

    d.  $$(\frac{z_1}{z_2})^*  = (\frac{r_1e^{j\theta_1}}{r_2e^{j\theta_2}})^* =   (\frac{r_1}{r_2} e^{j(\theta_1 - \theta_2)})^* =     
                \frac{r_1}{r_2} e^{j(\theta_2 - \theta_1)}$$

        $$\frac{z_1^*}{z_2^*} =
                \frac{r_1 e^{-j\theta_1}}{r_2 e^{-j\theta_2}} = 
                \frac{r_1}{r_2} e^{j(\theta_2 - \theta_1)}$$
        $$\rightarrow
                \frac{z_1^*}{z_2^*} =(\frac{z_1}{z_2})^*$$

5)  a.  $u(t)$ $$Odd = \frac{u(t) - u(-t)}{2}$$
        $$Evem = \frac{u(t) + u(-t)}{2} =  \frac{1}{2}$$

    b.  $Cos(2\pi t)u(t)$
        $$Odd = \frac{Cos(2\pi t)u(t) - Cos(-2\pi t)u(-t)}{2} = \frac{Cos(2\pi t)}{2}(u(t) - u(-t))$$
        $$Even = \frac{Cos(2\pi t)u(t) + Cos(-2\pi t)u(-t)}{2} = \frac{Cos(2\pi t)}{2}(u(t) + u(-t))$$
        $$= \frac{Cos(2\pi t)}{2}$$

6)  a.  $h(t) = e^tu(t)$ is not *BIBO* stable system, an example of a
        bounded input resulting in an unbound output is $x(t) = u(t)$
        which results in the output

        $$\begin{aligned}
                y(t) = h(t) * x(t) = 
                \int_{-\infty}^{\infty} u(\tau)e^{t - \tau}u(t - \tau) \, d\tau \\
                = \int_{0}^{t}e^{t - \tau} \, d\tau 
                = e^t \int_{0}^{t}e^{-\tau} \, d\tau = \\
                = \boxed{e^t (1 - e^{-t})}
                \\
                \end{aligned}$$

        which is an unbound function.

    b.  $h(t) = (t - 1)^2e^{1-t}u(t)$ The system is *BIBO* stable since:

        $$\begin{aligned}
                    y(t) = h(t) * x(t) = 
                    \int_{-\infty}^{\infty} |u(t)e^{1 - t}(t - 1)^2 \, dt \\
                    = e
                \end{aligned}$$

        which is bound, hance the integral is bound.

    c.  $h[n] = u[n - 4]$ is not *BIBO* stable system, an example of a
        bounded input resulting in an unbound output is $x(t) = u(t)$
        which results in the output:

        $$\begin{aligned}
                y[t] = h[t] * x[t] = 
                \sum_{k = -\infty}^{\infty} u[k] u[n - k - 4] = \sum_{k = 0}^{n - 4} 1 \\
                = n - 4 + 1 = \boxed{n - 3}
                \end{aligned}$$

        which is an unbound function. Therefore, the system is not BIBO
        stable

    d.  $Cos[2\pi n] u[n]$ is not *BIBO* stable system, an example of a
        bounded input resulting in an unbound output is $x[n]= u[n]$
        which results in the output

        $$\begin{aligned}
                y[t] = h[t] * x[t] = 
                \sum_{k = -\infty}^{\infty} u[k] u[n - k] 
                = \sum_{k = 0}^{n} 1 
                = \boxed{n +1 }
                \end{aligned}$$

        which is clearly unbound.

    e.  $\sum_{n = -\infty}^{\infty}\delta(t - 2n)$ is not *BIBO* stable
        system, an example of a bounded input resulting in an unbound
        output is $x(t)= u(t)$ which results in the output

        $$\begin{aligned}
                    y(t) = h(t) * x(t) = 
                    \int_{-\infty}^{\infty} u(t - \tau)\sum_{n = -\infty}^{\infty} \delta(\tau - 2n) \, d\tau \\
                    = \int_{-\infty}^{t} \sum_{n = -\infty}^{\infty} \delta(\tau - 2n) \, d\tau = 
                    \sum_{n = -\infty}^{\infty}  \int_{-\infty}^{t} \delta(\tau - 2n) \, d\tau \\
                    = \sum_{n = -\infty}^{\left \lfloor{\frac{t}{2}}\right \rfloor } 1 
                    = \boxed{\infty}
                \end{aligned}$$

        which is clearly unbound

7)  a.  $x(t) = \Pi ( t - 1); h(t) = r(t)$\

        $$\begin{aligned}
            y(t) = x(t) * h(t) = \int_{-\infty}^{\infty} r(\tau) \Pi (t - \tau - 1) \, d\tau \\
            = \int_{(t - 1) - \frac{1}{2}}^{(t - 1) + \frac{1}{2}}r(\tau) d\tau
            = \int_{t - \frac{3}{2}}^{t - \frac{1}{2}}r(\tau) d\tau \\
                   = \left\{
                \begin{array}{lr}
                    \int_{t - \frac{3}{2}}^{t - \frac{1}{2}}\tau d\tau & : t\geq \frac{3}{2} \\
                    \int_{0}^{t - \frac{1}{2}}\tau d\tau & : t \in [\frac{1}{2}, \frac{3}{2})\\
                          0 & : t < \frac{1}{2}
                  \end{array}
            \right. \\
            =
            \boxed{
                    \left\{
                \begin{array}{lr}
                    \frac{(t - \frac{1}{2})^2 - (t - \frac{3}{2})^2}{2} & : t \geq \frac{3}{2} \\
                    \frac{(t - \frac{1}{2})^2}{2} & : t \in [\frac{1}{2}, \frac{3}{2})\\
                          0 & : t < \frac{1}{2}
                  \end{array}
            \right.
            }\end{aligned}$$

    b.  $x(t) = e^{-t}u(t); h(t) = \Pi (t - \frac{1}{2})$\

        $$\begin{aligned}
            y(t) = x(t) * h(t) = \int_{-\infty}^{\infty} e^{-\tau}u(\tau) \Pi (t - \tau - \frac{1}{2}) \, d\tau \\
            = \int_{(t - \frac{1}{2}) - \frac{1}{2}}^{(t - \frac{1}{2}) + \frac{1}{2}}e^\tau u(\tau) d\tau
            = \int_{t - 1}^{t}e^\tau u(\tau)(\tau) d\tau \\
                   = \left\{
                \begin{array}{lr}
                    \int_{t}^{t - 1}e^\tau  d\tau & : t\geq 1 \\
                    \int_{0}^{t}e^\tau d\tau & : t \in [0, 1)\\
                          0 & : t < 0
                  \end{array}
            \right. \\  
            =
            \boxed{
            \begin{array}{lr}
                    e^t - e^{t - 1} & : t\geq 1 \\
                    e^t & : t \in [0, 1)\\
                          0 & : t < 0
             \end{array}
            }\end{aligned}$$

    c.  $x(t) = \sum_{n = -\infty}^{\infty} \delta(t - \frac{1}{2} - n) ; h(t) = \Pi(t)\sin(2\pi t)$\

        $$\begin{aligned}
            y(t) = x(t) * h(t) = \sum_{n = -\infty}^{\infty} \delta(t - \frac{1}{2} - n) * h(t) = 
            \sum_{n = -\infty}^{\infty}h(t - \frac{1}{2} - n) = \\
            \sum_{n = -\infty}^{\infty} \Pi(t - \frac{1}{2} - n)\sin(2\pi (t - \frac{1}{2} - n)) = 
            \sum_{n = -\infty}^{\infty} \Pi(t - \frac{1}{2} - n)\sin(2\pi t - \pi - 2 n \pi ) = \\
            -\sum_{n = -\infty}^{\infty} \Pi(t - \frac{1}{2} - n)\sin(2\pi t) = \\
            \boxed{\sin(2\pi t)}\end{aligned}$$



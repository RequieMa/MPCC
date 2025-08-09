# Dynamic Response

[reference](https://mrce.in/ebooks/Feedback%20Control%20of%20Dynamic%20Systems%208th%20Ed.pdf)

## Convolution and Laplace Transform of LIT
Suppose the input signal to an LTI system is a short pulse as $u_1(t) = p(t)$, and the corresponding output signal is $y_1(t) = h(t)$.

If the input is scaled to $u_1(t) = u(0) p(t)$, then by the scaling property of superposition, the output response will be $y_1(t) = u(0) h(t)$

Also, according to time invariance, if we delay the short pulse signal in time by $\tau$, then the input is of the form $u_2(t) = p(t - \tau)$ and the output response will also be delayed as $y_2(t) = h(t - \tau)$

Any arbitrary input signal $u(t)$ may be approximated by a series of pulses. We define a short pulse $p_{\Delta}(T)$ as a rectangular pulse having unit area such that
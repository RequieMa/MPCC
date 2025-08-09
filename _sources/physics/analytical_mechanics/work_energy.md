# Work Done and Energy

For a single particle moving along a trajectory, $\vec r(t)$, and experiencing a force, $\vec F$, the work done for moving a small step $d \vec r$ is

$$
dW ~=~ \vec F \cdot d\vec r
$$

If we move from $\vec r_1$ to $\vec r_2$, the total work done is 

```{math}
\begin{equation*}
    W_{12} ~=~ \int_{W_1}^{W_2} ~=~ \int_{\vec r_1}^{\vec r_2} \vec F \cdot d \vec r
\end{equation*}
```

$\vec F$ can be any kind of force. When we descibe the work done, we normally say "the work done by the force" or "the work done against the force". 

# Kinetic Energy
If the force is resultant force from Newton's 2nd Law, then

```{math}
\begin{eqnarray*}
    W_{12} ~ &=& ~ \int_{\vec r_1}^{\vec r_2} \vec F \cdot d \vec r\\
    \Rightarrow ~ &=& ~ \int_{\vec t_1}^{\vec t_2} \frac{d \vec p}{dt} \cdot \vec v dt\\
\end{eqnarray*}
```

Applying integration by part,

```{math}
\begin{eqnarray*}
    \Rightarrow W_{12} ~ &=& ~ \left[\vec p \cdot \vec v\right]_{\vec t_1}^{\vec t_2} - \int_{\vec t_1}^{\vec t_2} \frac{d \vec v}{dt} \cdot \vec p dt\\
    \, ~ &=& ~ \left[m \vec v \cdot \vec v\right]_{\vec t_1}^{\vec t_2} - \int_{\vec t_1}^{\vec t_2} \frac{d \vec v}{dt} \cdot \left(m \vec v\right) dt\\
    \, ~ &=& ~ \left[m \vec v \cdot \vec v\right]_{\vec t_1}^{\vec t_2} - \int_{\vec t_1}^{\vec t_2} \frac{d}{dt}  \left(\frac{1}{2} m \vec v \cdot \vec v \right) dt\\
    \, ~ &=& ~ \left[m \vec v \cdot \vec v\right]_{\vec t_1}^{\vec t_2} - \left[ \frac{1}{2} m \vec v \cdot \vec v \right]_{\vec t_1}^{\vec t_2}\\
    \, ~ &=& ~ \left[ \frac{1}{2} m \vec v \cdot \vec v \right]_{\vec t_1}^{\vec t_2}\\
    \, ~ &=& ~ \frac{1}{2} m_2 |\vec v_2|^2 - \frac{1}{2} m_1 |\vec v_1|^2 \\
\end{eqnarray*}
```

We define **Kinetic Energy** as $T = \frac{1}{2} m |\vec v|^2$, then

$$
W_{12} ~=~ T_2 - T_1
$$

which means that **the work done by the resultant force is the change in kinetic energy**.

# Potential Energy
Consider the case

$$
\vec F ~=~ - \vec \nabla V
$$

where $V$ is the **Potential Energy**. Forces which can be written in this form (the gradient of a potential) are called **"Conservative Forces"**.

In Physics, we often abuse the notation (which will make mathematician nuts) and write 

$$
\vec F ~=~ - \frac{\partial V}{\partial \vec r}
$$

Of course, we do that for purpose, 

```{math}
\begin{eqnarray*}
    W_{12} ~ &=& ~ \int_{\vec r_1}^{\vec r_2} \vec F \cdot d \vec r\\
    \Rightarrow ~ &=& ~ \int_{\vec r_1}^{\vec r_2} - \frac{\partial V}{\partial \vec r} \cdot d \vec r\\
\end{eqnarray*}
```

If the potential energy is only a function of displacement (which is almost always the case), $V = V(\vec r)$, then by total differential

$$
dV = \frac{\partial V}{\partial \vec r} \cdot d \vec r
$$

```{math}
\begin{eqnarray*}
    \Rightarrow W_{12} ~ &=& ~ \int_{\vec V_1}^{\vec V_2} - dV\\
    \, ~ &=& ~ \left[ -V \right]_{\vec V_1}^{\vec V_2}\\
    \, ~ &=& ~ V_1 - V_2\\
\end{eqnarray*}
```
which means that **the work done against a conservative force is the change in potential energy**.

Notice that we use "against" here, since normally when we say "change in potential energy" we refer to $V_2 - V_1$ (The difference between the final and the initial).

However, if it is the work done by the conservative force, it assumes the initial potential energy is greater than the final one.

# Conservation of Mechanical Energy

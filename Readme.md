#The Wave Equation 2D


##Discretisation of 2D Wave Equation}

Mathematical model of the wave equation 2-dimension
\begin{equation}
\dd{u}{t} = \gamma^2 \left(\dd{u}{x} + \dd{u}{y}\right) \qquad x\in(a,b)
\end{equation}

This is a time- and space-dependent problem

Introduce a grid in space-time
\begin{align*}
x_i &= (i-1)\Delta x,\qquad i=1,\dots, n\\
y_j &= (j-1)\Delta y,\qquad j=1,\dots, n\\
t_k &= k\cdot \Delta t,\quad \ \ \ \ \quad k=0,1,\dots
\end{align*}




Central difference approximations

\begin{align*}
\dd{u}{x}(x_i,y_j,t_k) &\approx \frac{u_{i-1,j}^k - 2u_{i,j}^k + u_{i+1,j}^k }{\Delta x^2}\\
\dd{u}{y}(x_i,y_j,t_k) &\approx \frac{u_{i,j-1}^k - 2u_{i,j}^k + u_{i,j+1}^k }{\Delta y^2}\\
\dd{u}{t}(x_i,y_j,t_k)&\approx \frac{u_{i,j}^{k-1} - 2u_{i,j}^k + u_{i,j}^{k+1}}{\Delta t^2}
\end{align*}

Assume for the moment that $\lambda\equiv 1$  and that $\Delta x = \Delta y$. Then
\begin{equation}
\frac{u_{i,j}^{k-1} - 2u_{i,j}^k + u_{i,j}^{i+1}}{\Delta t^2} = \frac{u_{i-1,j}^k - 2u_{i,j}^k + u_{i+1,j}^k }{\Delta x^2} + \frac{u_{i,j-1}^k - 2u_{i,j}^k + u_{i,j+1}^k }{\Delta y^2}
\end{equation}

or (with $r=\Delta t/ \Delta x$)
\begin{equation}
u_{i,j}^{k+1} = 2u_{i,j}^k - u_{i,j}^{k-1}  + r^2\left(u_{i-1,j}^k+ u_{i+1,j}^k + u_{i,j-1}^k  + u_{i,j+1}^k - 4u_{i,j}^k\right)
\end{equation}
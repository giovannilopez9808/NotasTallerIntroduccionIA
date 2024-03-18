# Optimización
## Derivada parcial
Calcular la derivada parcial de una función que mapea un vector a un valor escalar ($f: \mathbb{R}^n \rightarrow \mathbb{R}$), corresponde a calcular la derivada de la función respecto a esa variable asuminedo las demás variables son constantes. Esto es:
$$
\large
\frac{\partial f(x_1,x_2,x_3,\dots,x_i,\dots,x_n)}{\partial x_i} \overset{def}{=}\underset{h\rightarrow 0}{lim}\;\; \frac{f(x_1,x_2,x_3,\dots,x_i+h,\dots,x_n)-f(x_1,x_2,x_3,\dots,x_i,\dots,x_n)}{h}
$$
lo cual, se puede escribir de la siguiente manera:
$$
\frac{\partial f(x)}{\partial x_i}  \overset{def}{=}\underset{h\rightarrow 0}{lim}\;\; \frac{f(x+he_i)-f(x)}{h}
$$
donde $x$ es un vector de dimensión $n$ y $e_i$ es un vector unitario, el cual tiene ceros en cada posición excepto en $i$ donde se encuentra un uno.  

## Gradiente y jacobiano
En matemáticas, el gradiente es una generalización de la derivada, ya que la derivada de una función esta definida para unicamente funciones de una variable. El gradiente es una función de valor vectorial. El gradiente esta definido como:
$$
\large
\nabla_f(x) \overset{def}{=} \left(
\begin{matrix}
\frac{\partial f(x)}{\partial x_1} \\\\
\frac{\partial f(x)}{\partial x_2} \\\\
\frac{\partial f(x)}{\partial x_3} \\\\
\vdots \\\\
\frac{\partial f(x)}{\partial x_n}
\end{matrix}
\right)
$$
Con ello, se puede observar que el operador gradiente lleva a una función $n$ variabas variables a un vector de dimensión $n$ donde el elemento i-esimo es la derivada parcial de la función con respecto a la variable $i$. El operador del gradiente se escribe como $\nabla \{\}$ y el vector gradiente como $\nabla_f$   


Por otro lado, si se tiene una función que mapea de un espacio vectorial de dimensión $n$ a un espacio de dimensión $m$ $(f:\mathbb{R}^n \rightarrow \mathbb{R}^m)$, el concepto de derivada no se encuetra definido con el operador gradiente. Es por ello que se necesita definir el concepto del operador jacobiano. La definición del jacobiano es la siguiente:  
Sea $f: \mathbb{R}^n \rightarrow \mathbb{R}^m$, una función cuyas derivadas parciales de primer orden existen en todo $\mathbb{R}^n$ y denotemos como $f_1,f_2,f_3,\dots,f_m$ a sus componentes escalares. Se define la matriz jacobiana de $f$ en un punto $x \in \mathbb{R}^n$ como:
$$
\large
J_f(x) = \left(
\begin{matrix}
\frac{\partial f_1(x)}{\partial x_1} &\frac{\partial f_1(x)}{\partial x_2} & \dots &\frac{\partial f_1(x)}{\partial x_n} \\\\
\frac{\partial f_2(x)}{\partial x_1} &\frac{\partial f_2(x)}{\partial x_2} & \dots &\frac{\partial f_2(x)}{\partial x_n} \\\\
\frac{\partial f_3(x)}{\partial x_1} &\frac{\partial f_3(x)}{\partial x_2} & \dots &\frac{\partial f_3(x)}{\partial x_n} \\\\
\vdots & \vdots & \ddots &\vdots \\\\
\frac{\partial f_m(x)}{\partial x_1} &\frac{\partial f_m(x)}{\partial x_2} & \dots &\frac{\partial f_m(x)}{\partial x_n} \\\\
\end{matrix}
\right)
$$
## Hessiano
La matriz hessiana o hessiano de un campo escalar es una matriz cuadrada de dimensión $n \times n$ que tiene como elementos las derivadas parciales de segundo orden. La matriz hessiana se define como:  

Sea $f: \mathbb{R}^n \rightarrow \mathbb{R}$, un campo escalar cuyas derivadas parciales de segundo grado existen (clase $C^2$). La matriz hessiana de $f$, denotada por $H_f(x)$, es una matriz cuadrada $n \times n$ definida como:
$$
\large
H_f(x) = \left(
\begin{matrix}
\frac{\partial^2 f}{\partial x_1^2} (x) &\frac{\partial^2 f}{\partial x_1 \partial x_2} (x) & \dots & \frac{\partial^2 f}{\partial x_1 \partial x_n} (x) \\\\
\frac{\partial^2 f}{\partial x_2 \partial x_1} (x) &\frac{\partial^2 f}{\partial x_2^2} (x) & \dots & \frac{\partial^2 f}{\partial x_2 \partial x_n} (x) \\\\
\vdots & \vdots & \ddots & \vdots \\\\ 
\frac{\partial^2 f}{\partial x_n \partial x_1} (x) &\frac{\partial^2 f}{\partial x_n \partial x_2} (x) & \dots & \frac{\partial^2 f}{\partial x_n^2} (x) \\\\
\end{matrix}
\right)
$$
Con ello, se afirma que el hessiano es aplicar el operador jacobiano al gradiente de la función $f$.
$$
H_f(x) = J\lbrace \nabla f(x)\rbrace = J\lbrace J_f^T \rbrace
$$
Por otro lado, en algunos casos es más preferible calcular el hessiano por medio del operador gradiente. Para lograr este objetivo se define la operación divergencia el cual es la siguiente:
$$
\nabla \cdot f \overset{def}{=} 1^T\nabla f
$$
Con esto se tiene que el hessiano es calculado como:
$$
\nabla^2 f = \nabla^T \nabla f
$$
## Optimización convexa
## Optimalidad
### Dirección de descenso
### Condición de optimalidad de primer orden
### Condición de optimalidad de segundo orden
#### Condiciones de segundo orden sin restricciones
#### Condición necesaria de segundo orden
#### Condición suficiente de segundo orden

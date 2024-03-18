# **Optimización**

## **Derivada parcial**

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

## **Gradiente y jacobiano**

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

## **Hessiano**

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

## **Convexidad**

### **Conjunto convexo**

Un conjunto $\Omega \subseteq \mathbb{R}^n $ es convexo si
$$
\lambda x +(1-\lambda)y \in \Omega, \forall x,y \in \Omega\;\text{y}\; \lambda\in [0,1]
$$

### **Función convexa**

Una función $f: D\rightarrow\mathbb{R}$ es estrictamente convexa si su dominio $D\subset \mathbb{R}^n$ es convexo, y para todo $x,y \in D$ para todo $\lambda \in [0,1]$, se verifica
$$
f(\lambda x + (1-\lambda)y) \leq \lambda f(x) (1-\lambda) f(x)
$$
Se dice que una función es convexa cuando no se requiere la igualdad de los terminos. Algunos ejemplos de funciones convexas son:
$$
\begin{align}
f(x)&=x^2 & \text{Función cuadratica}\nonumber \\\\
f(x)&=Ax+b & \text{Funciones afines} \nonumber\\\\
f(x)&=||x|| & \text{Cualquier norma de un vextor} \nonumber\\\\
\end{align} \nonumber
$$

### **Funciones convexas diferenciales**

Sea $f: D\rightarrow \mathbb{R}$ diferenciable sobre un dominio convexo y abierto $D$. Entonces, $f$ es convexa si y solo si
$$
f(x) \geq f(\bar{x})+\nabla f(\bar{x})^T (x-\bar{x})
$$
para todo $x,\bar{x} \in D$.

### **Funciones convexas diferenciables dos veces**

Sea $f: D\rightarrow \mathbb{R}$ de clase $C^2$ sobre un dominio convexo y abierto $D$. Entonces, $f$ es convexa si y solo si $H_f(x)$ es semidefinida positiva para todo $x\in D$. Una matriz semidefinida positiva es una matriz hermitiana $M$ cuando se cumple una de las siguientes condiciones:

1. Para todos los vectores no nulos ($x\in \mathbb{R}^n$) tenemos que: $$ x^TMx \geq 0 $$
2. Todos los eigenvalores de $M$ son positivos.
3. La función $$ < x,y > = x^TMy $$
define un producto interno en $\mathbb{R}^n$.
4. Todos los menores principales de $M$ son positivos.

## **Optimalidad**

La optimización convexa trata el problema general de minimizar una función convexa, sobre un conjunto factible también convexo:
$$
\underset{x\in D}{min}\; f(x)
$$
donde $f:D\rightarrow \mathbb{R}$ es convexa y $ D\subset \mathbb{R}^n$ es convexo. En un problema convexo no hay distinción entre mínimos globales y locales. Es por ello que existen diferentes clasificaciones dependiendo de las condiciones que cumplan. Estas clasificaciones son la siguientes:

- *Óptimo global estricto*: $x^* \in \mathbb{R}^n $ es el óptimo global estricto si $f(y)>f(x^*), \forall y \in \mathbb{R}^n$.
- *Óptimo global*: $x^* \in \mathbb{R}^n $ es el óptimo global si $f(y)\geq f(x^*), \forall y \in \mathbb{R}^n$.
- *Óptimo Local Estricto*: $x^* \in \mathbb{R}^n $ es el óptimo local estricto si $f(y)> f(x^*), \forall y \in \Omega$, donde $\Omega$ es una vecindad abierta que contiene a $x^*$.
- *Óptimo Local*: $x^* \in \mathbb{R}^n$ es el óptimo local estricto si $f(y) \geq f(x^*), \forall y \in \Omega$, donde $\Omega$ es una vecindad abierta que contiene a $x^*$.

### **Dirección de descenso**

### **Condición de optimalidad de primer orden**

### **Condición de optimalidad de segundo orden**

#### **Condiciones de segundo orden sin restricciones**

#### **Condición necesaria de segundo orden**

#### **Condición suficiente de segundo orden**

[[Operators]]

Se llama ensemble a un conjunto de sistemas cuánticos, cada uno tenemos al menos 2 estados preparados.
Supongamos que tengo preparado dos estados (estoy en espacio de Hilbert 2 dimensional) dada una base $\{\ket{x},\ket{y}\}$:
$$\begin{aligned}\ket{a}&=\alpha\ket{x}+\beta\ket{y} \\ 
\ket{b}&=\delta\ket{x}+\gamma\ket{y}
\end{aligned}$$
Preparo $n_a$ veces el estado $\ket{a}$ y $n_b$ veces $\ket{b}$, $n_a+n_b=N\Rightarrow\dfrac{n_a}{N}+\dfrac{n_b}{N}=1$.
Luego si seleccionamos aleatoriamente un estado de los preparados tenemos probabilidad $p=\dfrac{n_a}{N}$ de obtener el estado $\ket{a}$ (1-p$ para $\ket{b}$).

**Regla de Born**
La suma de las probabilidades dado el cuadrado de las amplitudes debe sumar:
- A nivel de un único sistema cuántico, la probabilidad el resultado de una medición dada.
- A nivel del ensemble, si tomamos un estado miembro del ensemble hay una probabilidad que el sistema estuviera en un estado o en otro. (Actua como probabilidad clásica)


#### Operador de Densidad de un estado puro
Decimos que $\ket{\psi}$ está en un estado puro si dado una base ortonormal $\{\ket{u_1},\dots,\ket{u_n}\}$ se da:
$$\ket{\psi}=a_1\ket{u_1}+\dots+a_n\ket{u_n}$$
La probabilidad de medir $\ket{u_i}$ es $|a_n|^2$.

El operador de densidad $\rho$ es un operador que mide la media  (estadística).
En el caso de estados puros es el producto externo, primero miramos el [valor medio esperado] de un operador $A$.
$$\begin{aligned}<A> = & \bra{\psi}A\ket{\psi}=(\overline{a_1}\bra{u_1}+\dots+\overline{a_n}\bra{u_n})A(a_1\ket{u_1}+\dots+a_n\ket{u_n})\\= & \sum\limits_{k,l=1}^n \overline{a_k}a_l\bra{u_k}A\ket{u_l} = \sum\limits_{k,l=1}^n \overline{a_k}a_l A_{kl}  \end{aligned}$$
Sabiendo que $a_m=<u_m|\psi>$,$\overline{a_m}=<\psi|u_m>$. Entonces $\overline{a_k}a_l=a_l\overline{a_k}=<u_l|\psi><\psi|u_k>=\bra{u_l}(\ket{\psi}\bra{\psi})\ket{a_k}$.

##### Definición
Llamamos operador de densidad a $\rho = \ket{\psi}\bra{\psi}$, luego $<A>=\sum\limits_{k,l=1}^n \bra{u_l}\rho\ket{a_k} A_{kl}$.
Además por como se ha definido $\rho$ este es una proyección.

#### Operador de densidad para un estado mixto (hay varios estados posibles)
Tengo varios estados $\ket{a},\ket{b}$ en una cierta base (por ejemplo lo que teniamos antes)
Pasos:
- Construir el operador de densidad para cada estado
- Pesarlo (multiplicar) cada operador por la probabilidad de hallar el estado en el assemble
- Sumar todo.
Con dos estados quedaría $\rho=p\rho_a+(1-p)\rho_b$ donde $\rho_i$ es el operador de densidad puro, y p es la probabilidad de hallar $\ket{a}$.

Propiedade de $\rho$:
- Es hermítico $\rho=\rho^\dagger=\overline{\rho}^T$
- $Tr(\rho)=1$
- $\rho$ es un operador positivo, $\bra{\psi}\rho\ket{\psi} \geq 0$, equivale a $\rho$ hermítico con valores propios reales no negativos.

#### Usar $\rho$ para hallar el valor medio de un operador
Sabiendo que $\sum\limits_k \ket{u_k}\bra{u_k}=I$ (relación de clausura) entonces:
$$\begin{aligned}
<A> & = \sum\limits_{k,l=1}^n \bra{u_l}\rho\ket{a_k} \bra{u_k}A\ket{u_l}\\ 
& = \sum\limits_{l=1}^n \bra{u_l}\rho (\sum\limits_k \ket{u_k}\bra{u_k}) A\ket{u_l} \\
& = \sum\limits_{l=1}^n \bra{u_l}\rho A\ket{u_l} = tr(\rho A)
\end{aligned}$$
Y $tr(\rho)=\sum\limits_{l=1}^n \bra{u_l}\rho\ket{u_l}=\sum\limits_{l=1}^n|c_l|^2=1$, por ser $\ket{\psi}$ un estado cuántico.
La traza de la densidad es siempre uno debido a la conservación de la probabilidad.

Si vemos $\rho$ como una matriz, los elementos fuera de la diagonal se les llama coherences (coherencias), $\rho_{n,m}=\bra{u_n}\rho\ket{u_m}$ con  representan la media de los terminos cruzados, mientras que $\rho_{nn}$ representa la probabilidad de hallar el estado $\ket{u_n}$ en el sistema (al medir).
Las coherencias son no nulas en estados puros.

#### Mediciones
Si $M_m$ es un operador de medida que mide un resultado m de un estado, entonces:
$$P(m)=Tr(M_m^\dagger M_m \rho)$$
es la probabilidad de hallar m, y
$$\dfrac{M_m\rho M_m^\dagger}{Tr(M_m^\dagger M_m \rho)}$$
es el operador que indica el estado del sistema tras la medición.

Si en el asemble tomamos uno de sus estados y lo medimos respecto una base por ejemplo $\{\ket{u_0},\ket{u_1}\}$, entonces la probabilidad de que la medición salga el miembro $\ket{u_i}$  es $\bra{u_i}\rho\ket{u_i}$.

#### Caractericación estados mixtos
La coherencia es la capacidad de un estado para influir en otros, esto nos definir estados mixtos y puros cuando tenemos un estado en dimensiones superiores a 2, supuesto $\rho$ en la base que forma al estado.
- Estado mixto, alguna coherencia es nula (no hay coherencia). $\rho_{nm}= 0$ para algún $n\neq m$.
- Un estado es puro en el caso contrario, solo tiene elementos en la diagonal.
El problema se halla que está definición depende de la matriz en la que se represente $\rho$.
Usando que si $\rho$ proviene de un estado puro es una proyección. Entonces $\rho^2=\rho$, luego $Tr(\rho^2)=1$.
Pero si el estado no es mixto, esto no es cierto luego se dará que $Tr(\rho^2) < 1$

##### Estados completamente mixtos
Es un sistema que dado n estados posible puede estar equitativamente en cualquier estado [Entanglement] es decir, la probabilidad de estar en el estado $\ket{u_i}$ es $\frac{1}{n}$. Así pues $\rho=\frac{1}{n}I$ y $Tr(\rho^2)=\frac{1}{n}$.
Estos estados se pueden decir que son los opuestos a los estados puros.



#### Traza parcial y operador de densidad reducido
Se usa en sistemas compuestos, sistemas compuestos por dos o mas sistemas llamados subsistemas. (Viendo el ejemplo un sistema compuesto es el producto tensor al menos otros dos, así que seguiré esa lógica).
Vamos a ver como obtener información de un subsistema teniendo el operador de densidad del sistema completo, obtendremos un nuevo operador que llamaremos operador de densidad reducido (al subsistema).
Supongamos que el sistema compuesto es un estado, producto tensor de n subsistemas (por simplicidad de dimension 2) cada uno con su base $\{u_{1,i},u_{2,i}\}$. El estado se podría escribir como:
$$\ket{\psi}=a_1\ket{u_{1,1}}\otimes\dots\otimes\ket{u_{1,n}}+a_2\ket{u_{2,1}}\otimes\dots\otimes\ket{u_{1,n}}+\dots+a_{2^n}\ket{u_{2,1}}\otimes\dots\otimes\ket{u_{2,n}}$$
Este estado se encuenta en un espacio $2^n$ dimensional, aún pondré los subíndices a las bases de cada subsistemo pero cuando empecemos a usar más la base $\{\ket{0},\ket{1}\}$ el tensor $\ket{0}\otimes\ket{0}$ se denotará como $\ket{00}$. (Ahora mismo hago enfasís que son distintos).
El operador de densidad de este estado es $\rho=\ket{\psi}\bra{\psi}$. 
Supongamos que queremos calcular el operador de densidad del primer subsitema, $\rho_1$, entonces este se define como:
$$\rho_1=Tr_{2,\dots,n}(\rho)=\bra{u_{1,2}}\rho\ket{u_{1,2}}+\bra{u_{2,2}}\rho\ket{u_{2,2}}+\bra{u_{1,3}}\rho\ket{u_{1,3}}+\dots+\bra{u_{2,n}}\rho\ket{u_{2,n}}$$
Y este nuevo estado es el operador de densidad del sistema, verificando todo las propiedades y utilidades del operador de densidad.

#### Operador de densidad y vector de Bloch
![[Bloch Sphere]]

#### Bibliografía
Capítulo 5 [[Quantum_Computing_Explained_David_McMahon.pdf]]
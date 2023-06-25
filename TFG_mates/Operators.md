[[Quantum Computing]],[[Quantum Gates]]

#### Resumen
Para este libro los operators son aplicaciones lineales y bilineales.
- Trata de aplicaciones lineales de un espacio en si mismo (endomorfismos lineales).
- Dice que toda aplicación de esta forma se puede escribir como una matriz que depende de la base usada para escribir la matriz.
- Explica la relación de Clausura.
- Relaciona aplicaciones lineales con producto externo
- Da los operadores (aplicaciones) de Pauli
- Despues define operadores hermitianos y concepto de diagonalización con valores complejos (en espacios 2 dimensionales). De aquí da la descomposición espectral (teorema espectral).
- Traza de un operador y propiedades
- Ya acercándose más a la cuántica da lo que es el valor esperado (Expectation Value of an Operator).
- Después da la serie de Tailor o "función" de un operador
- Proyecciones
- Operadores positivos, es decir aplicaciones bilineales semidefinidas positivas
- Defina la conmutación de dos aplicaciones lineales.
- Principio de incertidumbre de Heisemberg
- Definir los postulados de la mécanica Cuántica con operadores.

#### Definición
Se denotan $\hat{A}$ aunque si no hay confusión se denotará simplemente en mayúscula $A$, y son aplicaciones que transforman un elemento de un tipo (función,vector...) en otro elemento pero del mismo tipo (cambia los elementos pero mantiene la estructura). Por ejemplo un operador puede ser una aplicación que transforma un ket, $\ket{v}$ en otro ket o un bra, $\bra{v}$ en otro bra.

Nos interesan los operadores lineales de un espacio en si mismo, es decir endomorfismos. Centrandonos en espaciones vectoriales complejos 2 dimensionales.

#### Producto externo
Es el producto entre, $\ket{v}\bra{w}$. Esto forma aplicación lineal (es una matriz luego se puede ver como una aplicación lineal). En más detalle aplicandolo a $\ket{x}$:
$$\ket{v}\bra{w}(\ket{x})=\ket{v}(\bra{w}\ket{x})=\ket{v}<w|x>=<w|x>\ket{v}$$

Como $<w|x>$ es un número complejo, está aplicación transforma un $\ket{x}$ en una paralelo a $\ket{v}$. Es una proyección al subespacio vectorial generado por $\ket{v}$.

#### Relación de Clausura
Dada una base en el espacio vectorial, $\{\ket{u_1},\dots,\ket{u_n}\}$, se verifica:
$\sum\limits_{i=1}^n \ket{u_i}\bra{u_i}=\hat{I}$  (la forma más sencilla de probar esto es usando la representación matricial)
Luego con con los qubits podemos escribir, $I=\ket{0}\bra{0}+\ket{1}\bra{1}$

#### Matrices y Aplicaciones lineales
Dada una aplicación lineal y una base puedo dar una matriz que representa a la aplicación en esa base. Y dada una matriz y una base puede tener una aplicación lineal.
Luego varias matrices pueden representar al mismo operador pero en distintas bases.
La dimensión dependerá de los espacios que intervienen en la aplicación.
Con esto se ve que el producto externo genera una matriz y por tanto induce una aplicación lineal. 
Podemos calcular los coeficientes de la matriz $A$ dada una base $\{\ket{u_1},\dots,\ket{u_n}\}$ como, $a_{ij}=\bra{u_i}A\ket{u_j}$, fila i-esima, columna j-esima.

Para los qubits las matrices serán $2\times2$ y con coeficientes complejos.

#### Operadores (Transformaciones) de Pauli
![[Operadores de Pauli]]


##### NOTA IMPORTANTE
En la propia bibliografía al da 2 expresiones de Y, primero da la que he puesto arriba y luego cuando hace la expresión matricial usa $Y\ket{0}=i\ket{1}$ , $Y\ket{1}=-i\ket{0}$. Hasta no ver aplicaciones más tarde no voy a decantarme por una sobre la otra.

#### Operadores normales, hermíticos y normales
Los operadores hermíticos y los unitarios son importantes para la física cuántica y por tanto para la computación cuántica.
Dado un operador $\hat{A}$ se define su adjunto hermítico (hermitian adjoint),$\hat{A}^\dagger$, como:
$$\bra{a}\hat{A}^\dagger\ket{b}=\overline{\bra{b}\hat{A}\ket{a}}$$
Computacionalmente se realiza, se toma el conjugado de todas las constantes ( $(a\hat{A})^\dagger = \overline{a}\hat{A}^\dagger$ ), si se aplica a un bra se transforma en un ket y viceversa ( $(\ket{v})^\dagger=\bra{v}$ ) y hago un reflejo a todo ( $(\hat{A}\hat{B})^\dagger=\hat{B}^\dagger\hat{A}^\dagger$ ,  $(\bra{v}\hat{A}\hat{B})^\dagger=\hat{B}^\dagger\hat{A}^\dagger\ket{v}$. Además al adjunto de la suma es la suma de los adjuntos.

Dado esto, se define:
- $\hat{A}$ es un operador hermítico si verifica, $\hat{A}=\hat{A}^\dagger$ (ejemplo los opradores de Pauli, las transformaciones hermíticas tienen en la diagonal valores reales )
- $\hat{A}$ es un operador unitario si verifica, $\hat{A}\hat{A}^\dagger=\hat{A}^\dagger\hat{A}=\hat{I}$ (ejemplo los operadores de Pauli)
- $\hat{A}$ es un operador normal si verifica, $\hat{A}\hat{A}^\dagger = \hat{A}^\dagger\hat{A}$ , (ejemplos los operadores hermíticos y los operadores unitarios)

#### Valores propios y vectores propios (eigenvalues and eigenvectors)
Dado un vector $\ket{v}$, se dice que es un vector propio (eigen vector) de una aplicación lineal A si existe un $\lambda \in \mathbb{C}$ verificando:
$$A\ket{v}=\lambda\ket{v}$$
Si $\ket{v}\neq 0$, a $\lambda$ se le llama valor propio del operador A.
Para hallar los valores y vectores propios de un operador usamos la **ecuación característica**
##### Ecuación característica
Dado un operador $A$ se define su ecuación característica como:
$$det|A-\lambda I| = 0$$
Los valores de $\lambda$ que sean solución de la ecuación son los valores propios de $A$.
Una vez se tienen los valores propios, hallamos las vectores propios de $A$, esto es resolviendo:
$$A\ket{v}=\lambda\ket{v}$$
De esta forma obtenemos el subespacio asociado al vector propio.
([Calcular valores y vectores propios] vectoriales)
En computación cuántica nos interesa que el vector propio sea unitario (porque los qubits son vectores unitarios), así que dado uno no  nulo lo normalizamos (si $\ket{v}$ es un vector propio entonces $a\ket{v}$ es un vector propio $\forall a \in \mathbb{C}$).
#####
Si cada vector propio está asociado a un único valor propio decimos que son no degenerado. Y si dos o más vectores propios son degenerados significa que corresponde al mismo valor propio.

Los valores propios de un operador hermítico son reales y los vecotres propios asociados son ortogonales entre sí.
Si un operador es unitario, sus valores propios tienen modulo 1 y si sus vectores no degenerados son ortogonales entre sí.
([Teorema Espectral])
Dado un operador que verifique el Teorema Espectral, entonces existe una base $\{\ket{u_1},\dots,\ket{u_n}\}$ donde su representación matricial es una matriz diagonal con coeficientes sus valores propios asociados $\{\lambda_1,\dots,\lambda_n\}$. Y podemos escribir A como:
$$A=\sum\limits_{i=1}^n\lambda_i\ket{u_i}\bra{u_i}$$

#### Traza
La traza de un operador es dada cualquier representación matricial suya, es la traza de la matriz (la suma de suma de los elementos de la diagonal). Este número es invariante respecto a la base que se escoja. Una forma de calcularla es dada una base $\{\ket{u_1},\dots,\ket{u_n}\}$:
$$Tr(A)=\sum\limits_{i=1}^n\bra{u_i}A\ket{u_i}$$
##### Propiedades
- Cíclica, $Tr(ABC)=Tr(CAB)=Tr(BCA)$
- La traza del producto externo es el producto interno, $Tr(\ket{v}\bra{w})=<w|v>$
- Extendiendo lo anterior $Tr(A\ket{v}\bra{w})=\bra{w}A\ket{v}$
- La traza no depende de la base
- Si A es diagonalizable (se puede escribir en alguna base como una matriz diagonal que serían sus valores propios), la traza de A es la suma de sus valores propios
- La traza es lineal



#### Valor Medio Esperado de un Operador
Se define el valor medio esperado de un operador es la media o valor medio del operador respecto a un estado cuántico dado $\ket{v}$ . Esto corresponde al valor medio de veces que medimos $A\ket{v}$ si partimos de  $\ket{v}$ si lo repetimos muchas veces. Se define:
$$<A>=\bra{v}A\ket{v}$$
A partir de esto podemos definir la desviación típica o incertidumbre del operador como:
$$\Delta A = \sqrt{<A^2> - <A>^2}$$

RESPASAR SIGNIFICADO

#### Funciones de operadores
Supongamos $f$ una función de $f:\mathbb{C}\longrightarrow\mathbb{C}$, f holomorfa (supongo que se puede debilitar...) en un entorno del 0. Entonces f se puede escribr en un entorno del 0 como:
$$f(z)=\sum\limits_{i=0}^\infty a_n z^n$$
Como en el espacio de las matrices cuadradas complejas tenemos un algebra cerrada, y ademas podemos inducir una norma (a partir de la norma que hay en $\mathbb{C}$. Entonces tiene sentido hablar de (se puede mirar si siempre tiene sentido o no):
$$f(A)=\sum\limits_{i=0}^\infty a_n A^n$$
Donde $A \in \mathbb{C}^{n \times n}$ . ($A^0=I$)

Tomando la versión matricial de los operadores podemos definir la función de un operador.


Si A es un operador unitario y diagonalizable (admite una expansión espectral), entonces si $A=\sum\limits_{i=1}^n\lambda_i\ket{u_i}\bra{u_i}$ $$f(A)=\sum\limits_{i=1}^nf(\lambda_i)\ket{u_i}\bra{u_i}$$
Demostración:
Lo haré para el caso de n=2, el resto es análogo.
- Por definición $f(A)=\sum\limits_{i=0}^\infty a_n A^n$
- Como A es diagonaliazble $f(A)=\sum\limits_{i=0}^\infty a_n \begin{pmatrix} \lambda_1^n & 0 \\ 0 & \lambda_2^n\end{pmatrix}$ 
- Separando, $f(A)=\sum\limits_{i=0}^\infty a_n\lambda_1^n \begin{pmatrix} 1 & 0 \\ 0 & 0\end{pmatrix} + a_n\lambda_2^n \begin{pmatrix} 0 & 0 \\ 0 & 1\end{pmatrix}$
- Como f admite desarrollo de taylor, $f(\lambda_j)=\sum\limits_{i=0}^\infty a_n\lambda_j^n$
- Se da que, $f(\lambda_1)\begin{pmatrix} 1 & 0 \\ 0 & 0\end{pmatrix} = \sum\limits_{i=0}^\infty a_n\lambda_1^n\begin{pmatrix} 1 & 0 \\ 0 & 0\end{pmatrix}$, $f(\lambda_2)\begin{pmatrix} 0 & 0 \\ 0 & 1\end{pmatrix} = \sum\limits_{i=0}^\infty a_n\lambda_2^n\begin{pmatrix} 0 & 0 \\ 0 & 1\end{pmatrix}$
- Escribiendo $A_1=\begin{pmatrix} 1 & 0 \\ 0 & 0\end{pmatrix}$,$A_2=\begin{pmatrix} 0 & 0 \\ 0 & 1\end{pmatrix}$
- Como ambos limites existian por separado, puedo escribir $f(A)=\sum\limits_{i=1}^2 f(\lambda_i)A_i$ 
$\blacksquare$

Sea H un operador hermítico entonces $U=e^{i\epsilon H}$, donde $\epsilon$ es un escalar, es unitaria. H siempre es diagonalizable (por ser hermítico), luego $U=\sum\limits_ie^{i\epsilon\lambda_i}\ket{u_i}\bra{u_i}$
Tomando los primeros terminos de serie de Taylor de U (no la que tenemos indicada) obtenemos lo que se llama transformación unitaria infinitesimal:
$$I+i\epsilon H$$
#### Transformaciones unitarias
Cambios de base de una aplicación lineal

#### Proyecciones
Son hérmeticas, se pueden escribir como $\ket{v}\bra{v}$, las proyecciones conmutan entre sí.
Dado una matriz diagonalizable, la puedo escribir como suma de proyecciones una para cada subespacio propio. La probabilidad de medir un estado en una de esas poryecciones es el autovalor asociado al subespacio.


#### Operadores semidefinidos positivos
$\hat{A}$ es semidefinida positiva si: $\bra{v}A\ket{v}\geq 0 \ \ \forall\ket{v}\in\mathbb{C}^n$
Se define un tipo específico de operador llamado valor medido de un operador positivo (positive operator valued measure, POVM) como un conjunto de operadores semidefinidos positivos $\{E_1,\dots,E_n\}$ verificando $\sum\limits_i E_i=I$
#### Álgebra de Conmutadores
Se define el conmutador de dos aplicaciones lineales,$A,B$ como $[A,B]=AB-BA$
Si $[A,B]=0$ se dirá que los operadores conmutan y diremos que son incompatibles si no conmutan.
Propiedades: lineal, antisimétrico y distributivo.
El anticonmutador de dos aplicaciones es $\{A,B\}=AB+BA$
#### Bibliografía
- Capítulo 3 [[Quantum_Computing_Explained_David_McMahon.pdf]]
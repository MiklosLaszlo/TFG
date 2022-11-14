#### Definición 
Un espacio vectorial es una tupla (V,K), donde V es el espacio vectorial y K es un cuerpo.
Cumplen los axiomas:
Si $v,w,s \in V$ entonces:
- $v + w \in V$
- $v + w = w +v$
- $(v + w) + s = v + (w + s)$
- Existe un elemento en V, llamado $0\in V$ tal que $\forall v \in V$ $v + 0 = 0 + v = v$
- $\forall v \in V \exists -v \in V$ tal que $v + (-v) = 0$
Si $v,w\in V$, $a,b \in K$, entonces:
- $av \in V$
- $av=va$
- $a(bv)=(ab)v$
- $(a+b)v=av+bv$
- $(v + w)a= va + wa$

Para computación cuántica, los estados de uno o varios qubits se formalizan matemáticamente en un espacio vectorial complejo.

#### Base y Dimensión
Un conjunto de vectores $\{v_i:i\in I\}$  se dice que es una base de V, si todo vector v de V se puede escribir como combinación lineal finita de vectores de la base.
La dimensión de V se define como el número de elementos de una de sus bases.
Si la base es finita, con n elementos $dim(V)=n$. Y además todas sus bases tienen el mismo nñumero de elementos.
Si la base no es finita, $dim(V)=\infty$. Y todas las bases no son finitas.

Nosotros vamos a trabajar en dimensiones finitas, salvo que se indique lo contrario se va a suponer que la dimensión del espacio es finita.

#### Producto escalar (interno)
Es una aplicación de $V\times V:\longrightarrow K$, en nuestro caso $K = \mathbb{C}$ , llamamos al producto $< | >$. Y tiene que verificar las siguientes propiedades:
- $<v|v> \ \geq  \ 0$ y $<v|v> \ = \ 0 \ \Leftrightarrow v=0$ 
- $<u|v> \ = \ \overline{<v|u>}$  si $V$ tiene más de una dim, es el conjugado componente a componente.
- $<u|av + bw> \ = \ a<u|v> + b<u|w>$, es lineal en la segunda componente.
- $<au+bv|w> \ = \ \overline{a}<u|w> + \overline{b}<v|w>$, es antilineal en la primera componente.

Con la linealidad y antilinealidad podemos solo tomar una, ya que la otra se podría deducir del resto de propiedades.

Un producto escalar es: $<u|v> = \overline{u}^T \ v$ , este es el producto escalar usual y es el que se usará normalmente. Con este producto obtenemos un [espacio de Hilbert].
De hay que en computación cuántica se usa la sugestiva notación de $\overline{u}^T=\bra{u}$, también se le llama [Hermitian conjugate].

Se define la norma de un vector como: $\lVert v \rVert = \sqrt{<v|v>}$.

Dos vectores $v,u$ son ortogonales si $<v|u> = 0$, denotándolo $v\perp u$.

Un vector $v$ está normalizado o es unitario si $<v|v> = 0$

Dado un conjunto de vectores, es ortonormal si son unitarios y ortogonales dos a dos.

En cualquier espacio (dimensión finita) con un producto escalar puedo encontrar una base ortonormal (usando el [método de Grand-Schmidt]).

Teniendo un producto escalar induzco una norma. Entonces se verifica la desigualdad de Cauchy-Schwartz y la desigualdad triangular.

#### Bibliografía

Capitulo 2 de [[Quantum_Computing_Explained_David_McMahon.pdf]]



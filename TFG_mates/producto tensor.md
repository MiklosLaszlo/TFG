#### Espacios Vectoriales
Hay muchas formas de definir el producto tensor entre dos espacios vectorial $V$ y $W$ sobre un mismo cuerpo K, la que voy a dar es la  que se usa por espacio cociente porque se puede extender a anillos. Despues pondre como calcularlo a partir de bases porque es más eficiente (nota, si se cambia las bases el espacio resultante es isomorfo al primero haciendo un cambio de bases).

##### Definición Cociente
Sea L el espacio vectorial que tiene como base el producto cartesiano $V \times W$. Una forma de ver este espacio es la siguiente, L es el espacio de todas las funciones que verifican lo siguiente $f \in L \Leftrightarrow f:V \times W \longrightarrow K$ donde f tiene un número finito de valores no nulos.
Entonces f se puede poner como combinación lineal finita de elementos de la base. Si f tiene el valor a en (v,w) entonces f se le pone a para combinación lineal con (v,w). Como solo hay un número finito de valores no nulos la combinación para dar f es finita.
A continuación se defina el subespacio vectorial R en L, donde en R se verifica:
$$(v_1 + v_2, w) = (v_1,w) + (v_2,w)$$
$$(v, w_1 + w_2) = (v,w_1) + (v,w_2)$$
$$(sv,w) = s(v,w)$$
$$(v,sw) = s(v,w)$$
Donde $v,v_1,v_2 \in V \ , \ w,w_1,w_2 \in W \ , \ s\in F$. (Literalmente R es el espacio vectorial resultante de hacer el producto cartesiano).
Finalmente el producto tensor se define como el espacio cociente:
$$V \otimes W = L/R$$
y la imagen $(v,w)$ se denota como $v\otimes w$

Cabe destacar que $v\otimes w = w\otimes v$ si $w,v$ pertenecen al mismo espacio (para poder intercambiarlos).

**Definición Bases**
Sea $B_V$ una base de $V$ y $B_W$ una base de $W$. Entonces una base de $V\otimes W$ es $\{v\otimes w: v\in B_V, w\in B_W\}$, donde $\otimes$ es el producto externo entre $v$ y $w$.
Finalmente si $x = \underset{b\in B_V}{\sum} x_b b$ , $y = \underset{c\in B_W}{\sum} y_c c$, entonces $x\otimes y = \underset{b\in B_V}{\sum} x_b b \otimes \underset{c\in B_W}{\sum} y_c c =  \underset{b\in B_V}{\sum}\underset{c\in B_W}{\sum} x_b y_c b\otimes c$ 

**Propiedades**
- Si $V$ y $W$ tienen dimensión finita, entonces $dimV\otimes W = dimV * dimW$ 

#### Aplicaciones Lineales
Dada dos aplicaciones lineales $A,B:V\longrightarrow W$ se define su producto tensor como:
$$A\otimes B(w)=A(w)\otimes B(w)$$
Es el tensor de las imágenes. Da lugar a una aplicación lineal por la bilinealidad del tensor.
Además:
- Si A,B son herméticas (unitarios, proyecciones, definidas positivas) entonces tambien lo es hermético (unitario, proyección, definido positivo)

#### Espacios de Hilbert
Si $H_1,H_2$ son espacios de Hilbert entonces su $H_1\otimes H_2$ es un espacio de Hilbert con producto escalar: $v,w\in H_1\otimes H_2 \Rightarrow v=v_1\otimes v_2 , w=w_1 \otimes w_2 \ \ v_1,w_1 \in H_1 \ \ v_2,w_2 \in H_2$. 
$$<v,w> = <v_1,v_2><w_1,w_2>$$
#### Cálculo práctico
- Si $v=\begin{pmatrix} v_1 \\ v_2 \end{pmatrix},w=\begin{pmatrix} w_1 \\ w_2 \end{pmatrix}$ entonces $v\otimes w = \begin{pmatrix} v_1w_1 \\ v_1w_2 \\ v_2w_1 \\ v_2w_2   \end{pmatrix}$
- Si $V=\begin{pmatrix} v_1 & v_2 \\ v_3 & v_4 \end{pmatrix},W=\begin{pmatrix} w_1 & w_2 \\ w_3 & w_4 \end{pmatrix}$ entonces: $V\otimes W=\begin{pmatrix} v_1W & v_2W \\ v_3W & v_4W \end{pmatrix} = \begin{pmatrix} v_1w_1 & v_1w_2 & v_2w_1 & v_2w_2 \\ v_1w_3 & v_1w_4 & v_2w_3 & v_2w_4 \\ v_3w_1 & v_3w_2 & v_4w_1 & v_4w_2 \\ v_3w_3 & v_3w_4 & v_4w_3 & v_4w_4 \end{pmatrix}$

#### Relación con la computación cuántica
A la hora de estudiar n qubits juntos estos se viven en el productor tensor de sus respectivos espacios. Además dado puertas cuánticas (isomorfismos lineales) para p y q qubits puedo definir otra para n qubits como el producto tensor


#### Bibliografía
- Capitulo 4 de [[Quantum_Computing_Explained_David_McMahon.pdf]]
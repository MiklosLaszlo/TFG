Para la computación cuántica se usa un número finito de sistemas cuánticos.
Un sistema cuántico es un espacio vectorial complejo de dimensión finita con un producto escalar. Por tanto estado (cuántico) y las transformaciones asociadas se podrán describir como vectores y matrices (aplicaciones lineales o bilineales si se da el caso).

A cada vector $\{v_1, v_2, v_3,\dots , v_n\}$ de una base se le denota por $\ket{v_i}$ (mirar cambiar el simbolo > por otro mas adecuado). Y al conjuguado transpuesto (recuerdo que es una base compleja) se le denota $\bra{v_i}$, solo estaria en 2D en principio.... (Es decir, esto es, si tengo $\ket{x}=(1,1)^T$ entonces $(1,-1)=\bra{x}$ )
Normalmente se trabajara en un espacio 2-dimensional (a nivel expositivo), donde la base sera $\{(1,0)^T,(0,1)^T\}$ (otra vez un numero complejo se puede ver como un par de numeros reales), que se denotarán respectivamente por $\ket{1}$, $\ket{0}$.
El producto escalar de dos vectores $\bra x$ e $\ket{y}$, se denotara por $\braket{x|y}$, que es directamente multiplicar $\braket{x||y} = (a_x,-b_x)*(a_y,b_y)^T$.
Análogamente se tiene el producto externo, que seria $\ket{x}\bra y=(a_x,b_x)^T*(a_y,-b_y)$.
Estas notaciones se reducen a multiplicar matrices de distintas dimensiones.

Usando estas notaciones se pueden expresar transformaciones de los estados cuanticos (aplicaciones lineales aplicadas a vectores), en función de la base dando una matriz.
Como ejemplo la matriz: $X =\ket 0 \bra 1+\ket 1 \bra 0$ , denota a intercambiar los vecotres de la base usual. Por comodidad (al ser una aplicacion lineal), se indican a que vectores van a parar los de la base, en este caso, X ( $\ket 0$) = $\ket 1$, X ( $\ket 1$) = $\ket 0$.

Dicho esto el [[Qubit]] es un vector unitario de dimensión 2.
Varios Qubit se pueden juntar usando el producto tensorial.



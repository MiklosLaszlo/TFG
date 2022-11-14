Ocurre cuando trabjamos al menos con dos qubits. Varios qubits estan en el producto tensor de los espacios de donde provienen y tienen modulo 1 (suspicious).
Se dice que un estado de varios qubits está entrelazado cuando no puedo descomponer dicho estado en estados de cada uno de sus qubits compenentes de forma que el producto tensor de los estados en cada qubit me de el estado en comun. Un ejemplo de un estado entrelazado con 2 qubits es $\frac{1}{\sqrt 2}(\ket {00} + \ket {11})$. Por lo siguiente:
$(a_1\ket 0 + b_1\ket 1) \otimes (a_2 \ket 0 + b_2 \ket 1) = a_1a_2 \ket{00} + a_1b_2\ket{01} + b_1a_2 \ket{10} + b_1b_2\ket{00} = \ket {00} + \ket {11}$
Por tanto $a_1b_2=0$, que implica $a_1=0$ ó $b_2=0$, y en ambos casos es imposible que se de la 
última igualdad.
Ahora un estado con dos qbits que no está entrelazado es $\frac{1}{\sqrt 2}(\ket {00} + \ket {01}) = \ket {0} \otimes \frac{1}{\sqrt 2}(\ket 0 + \ket {1} )$

Otra forma de ver si un estado está entrelazado es cuando la medicion de un conjunto de qubits afecta a la posterior medición de otro conjunto de qubits. Como ejemplo pongamos el estado $\frac{1}{\sqrt 2}(\ket {00} + \ket {11})$.
La probabilidad de medir $\ket 0$ es $\frac{1}{2}$ si no se ha medido el segundo qubit, ahora si medimos el segundo qubit la probabilidad de medir $\ket 0$ es 0 o 1, dependiendo de si se ha medido $\ket 1$ o $\ket 0$ en el segundo qubit respectivamente (esto es porque si mide $\ket 1$ nos quedamos solo con $\ket {11}$ y si mide $\ket 0$ tenemos $\ket {00}$).

En cambio con $\frac{1}{\sqrt 2}(\ket {00} + \ket {01})$, esto no pasa si medimos el primer qubit tenemos la probabilidad $1$ de medir $\ket 0$, si medimos primero el segundo sea cual sea la medición lo que nos quedaría sería $\ket {00}$ ó $\ket {01}$ y si medimos el primer qubit nos volvera a salir $\ket 0$ siempre.
De forma analoga se puede ver que medir primero el primer qubit no afecta a la probabilidad de la medición del segundo qubit.

#### Bibliografía
- [[Resumen.pdf]]
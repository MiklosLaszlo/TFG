Es un vector unitario en un [[Espacio vectorial]] complejo 2-dimensional, en el que se ha fijado una base (ordenada) $\{\ket{0},\ket{1}\}$. Normalmente dicha base es la $\{(1,0)^T,(0,1)^T\}$ (tambien se puede denotar como $\{\ket{\uparrow},\ket{\rightarrow}\}$), es importante preestablecer está base porque es con la que se va a medir. Si el qbit no es ni $\ket{0}$ ni $\ket{1}$, se dice que está en un estado de superposición.

El motivo por el que a las bases se denotan $\ket 0, \ket 1$ es por tradición al bit clásico.

Una notación importante es que si el qubit $x=a\ket{0} + b\ket{1}$, (donde $|a|^2 + |b|^2 = 1$) entonces la probabilidad de medir x según el vector de la base $\ket{0}$ es $|a|^2$ y el de medirlo con $\ket{1}$ seria $|b|^2$.

Cuando se mide un qubit se pierde información porque solo lo podemos medir en una de las coordenadas (en general solo en la dirección de un vector) y perdemos información de la otra.
Además no es posible clonar el qubit sin alterarlo para hacer dos mediciones (usando [[Quantum Gates]] se explica).

Si tenemos varios qubits, cada uno en un su espacio vectorial complejo 2D tomemos que son el mismo y con la misma base. Entonces podemos ver todos estos qubits como un vector en el espacio vectorial resultante de hacer el [[producto tensor]]ial de todos los espacios vectoriales.
Esto supone un incremento exponencial de combinaciones con un crecimiento lineal de espacio.
[[Qubitvsbit]].
Volviendo si tenemos dos qbits, el espacio vectorial en el que tabajamos tiene como base $\{\ket 0 \otimes \ket 0, \ket 0 \otimes \ket 1 , \ket 1 \otimes \ket 0 , \ket 1 \otimes \ket 1\}$ que de forma compacta se escribe como $\{\ket {00} , \ket {01}, \ket {10} , \ket {11}\}$.
Así pues con tres qubits, la base sería $\{\ket{000},\ket{001},\ket{010},\ket{011}, \ket{100}, \ket{101}, \ket{110}, \ket{111}\}$.

Finalmente, hay estados cuando se usan mas de un qubit que no se pueden representar conociendo las coordenadas de cada qubit por separado. Por ejemplo sea el estado de dos qubit $\ket {00} + \ket {11}$, supongamos que lo podemos expresar en sus bases originales y haciendo el producto tensor, es decir, existen $a_1,a_2,b_1,b_2$ tales que:
$(a_1\ket 0 + b_1\ket 1) \otimes (a_2 \ket 0 + b_2 \ket 1) = a_1a_2 \ket{00} + a_1b_2\ket{01} + b_1a_2 \ket{10} + b_1b_2\ket{11} = \ket {00} + \ket {11}$
Por tanto $a_1b_2=0$, que implica $a_1=0$ ó $b_2=0$, y en ambos casos es imposible que se de la 
última igualdad.

Los estados que no pueden ser descompuestos como el porducto tensor de las bases de los qubits se dice que están entrelazados ([[Entanglement (Entrelazado)]]). Estos estados no tienen contraparte clásica.

Ahora supongamos que queremos medir k qubits de un conjunto de n qubits. El proceso a seguir es: la maquina descompone el espacio $L$ donde viven los n qubits en $2^k$ subespacios ortogonales entre si de forma que el producto cartesiano de estos subespacios me da $L$, estos espacios son todas las combinaciones de los k qubits que queremos medir. Cada uno de estos subespacios tiene una probabilidad y una lectura asociada, la maquina selecciona uno de esos subespacios con dicha probabilidad y devuelve la lectura, nota esto hace que se pierda la información de todos los demás qubits ya que la maquina proyecta nuestro estado original en el subespacio leido.

Como ejemplo si quiero medir los dos primeros qbits en tres qbits sería:
En general tengo el estado que seria de la forma: 
$a^2+b^2+c^2+d^2+e^2+f^2+g^2+h^2=1$
$a\ket{000} + b\ket{001} + c\ket{010} + d\ket{011} + e\ket{100} + f\ket{101}+ g\ket{110}+h\ket{111}$
Como quiero medir los dos primeros qbits, son $4$ subespacios. Separo esta combinación en dicho subespacios:
$\ket{00} \otimes (a\ket 0 + b\ket 1) + \ket{01}\otimes(c\ket0 + d\ket1) + \ket{10}\otimes(e \ket0 + f\ket{1})+ \ket{11}\otimes(g\ket 0 +h \ket{1})$ 
Tomando $m_1 = \sqrt{|a|^2+|b|^2},m_2 = \sqrt{|c|^2+|d|^2},m_3 = \sqrt{|e|^2+|f|^2},m_4 = \sqrt{|g|^2+|h|^2}$
$m_1\ket{00} \otimes (\frac{a}{m_1}\ket 0 + \frac{b}{m_1}\ket 1) + m_2\ket{01}\otimes(\frac{c}{m_2}\ket0 + \frac{d}{m_2}\ket1) + m_3\ket{10}\otimes(\frac{e}{m_3} \ket0 + \frac{f}{m_3}\ket{1})+ m_4\ket{11}\otimes(\frac{g}{m_4}\ket 0 +\frac{h}{m_4} \ket{1})$ 
Ahora tenemos los qubits que queremos medir como producto tensor de qubits con longitud unidad. Luego la probabilidad de medir un estado sería $m_1^2$ ($m_1$ al cuadrado) para $\ket {00}$, $m_2^2$ para $\ket {01}$, $m_3^2$ para $\ket {10}$ y $m_4^2$ para $\ket {11}$.

El [[Entanglement (Entrelazado)]] se puede ver aqui como si la medida de un conjunto de qubits afecta la medida de otro conjunto de qubits.

Medir un qubit cambia el estado del qubit (sistemas cuánticos estáticos). Pero este no es la única forma de cambiar el estado de un qubit, la otra forma es mediante sus transformaciones cuanticas o [[Quantum Gates]] (sistemas cuánticos dinámicos).

#### Bibliografía
- [[Resumen.pdf]]
- [[Quantum_Computing_Explained_David_McMahon.pdf]]

Vamos a verlo desde el punto de vista de la computación y más sencillo.
Los bits los representamos en binario matematicamente. Si queremos representar algo que tiene m estados con bits entonces necesitamos al menos n bits verificando $2^n \geq m$. (los estados son el número de posibilidades).

**Clásicamente (Hartley)**
La pregunta dado un mensaje m cuanta información contiene. Clásicamente se tomaba lo siguiente, suponiendo la igualdad $2^n = m$, tomando logaritmos en base 2, $\log_{2}m=n$. Esto dice que en n bits podemos guardar m mensajes distintos.

**Entropía y la teoría de Shannon**
Se basa en como de probable es que obtengamos un tipo de mensaje.
Supongamos que p es la probabilidad de un mensaje, entonces la información contenida la medimos por (ponemos un - para que sea positiva):
$$I = -log_{2}p$$ 
Si p es 0, entonces I es 0.
Ahora esto se reduce en dos ideas clave:
- Un mensaje que tenga poca probabilidad contiene mucha información.
- Un mensaje que tenga mucha probabilidad contiene poca información.

Generalizando al mensaje con todos sus tipos. Sea $X$ una variable aleatoria (discreta) (puede representar que haya mensajes) con distribución de probabilidad $\overset{\rightarrow}{p}$, es decir $x_1,\dots,x_n$ y las probabilidades $p_1,\dots,p_n$.
La entropía de Shannon de $X$ se define como:
$$H(X)=-\underset{i}{\sum} p_i log_2p_i$$

(Oye, si la variable $X$ es continua lo más normál será tomar lo siguiente:
$H(X) = -\int p_i log_2p_i$ )

La entropía de Shannon mide la cantidad de aleatoriedad o incertidumbre de un mensaje (señal), la entropía tiene dos aspectos:
- Si estamos seguros del contenido de un mensaje, la entropía es 0
- Cuanto más inseguros estamos del contenido de un mensaje, mayor es la entropía.
Resumiendo:
- Disminuye incertidumbre $\Rightarrow$ Aumenta la información
- Aumenta incertidumbre $\Rightarrow$ Aumenta la entropía

Por último cotas, supongamos que necesitamos $l_i$ bits para codificar $x_i$. La media de bits de X es:
$$R_X = \overset{n}{\underset{i=1}{\sum}}l_ip_i$$
Dado una codificación unica para cada estado y en caso de recibir una señal saber cuales son (esto es si tengo tres estados $\{x_1,x_2,x_3\}$ no puedo codificarlo como $\{0,1,10\}$ ya que si me dan la señal $10$ no se si $x_3$ o $x_2x_1$ , es ser uniquely decodable, descifrable de una sola forma) se da lo siguiente (se puede probar):
$H(X) \leq R_X$
El peor caso de la entropía es que $X$ siga una distribución uniforma $p_i=\frac{1}{n}$. $$H(X) =-\overset{n}{\underset{i=1}{\sum}} \frac{1}{n} log_2\frac{1}{n} = log_2{n}$$
Luego tenemos una mejor cota de la entropía:
$$0 \leq H(X) \leq log_2{n}$$
La entropía relativa de una variable $X$ condicionada a una variable $Y$ (a un valor $y_i$ concreto de $Y$), es igual que sola pero metiendo probabilidad condicionada. $$H(X\|Y)=-\underset{j}{\sum} p(x_j| y_i) log_2p(x_j| y_i)$$ 
$$H(X\| Y) \leq H(X)$$
Si X e Y son independientes (y tendriamos la igualdad en la desigualdad anterior) $$H(X,Y) = H(Y) + H(X| Y)$$ 

Se define la información mutua de las variables $X$ e $Y$, la diferencia entre la entropia de $X$ y la entropia de $X$ conocida $Y$ (o más bien un valor suyo):
$$I(X|Y)=H(X) - H(X | Y)$$

(Repaso de [[Probabilidad]])

#### Bibliografía
- [[Quantum_Computing_Explained_David_McMahon.pdf]]



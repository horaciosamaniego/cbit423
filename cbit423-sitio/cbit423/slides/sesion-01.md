---
marp: true
theme: default
paginate: true
lang: es
math: katex
header: "CBIT423 · Semana 01 · La red como formalismo"
footer: "Horacio Samaniego · Instituto de Conservación, Biodiversidad y Territorio · UACh"
---

<!-- _class: lead -->
<!-- _paginate: false -->

# La red como formalismo

### ¿Qué gano, y qué pierdo, al decir que mi sistema *es* una red?

CBIT423 — Semana 1
Lectura ancla: Barabási, caps. 1 y 2 (§2.1–2.5)

---

## Ruta de la sesión

**I. ¿Por qué redes?** — interdependencia, sistemas complejos, por qué el campo emerge ahora
**II. Königsberg, 1735** — el primer problema resuelto representando
**III. El formalismo mínimo** — $G=(V,E)$, grado, y qué se pierde en el camino
**IV. El paper de la semana** — Butts (2009)
**V. Taller** — tu propio Königsberg, en papel

<!-- Advertir desde el inicio: hoy no se toca el computador. Ni hoy ni las próximas cuatro semanas. -->

---

## Glosario de la semana

| Español | Inglés | Notación |
|---|---|---|
| nodo, vértice | *node*, *vertex* | $i,\ j$ |
| enlace, arista | *edge*, *link*, *tie* | $(i,j)$ |
| grafo, red | *graph*, *network* | $G=(V,E)$ |
| grado | *degree* | $k_i$ |
| grado promedio | *average degree* | $\langle k \rangle$ |
| frontera del sistema | *system boundary* | — |

> Toda la literatura del curso está en inglés. El glosario abre cada sesión.

---

## ¿Red o grafo?

Barabási registra la doble tradición terminológica:

| Sistemas reales | Literatura matemática |
|---|---|
| red (*network*) | grafo (*graph*) |
| nodo (*node*) | vértice (*vertex*) |
| enlace (*link*) | arista (*edge*) |

La columna izquierda viene de quienes miden sistemas; la derecha, de quienes los demuestran.
En la práctica se usan indistintamente — **pero el vocabulario que elijas delata de qué tradición vienes.**

---

<!-- _class: lead -->

# I. ¿Por qué redes?

---

## 14 de agosto de 2003

Una línea de transmisión en Ohio roza un árbol.

En cuestión de horas, unos **50 millones de personas** en el noreste de Estados Unidos y en Ontario quedan sin electricidad.

Ninguna central falló. Ninguna línea fue atacada.

<!-- Preguntar antes de avanzar: ¿por qué un contacto local produce un apagón continental? -->

---

## Lo que el apagón enseña

El comportamiento del sistema **no estaba en sus componentes**.

- Cada generador funcionaba dentro de especificación
- Cada línea estaba correctamente dimensionada
- La falla emergió de **cómo estaban conectados**

Estudiar los componentes por separado —por exhaustivamente que se haga— no habría anticipado la cascada.

> Éste es el argumento fundacional de todo el curso.

---

## Detrás de cada sistema complejo hay una red

Barabási lo formula como principio: para entender un sistema complejo, primero hay que **cartografiar su red**.

| Sistema | Nodos | Enlaces |
|---|---|---|
| Célula | metabolitos, proteínas | reacciones, interacciones |
| Sociedad | individuos | vínculos sociales |
| Ecosistema | especies | depredación, mutualismo |
| Ciudad | intersecciones, personas | calles, viajes, llamadas |
| Ciencia | artículos, autores | citas, coautoría |

<!-- Pedirle que agregue una fila con su propio sistema. En la pizarra, no en la diapositiva. -->

---

## ¿Por qué ahora? Dos fuerzas

La teoría de grafos existe desde 1735. La ciencia de redes, desde hace ~25 años.
Barabási identifica dos razones:

**1. Los mapas.** La digitalización hizo mensurables redes que antes eran inaccesibles: rastreo de la web, registros de telefonía móvil, interactomas, bases de citas, sensores.

**2. La universalidad.** Redes de dominios sin relación alguna resultaron compartir principios de organización — y por lo tanto, herramientas.

---

## Sobre la universalidad — con cautela

La universalidad es la promesa del campo y también su tentación.

Que la web, la célula y una red social compartan una firma estructural **no implica** que compartan un mecanismo.

<!-- Sembrar aquí la semana 7: Broido & Clauset someterán esta afirmación a contraste sistemático. Que quede la duda instalada desde el día 1. -->

> Volveremos sobre esto en la semana 7, y no será amable con la versión fuerte del argumento.

---

## Las cuatro características del campo

Según Barabási, la ciencia de redes es:

1. **Interdisciplinaria** — el formalismo cruza dominios sin pedir permiso
2. **Empírica y guiada por datos** — no es teoría de grafos pura: los mapas mandan
3. **Cuantitativa y matemática** — hereda de la física estadística y de la matemática discreta
4. **Computacional** — el tamaño de las redes reales obliga a algoritmos

Este curso invierte el orden: **las semanas 1 a 5 trabajan (1) y (2); el cómputo llega en la semana 6.**

---

## Por qué el orden importa

La característica computacional es la más visible y la menos determinante.

Un análisis de redes mal formalizado y bien programado produce resultados **precisos y falsos** — y el código no da ninguna señal de alarma.

La decisión de qué es un nodo no tiene *stack trace*.

---

<!-- _class: lead -->

# II. Königsberg, 1735

---

## El problema

La ciudad de Königsberg (hoy Kaliningrado) se extendía sobre el río Pregel: dos riberas, dos islas, **siete puentes**.

**La pregunta de los habitantes:** ¿existe un recorrido que cruce cada puente exactamente una vez?

Nadie lo lograba. Nadie podía demostrar que fuera imposible.

<!-- Dibujar el mapa en la pizarra, con detalle geográfico innecesario. Ése es el punto. -->

---

## El movimiento de Euler

Euler **descartó la geografía**.

- Cada masa de tierra $\rightarrow$ un nodo
- Cada puente $\rightarrow$ un enlace

Cuatro nodos, siete enlaces. Distancias, formas, tamaños: irrelevantes.

> La pregunta dejó de ser sobre Königsberg y pasó a ser sobre un grafo.

---

## El argumento

En cualquier recorrido, cada vez que se **entra** a un nodo hay que **salir** de él — salvo en el inicio y en el final.

Por lo tanto, si cada enlace se usa exactamente una vez:

- Todo nodo intermedio debe tener **grado par**
- A lo sumo dos nodos (inicio y fin) pueden tener **grado impar**

Es una condición sobre la **paridad de los grados**. Nada más.

---

## Los grados de Königsberg

$$k_A = 5, \qquad k_B = k_C = k_D = 3$$

Los cuatro nodos tienen grado impar.

$$\sum_i k_i = 5 + 3 + 3 + 3 = 14 = 2L \quad \Rightarrow \quad L = 7 \ \checkmark$$

**El recorrido no existe.** No por falta de ingenio: por estructura.

---

## Lo que Euler realmente hizo

No resolvió un acertijo. Hizo **tres movimientos**, en este orden:

1. **Eligió** qué contaba como nodo y qué como enlace
2. **Descartó** todo lo demás como irrelevante para la pregunta
3. **Demostró** algo sobre el objeto resultante

El paso (3) es el famoso. El paso (1) es el que hizo posible el paso (3).

> Y el paso (1) no era obligatorio: otra representación —puentes como nodos, por ejemplo— habría dado otro problema.

---

## La lección para este curso

Euler no descubrió una propiedad de Königsberg.
Descubrió una propiedad **del grafo con el que decidió representar Königsberg**.

Toda la Fase I de este curso vive en esa distinción.

Cuando en la semana 5 defiendas tu protocolo de problematización, estarás haciendo exactamente el paso (1) — y tendrás que justificar por qué descartaste lo que descartaste.

---

<!-- _class: lead -->

# III. El formalismo mínimo

---

## Notación

$$G = (V, E)$$

- $V$: conjunto de nodos, con $|V| = N$
- $E$: conjunto de enlaces, con $|E| = L$

En Königsberg: $N = 4$, $L = 7$.

Todo lo que veremos en quince semanas —distancias, comunidades, robustez, modelos nulos— son **consecuencias** de $V$ y $E$.

---

## Grado

El **grado** $k_i$ es el número de enlaces del nodo $i$.

Para una red no dirigida, cada enlace aporta a dos nodos:

$$\sum_{i=1}^{N} k_i = 2L \qquad\Longrightarrow\qquad \langle k \rangle = \frac{2L}{N}$$

En Königsberg: $\langle k \rangle = 14/4 = 3{,}5$.

<!-- Que verifique la identidad a mano sobre el grafo de Königsberg antes de seguir. -->

---

## El mismo sistema, tres redes distintas

Un bosque puede formalizarse como:

- **Nodos = especies**, enlaces = interacciones tróficas
- **Nodos = individuos**, enlaces = vecindad espacial
- **Nodos = fragmentos de hábitat**, enlaces = flujo de dispersión

Las tres son correctas. Las tres responden preguntas **distintas e incompatibles**.

La elección no se justifica por los datos disponibles, sino por la pregunta.

---

## Qué se pierde

Representar un sistema como grafo implica aceptar que:

- Los nodos son **discretos** y **distinguibles**
- Los enlaces son **diádicos** — lo que ocurre entre tres partes se descompone o se pierde
- La relación es **binaria o escalar**, nunca cualitativa
- La estructura es **estática**, salvo declaración explícita

Cada supuesto es un costo. Puede valer la pena; lo que no se puede es ignorarlo.

---

<!-- _class: lead -->

# IV. El paper de la semana

**Butts, C. T. (2009).**
*Revisiting the foundations of network analysis.*
Science, 325(5939), 414–416.

---

## 1 · La decisión de formalización

- ¿Qué define Butts como nodo?
- ¿Qué define como enlace?
- ¿Qué queda fuera del sistema, y es una omisión declarada o silenciosa?

<!-- Que responda el/la estudiante antes de que yo diga nada. -->

---

## 2 · La figura central

<!-- Proyectar la figura y leerla en voz alta, elemento por elemento. -->

- ¿Qué muestra exactamente?
- ¿Qué se ve **porque** la formalización lo permite ver?

---

## 3 · Qué hace bien

- ¿Qué afirmación se vuelve posible gracias a esta formalización?
- ¿Podría sostenerse esa afirmación sin el formalismo de redes?

---

## 4 · Qué no resiste

- ¿Qué supuesto es frágil?
- ¿Hay contraste contra alguna expectativa nula?
- ¿Se salta del patrón observado al mecanismo?

> Esta diapositiva se repite las quince semanas. Es el eje de lectura del curso.

---

## Butts y Euler, en una línea

Euler (1735) **hizo** el movimiento.
Butts (2009) lo **nombró** como decisión metodológica y mostró que sigue tomándose mal.

Doscientos setenta y cuatro años entre uno y otro.

<!-- Preguntar: ¿por qué tardó tanto en volverse un problema explícito? Pista: mientras las redes eran pequeñas y hechas a mano, la decisión era visible. -->

---

<!-- _class: lead -->

# V. Taller — 1 hora

### Tu propio Königsberg

---

## Instrucciones

Sobre papel. Sin computador.

1. Escribe la **pregunta** que te interesa de tu sistema. Una frase.
2. Propón **dos formalizaciones distintas**: dos definiciones de nodo y enlace que ambas sean defendibles.
3. Para cada una, escribe **qué descartas** al adoptarla.
4. Decide cuál de las dos responde mejor tu pregunta — y por qué la otra no.

<!-- Si propone una sola formalización, no ha entendido el ejercicio. Insistir en la segunda. -->

---

## Producto de la semana

**Rastreo bibliográfico inicial**

- ¿Alguien ya formalizó tu sistema como red?
- Si sí: ¿qué eligieron como nodo, y estás de acuerdo?
- Si no: ¿por qué no? ¿Falta de datos, o falta de pertinencia?

**Además:** proponer 3 artículos de campos ajenos para el ensayo comparado (Hito 1, semana 2).
Plazo: 5 días, en `lecturas/propuestas.md`.

---

<!-- _class: lead -->

## Semana 2

### Barrido comparado entre disciplinas

Cinco campos, cinco definiciones de nodo.

Ancla: Ramos-Jiliberto, capítulos introductorios
Hallmark: Proulx, Promislow & Phillips (2005), *Network thinking in ecology and evolution*

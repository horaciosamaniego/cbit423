**UNIVERSIDAD AUSTRAL DE CHILE**
**FACULTAD DE CIENCIAS FORESTALES Y RECURSOS NATURALES**
**INSTITUTO DE CONSERVACIÓN, BIODIVERSIDAD Y TERRITORIO**

# 1. Información general

| | |
|---|---|
| **1.1. Nombre de la asignatura** | Introducción a Redes Complejas con aplicaciones en Ecología, Conservación y Socio-Ecosistemas |
| **1.2. Código** | CBIT423 |
| **1.3. Créditos** | 4 |
| **1.4. Período académico** | Segundo semestre |
| **1.5. Tipo de asignatura** | Electiva |
| **1.6. Horas teóricas** | 3 |
| **1.7. Horas prácticas** | 1 |
| **1.8. Cupo** | 10 (mínimo 1) |
| **1.9. Pre-requisitos** | Estadística avanzada. No se exige experiencia previa en programación: la nivelación en Python se realiza como trabajo autónomo durante la Fase I, de modo que la Fase II pueda iniciarse sin retraso. |
| **1.10. Prof. Responsable** | Horacio Samaniego + Prof. Invitados |
| **1.11. Modalidad** | Seminario–taller de cohorte reducida, organizado en dos fases. Ver sección 5. |

# 2. Descripción de la asignatura

Una introducción al uso de redes complejas con ejemplos en el estudio de los socio-ecosistemas. Se busca desarrollar una capacidad de análisis de los sistemas complejos usando el formalismo de redes. Se espera que el/la estudiante desarrolle capacidades analíticas cualitativas y cuantitativas para problematizar su sistema de estudio en función de las interacciones entre sus componentes.

La asignatura se organiza en **dos fases**. La **Fase I** (primer tercio del semestre) es conceptual y no involucra programación: mediante un barrido comparado de la literatura de distintas disciplinas, el/la estudiante examina cómo diferentes campos han convertido sus objetos de estudio en nodos y enlaces, y construye a partir de ese ejercicio una problematización propia de su sistema en clave de redes. El producto de esta fase es un protocolo de formalización explícito y defendible. La **Fase II** (dos tercios restantes) traslada ese protocolo al plano computacional: construcción, caracterización, contraste contra modelos nulos y modelación de la red, con programación en Python sobre datos reales.

El orden importa. La decisión metodológica central en el análisis de redes —qué cuenta como nodo, qué cuenta como enlace y dónde termina el sistema— es teórica, no computacional, y se toma antes de escribir la primera línea de código. Se espera que al término del curso el/la estudiante adquiera una visión sistémica de la ocurrencia de redes en fenómenos ecológicos y socioeconómicos, disponga de nociones sólidas para manipularlas computacionalmente y sea capaz de distinguir un patrón estructural informativo de un artefacto del muestreo, de la agregación o del azar.

# 3. Objetivos

## 3.1. Objetivo general

Analizar y comprender los progresos realizados en la investigación de sistemas complejos mediante el desarrollo y aplicación del formalismo de redes.

## 3.2. Objetivos específicos

**3.2.1.** Analizar y comprender el fenómeno de interconexión entre los elementos de un sistema.

**3.2.2.** Rastrear y comparar críticamente cómo distintas disciplinas formalizan sus objetos de estudio como redes, identificando qué pregunta habilita y qué pregunta clausura cada formalización.

**3.2.3.** Formalizar el propio sistema de estudio como una red, explicitando y defendiendo las decisiones de definición de nodos, enlaces y frontera, y descartando de manera razonada formalizaciones alternativas.

**3.2.4.** Construir, analizar y modelar redes, idealmente en distintos socio-ecosistemas.

**3.2.5.** Evaluar la significancia de un patrón estructural mediante modelos nulos apropiados, distinguiendo señal de artefacto.

**3.2.6.** Producir un análisis reproducible y comunicable, con código versionado y resultados replicables por terceros.

# 4. Contenidos

## FASE I — Problematización y formalización

### 4.1. Introducción: la red como formalismo

- Redes y problematización de relaciones en sistemas complejos
- Representación y grafos
- Qué se gana y qué se pierde al representar un sistema como grafo

### 4.2. Problematización comparada entre disciplinas

- Interacciones ecológicas: tramas tróficas y redes mutualistas
- Redes sociales y de gobernanza
- Redes espaciales, urbanas y de movilidad
- Redes de información y de citaciones
- Sistemas socio-ecológicos y redes multinivel
- Cómo cada campo define su nodo, y qué pregunta le permite responder esa elección

### 4.3. Vocabulario formal sin cómputo

- Grado, camino, componente, ciclo
- Redes dirigidas, ponderadas y bipartitas
- Lectura de matrices de adyacencia y de diagramas a mano
- Ejercicios analógicos sobre subconjuntos pequeños del sistema propio

### 4.4. Especificación del sistema

- Unidad de observación y definición de frontera: qué queda fuera de la red y por qué
- Sesgos de muestreo, datos faltantes y efectos de la agregación
- La proyección de redes bipartitas y sus falacias
- Formalizaciones alternativas de un mismo sistema: defensa y descarte
- Hipótesis estructurales explícitas: qué estructura se espera observar y qué la refutaría

## FASE II — Análisis computacional

### 4.5. Construcción y caracterización de redes

- Del protocolo al listado de enlaces: flujo de datos y formatos
- La matriz de adyacencia en la práctica
- El grado: promedio, distribución y colas pesadas
- Densidad, conectancia y componentes
- Caminos y distancias
- Centralidades y su interpretación sustantiva
- Asortatividad y correlaciones de grado

### 4.6. Modelos nulos y significancia estadística

- Aleatorización de redes y modelo de configuración
- Contraste de patrones observados frente a expectativas nulas

### 4.7. Estructura mesoscópica

- Modularidad, partición y clusterización
- Algoritmos de detección de comunidades: supuestos y límite de resolución
- Estabilidad, validación y comparación de particiones

### 4.8. Propiedades y modelos generativos de redes

- Grafos aleatorios
- Redes de pequeño mundo
- *Preferential attachment*
- Mecanismo frente a patrón: qué puede y qué no puede inferirse de la topología

### 4.9. Módulos electivos *(se selecciona uno en la semana 8)*

- **Redes espaciales:** decaimiento con la distancia, modelos de gravedad, restricciones del embebimiento
- **Robustez y percolación:** remoción de nodos, fragmentación, aplicaciones en conservación
- **Redes temporales y multicapa:** redes que cambian en el tiempo, sistemas con múltiples tipos de interacción

### 4.10. Reproducibilidad y comunicación de resultados

- Control de versiones y cuadernos ejecutables
- Visualización de redes: cuándo ayuda y cuándo engaña
- Escritura de resultados estructurales

# 5. Metodología de trabajo

Discusión de **literatura primaria** y, en su segunda mitad, ejercicios de **programación en Python**. Dado el carácter electivo de la asignatura y el número reducido de estudiantes, el tiempo lectivo se organiza en formato de seminario–taller en lugar de cátedra expositiva. La carga horaria total se mantiene sin variación.

## 5.1. Organización del tiempo lectivo

**Fase I — semanas 1 a 5 (sin programación)**

| Bloque | Duración | Descripción |
|---|---|---|
| **Seminario de barrido comparado** | 2 h semanal | Discusión de literatura primaria de distintas disciplinas, conducida por el/la estudiante. El foco no está en los resultados de cada artículo sino en la decisión de formalización que lo hizo posible. |
| **Taller de problematización** | 1 h semanal | Trabajo sobre pizarra y papel con el sistema propio: definiciones tentativas, diagramas, matrices pequeñas construidas a mano. |
| **Trabajo autónomo** | 1 h semanal | Rastreo bibliográfico y nivelación autónoma en Python con material entregado por el docente. |

**Fase II — semanas 6 a 15 (computacional)**

| Bloque | Duración | Descripción |
|---|---|---|
| **Seminario** | 1,5 h semanal | Discusión de literatura primaria metodológica conducida por el/la estudiante. El docente interviene con exposición breve (~20 min) sólo para cubrir los vacíos que la lectura deja abiertos. |
| **Clínica de código** | 1,5 h semanal | Programación en pareja sobre los datos del/de la estudiante. Pantalla compartida; el docente y el/la estudiante alternan en el teclado. |
| **Trabajo autónomo supervisado** | 1 h semanal | Avance individual con entrega semanal al repositorio, revisado de forma asíncrona por el docente antes de la sesión siguiente. |

## 5.2. La secuencia teoría → cómputo

La Fase I no es preparatoria en sentido débil: produce un documento vinculante. El **protocolo de problematización** entregado en la semana 5 fija las definiciones de nodo, enlace y frontera, y enuncia las hipótesis estructurales que la Fase II pondrá a prueba. Todo cambio posterior al protocolo debe registrarse y justificarse en la bitácora, del mismo modo en que se documenta una desviación respecto de un plan de análisis preregistrado.

La nivelación en Python ocurre en paralelo durante la Fase I como trabajo autónomo asíncrono, de manera que la semana 6 no comience desde cero. La **auditoría de datos** de la semana 4 verifica que el/la estudiante disponga efectivamente de los datos requeridos por su protocolo antes de que se inicie la fase computacional; de no ser así, el docente provee un conjunto de datos alternativo de complejidad equivalente.

## 5.3. Profesores invitados y audiencia externa

Los profesores invitados no participan como expositores sino como comisión informal: asisten a la defensa del protocolo (semana 5) y al seminario de cierre (semana 15), formulan preguntas y entregan retroalimentación. Esta modalidad restituye la exigencia propia de una presentación pública en un curso de cohorte reducida y funciona como ensayo de defensa de tesis. Las sesiones de seminario quedan abiertas a estudiantes e investigadores del Instituto en calidad de oyentes.

## 5.4. Herramientas

Fase I: gestor bibliográfico (Zotero o equivalente), papel y pizarra. Fase II: Python (NetworkX, igraph, pandas, NumPy, matplotlib; geopandas cuando corresponda), cuadernos Jupyter o Quarto, y control de versiones con git. Desde la semana 6 todo el trabajo reside en un repositorio único, que constituye la evidencia principal de evaluación continua.

# 6. Evaluación

| Componente | Ponderación | Evidencia |
|---|:---:|---|
| **Ensayo comparado de formalizaciones** (Hito 1, sem. 2) | 15% | Ensayo de ~2.000 palabras contrastando cómo cinco campos definen nodos y enlaces, y qué pregunta habilita cada definición. |
| **Protocolo de problematización y su defensa** (Hito 2, sem. 5) | 20% | Documento de especificación del sistema propio como red, con hipótesis estructurales y alternativas descartadas, defendido ante profesores invitados. |
| **Conducción de seminarios de literatura primaria** | 15% | Calidad de las preguntas planteadas al artículo, no del material de apoyo. Mínimo 8 sesiones conducidas a lo largo del semestre. |
| **Bitácora y repositorio computacional** (Fase II) | 20% | Repositorio con historial de *commits* y cuadernos ejecutables. Incluye el checkpoint de caracterización de la semana 11. |
| **Reporte final y seminario abierto** (Hitos 4 y 5) | 30% | Reporte con análisis original en formato de manuscrito breve y presentación pública. |

El reporte final consiste en un análisis original sobre datos propios, presentado en formato de manuscrito breve (introducción, métodos, resultados y discusión; extensión sugerida 4.000–6.000 palabras) y acompañado del repositorio que permite reproducir íntegramente sus resultados. Su sección de métodos se construye sobre el protocolo de la semana 5. La entrega de los hitos en las fechas señaladas es requisito de aprobación.

# 7. Cronograma

El cronograma es indicativo. El módulo electivo de la semana 13 se selecciona en conjunto con el/la estudiante a más tardar en la semana 8, en función de lo que requiera su sistema de estudio.

## Fase I — Problematización (semanas 1–5, sin programación)

| Sem. | Contenido y literatura | Producto sobre el sistema propio |
|:---:|---|---|
| 1 | La red como formalismo. Representación y grafos. Qué se gana y qué se pierde al representar un sistema como grafo. | Rastreo bibliográfico inicial en la propia disciplina: ¿alguien ya formalizó esto como red? |
| 2 | Barrido comparado: interacciones ecológicas, redes sociales y de gobernanza, redes espaciales y urbanas, redes de información, sistemas socio-ecológicos. | **HITO 1** — Ensayo comparado de formalizaciones (~2.000 palabras). |
| 3 | Vocabulario formal sin cómputo: grado, camino, componente, bipartito, dirigido, ponderado. Lectura de matrices y diagramas a mano. | Ejercicio analógico: representación manual de un subconjunto de 10–20 nodos del `[sistema de estudio del/de la estudiante]`. |
| 4 | Unidad de observación y especificación de frontera. Sesgos de muestreo, datos faltantes, agregación. Proyección y sus falacias. | Auditoría de datos: qué datos existen, en qué estado, qué falta y qué es inalcanzable. |
| 5 | Formalizaciones alternativas del mismo sistema: defensa y descarte. Enunciado de hipótesis estructurales. | **HITO 2** — Protocolo de problematización y defensa ante profesores invitados (25 min + preguntas). |

## Fase II — Análisis computacional (semanas 6–15)

| Sem. | Contenido y literatura | Producto sobre el sistema propio |
|:---:|---|---|
| 6 | Entrada al cómputo de redes: Python y NetworkX. Del protocolo al listado de enlaces. Formatos y matriz de adyacencia. | Red construida y cargada según las definiciones fijadas en el protocolo. |
| 7 | Grado: promedio, distribución y colas pesadas. Ajuste y contraste de distribuciones. Densidad y conectancia. | Distribución de grado y descripción básica de la red. |
| 8 | Caminos, distancias, componentes. Centralidades y su interpretación. Asortatividad. | Caracterización topológica completa. Selección del módulo electivo de la semana 13. |
| 9 | Modelos nulos y aleatorización. Modelo de configuración. Significancia de un patrón estructural. | Línea base nula. ¿Qué del patrón observado sobrevive al azar? |
| 10 | Modularidad y partición. Algoritmos de detección de comunidades y sus supuestos. | Detección de comunidades sobre el sistema propio. |
| 11 | Límite de resolución, estabilidad y validación. Comparación de particiones. | **HITO 3** — Caracterización contrastada contra modelos nulos (checkpoint de bitácora). |
| 12 | Modelos generativos: grafos aleatorios, mundo pequeño, *preferential attachment*. Mecanismo vs. patrón. | Contraste de las hipótesis estructurales enunciadas en el protocolo. |
| 13 | Módulo electivo: redes espaciales · robustez y percolación · redes temporales y multicapa. | Análisis del módulo seleccionado. |
| 14 | Escritura científica con resultados de redes. Figuras, reproducibilidad, control de versiones. | **HITO 4** — Borrador de la sección de resultados y figuras finales. |
| 15 | Seminario abierto de cierre. | **HITO 5** — Presentación pública (Instituto/Laboratorio) y entrega del reporte final. |

# 8. Bibliografía

## 8.1. Textos de referencia

Menczer, F., Fortunato, S., & Davis, C. A. (2020). *A First Course in Network Science*. Cambridge University Press. DOI: 10.1017/9781108653947

Barabási, A.-L. (2016). *Network Science*. Cambridge University Press.

Latora, V., Nicosia, V., & Russo, G. (2017). *Complex Networks: Principles, Methods and Applications*. Cambridge University Press.

Newman, M. E. J. (2018). *Networks* (2nd ed.). Oxford University Press.

Jackson, M. O. (2010). *Social and Economic Networks*. Princeton University Press.

Borgatti, S. P., Everett, M. G., & Johnson, J. C. (2018). *Analyzing Social Networks* (2nd ed.). SAGE.

Ramos-Jiliberto, R. (2020). *Deja a la Estructura Hablar: Modelización y Análisis de Sistemas Naturales, Sociales y Socioecológicos*. Ediciones Umayor.

## 8.2. Literatura primaria — Fase I (formalización comparada)

Bascompte, J., & Jordano, P. (2007). Plant-animal mutualistic networks: the architecture of biodiversity. *Annual Review of Ecology, Evolution, and Systematics*, 38, 567–593.

Bodin, Ö. (2017). Collaborative environmental governance: achieving collective action in social-ecological systems. *Science*, 357(6352), eaan1114.

Barthélemy, M. (2011). Spatial networks. *Physics Reports*, 499(1–3), 1–101.

Newman, M. E. J. (2003). The structure and function of complex networks. *SIAM Review*, 45(2), 167–256.

Butts, C. T. (2009). Revisiting the foundations of network analysis. *Science*, 325(5939), 414–416.

## 8.3. Literatura primaria — Fase II (métodos)

Watts, D. J., & Strogatz, S. H. (1998). Collective dynamics of 'small-world' networks. *Nature*, 393, 440–442.

Barabási, A.-L., & Albert, R. (1999). Emergence of scaling in random networks. *Science*, 286, 509–512.

Girvan, M., & Newman, M. E. J. (2002). Community structure in social and biological networks. *PNAS*, 99(12), 7821–7826.

Fortunato, S., & Hric, D. (2016). Community detection in networks: A user guide. *Physics Reports*, 659, 1–44.

Dunne, J. A., Williams, R. J., & Martinez, N. D. (2002). Network structure and biodiversity loss in food webs: robustness increases with connectance. *Ecology Letters*, 5(4), 558–567.

Holme, P., & Saramäki, J. (2012). Temporal networks. *Physics Reports*, 519(3), 97–125.

Kivelä, M., et al. (2014). Multilayer networks. *Journal of Complex Networks*, 2(3), 203–271.

## 8.4. Bibliografía específica

Lecturas entregadas en clases, seleccionadas en función del sistema de estudio abordado por el/la estudiante.

---

*Avenida Carlos Ibáñez del Campo · Campus Isla Teja · Valdivia · Chile*
*Fonos: 56-63-2221397 / 56-63-2221550 · postgrado@uach.cl · http://www.postgrado.uach.cl*

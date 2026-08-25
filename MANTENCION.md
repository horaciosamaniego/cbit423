# CBIT423 — Introducción a Redes Complejas

Sitio del curso *Introducción a Redes Complejas con aplicaciones en Ecología, Conservación y
Socio-Ecosistemas*. Instituto de Conservación, Biodiversidad y Territorio, Universidad Austral de Chile.

Sitio publicado: **https://USUARIO.github.io/cbit423**

---

## Puesta en marcha

### 1. Crear el repositorio

```bash
cd cbit423
git init -b main
git add .
git commit -m "Sitio del curso CBIT423"
gh repo create cbit423 --public --source=. --push
```

Sin `gh`: crear el repositorio en github.com y luego

```bash
git remote add origin https://github.com/USUARIO/cbit423.git
git push -u origin main
```

### 2. Activar GitHub Pages

En el repositorio: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

No elegir "Deploy from a branch" — el flujo de trabajo publica el artefacto directamente.

### 3. Reemplazar `USUARIO`

Aparece en tres archivos: `_quarto.yml` (dos veces), `README.md` y `index.qmd`.

```bash
grep -rl USUARIO . --exclude-dir=.git | xargs sed -i 's/USUARIO/tu-usuario/g'
```

### 4. Primer despliegue

```bash
git push
```

El flujo tarda 2–4 minutos. Se sigue desde la pestaña **Actions**.

---

## Estructura

```
cbit423/
├── _quarto.yml                 Configuración del sitio y navegación
├── index.qmd                   Portada
├── programa.qmd                → incluye _programa.md
├── lecturas.qmd                → incluye _lecturas.md
├── sesiones.qmd                Índice de diapositivas
├── proyecto.qmd                Descripción de los hitos
├── _programa.md                Programa oficial (fuente única)
├── _lecturas.md                Plan de lecturas (fuente única)
├── styles.css                  Identidad visual
├── slides/
│   └── sesion-01.md            Decks Marp, uno por semana
├── lecturas/
│   ├── propuestas.md           Propuestas del/de la estudiante
│   └── hallmark/               PDFs — IGNORADO POR GIT (ver abajo)
├── proyecto/
│   └── protocolo-plantilla.md  Plantilla del Hito 2
└── .github/workflows/
    └── publish.yml             Quarto + Marp → GitHub Pages
```

### Fuente única

`_programa.md` y `_lecturas.md` son los documentos reales; los `.qmd` correspondientes sólo los
incluyen. Para actualizar el programa se edita el `.md`, no la página.

Los archivos que empiezan con guion bajo no se renderizan como páginas independientes, y
`_quarto.yml` limita el renderizado a `*.qmd` — por eso los decks Marp de `slides/` no se
confunden con páginas del sitio.

---

## Artículos y copyright

`lecturas/hallmark/` está en `.gitignore` **a propósito**.

Publicar PDFs de artículos con copyright en un repositorio público es redistribución. La página
de lecturas entrega la referencia completa de cada artículo; el acceso se gestiona por la
biblioteca de la UACh o por el aula virtual del curso.

La carpeta local sirve para trabajar; su contenido no se sube.

---

## Trabajo semanal

### Agregar una sesión

1. Crear `slides/sesion-NN.md` (copiar `sesion-01.md` como base — la estructura de bloques es fija)
2. Enlazarla en la tabla de `sesiones.qmd`
3. `git push`

Las diapositivas se compilan solas a HTML y PDF y quedan en `slides/sesion-NN.html`.

### Estructura fija de cada deck

| Bloque | Diapositivas |
|---|:---:|
| Apertura — la pregunta de la semana | 1 |
| Glosario bilingüe (español / inglés / notación) | 1–2 |
| Concepto | 6–10 |
| **Paper de la semana** — bloque fijo de 4 | 4 |
| Bloque del/de la estudiante | variable |
| Cierre — producto de la semana | 1 |

Las cuatro diapositivas del paper son siempre las mismas: la decisión de formalización,
la figura central, qué hace bien, qué no resiste.

---

## Trabajo local

### Previsualizar el sitio

```bash
quarto preview
```

Las diapositivas no aparecen en la previsualización local: se compilan en CI. Para verlas:

```bash
marp --no-stdin slides/sesion-01.md --html -o _site/slides/sesion-01.html
```

`--no-stdin` es necesario — sin él `marp` se queda esperando la entrada estándar.

### Exportar un deck a PDF

```bash
marp --no-stdin slides/sesion-01.md --pdf --allow-local-files -o sesion-01.pdf
```

Requiere Chrome o Chromium instalado localmente.

---

## Notas sobre el flujo de trabajo

- **El PDF es la parte frágil.** La exportación a PDF depende de Chrome en el runner. El flujo
  está escrito para que un fallo del PDF no detenga la publicación: el HTML se publica igual y
  queda un aviso en el log.
- **Matemáticas.** Los decks usan KaTeX (`math: katex` en el *frontmatter*). Verificado sobre
  `sesion-01.md`: 34 diapositivas, ecuaciones correctas.
- **Idioma.** El sitio está en español; la literatura primaria está en inglés. Cada deck abre con
  un glosario bilingüe — no es decorativo: sostiene la asimetría entre la lengua de la clase y la
  de los artículos.

---

## Licencia

Contenidos bajo [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es),
salvo los artículos de terceros, que conservan la licencia de sus editores.

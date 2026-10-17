# 📘 Guía de Markdown

![Markdown](https://img.shields.io/badge/Markdown-guía-black) ![GitHub](https://img.shields.io/badge/GitHub-README-blue) ![oficio-dev](https://img.shields.io/badge/oficio-dev-orange)

> [!TIP]
> Ábrela en VS Code y presiona **Ctrl + Shift + V** para verla como la mostraría GitHub.
> Para ver el código y el resultado lado a lado: **Ctrl + K** y luego **V**.

**Markdown** es una forma de dar formato a un texto con símbolos simples. GitHub lo usa en los README, en los issues y en los Pull Requests. Los archivos terminan en `.md`.

Esta guía está escrita en Markdown: todo lo que ves aquí lo puedes hacer tú. En cada sección ves primero **el resultado**; para ver **cómo se escribe**, abre el desplegable ▶.

## Contenido

1. [Títulos](#1-títulos)
2. [Párrafos](#2-párrafos)
3. [Negrita, cursiva y código](#3-negrita-cursiva-y-código)
4. [Listas](#4-listas)
5. [Enlaces e imágenes](#5-enlaces-e-imágenes)
6. [Bloques de código](#6-bloques-de-código)
7. [Tablas](#7-tablas)
8. [Citas y líneas divisorias](#8-citas-y-líneas-divisorias)
9. [Listas de tareas](#9-listas-de-tareas)
10. [Emojis](#10-emojis)
11. [Alertas](#11-alertas)
12. [Insignias](#12-insignias)
13. [Desplegables](#13-desplegables)
14. [Errores comunes](#14-errores-comunes)
15. [Plantilla para tu README](#15-plantilla-para-tu-readme)

---

## 1. Títulos

Un `#` y un espacio. Más `#`, título más pequeño. Usa un solo `#` por archivo: es el nombre del proyecto.

### Así se ve un título de nivel 3

<details>
<summary>▶ Ver cómo se escribe</summary>

```
# Título principal
## Sección
### Subsección
```

</details>

---

## 2. Párrafos

Esta es la primera idea.

Esta es la segunda idea. Entre las dos hay **una línea en blanco**: sin ella, salen pegadas en el mismo párrafo.

<details>
<summary>▶ Ver cómo se escribe</summary>

```
Esta es la primera idea.

Esta es la segunda idea.
```

</details>

---

## 3. Negrita, cursiva y código

Esto es **importante**, esto es *cursiva* y esto es `código`.

El `código` sirve para nombres de archivos y comandos: `main.py`, `git status`.

<details>
<summary>▶ Ver cómo se escribe</summary>

```
Esto es **importante**, esto es *cursiva* y esto es `código`.
```

Las comillas del código son las invertidas: en el teclado en español, la tecla a la derecha de la `P`, seguida de espacio.

</details>

---

## 4. Listas

- Leche
- Pan
- Huevos

1. Descargar el proyecto
2. Abrir la carpeta
3. Ejecutar el programa

<details>
<summary>▶ Ver cómo se escribe</summary>

```
- Leche
- Pan
- Huevos

1. Descargar el proyecto
2. Abrir la carpeta
3. Ejecutar el programa
```

Guion y espacio para una lista normal; número y punto para una lista con orden.

</details>

---

## 5. Enlaces e imágenes

[Visita GitHub](https://github.com)

Una imagen se escribe igual que un enlace, pero con `!` al inicio. El archivo de la imagen debe estar en el repositorio.

<details>
<summary>▶ Ver cómo se escribe</summary>

```
[Visita GitHub](https://github.com)

![Logo de la tienda](logo.png)
```

Entre `[ ]` va el texto que se ve; entre `( )`, la dirección.

</details>

---

## 6. Bloques de código

```python
productos = ["Leche", "Pan", "Huevos"]
for producto in productos:
    print(producto)
```

<details>
<summary>▶ Ver cómo se escribe</summary>

````
```python
productos = ["Leche", "Pan", "Huevos"]
for producto in productos:
    print(producto)
```
````

Tres comillas invertidas al inicio y al final. Si escribes el lenguaje después de las primeras (`python`, `php`, `sql`, `javascript`), GitHub le pone colores. Para comandos o árboles de carpetas, déjalo sin lenguaje.

</details>

---

## 7. Tablas

| Producto | Precio |
|---|---|
| Leche 1L | $4.500 |
| Pan tajado | $6.500 |

<details>
<summary>▶ Ver cómo se escribe</summary>

```
| Producto | Precio |
|---|---|
| Leche 1L | $4.500 |
| Pan tajado | $6.500 |
```

Una fila de títulos, una fila de guiones y luego los datos. Las columnas se separan con `|`.

</details>

---

## 8. Citas y líneas divisorias

> Un buen README responde tres preguntas: qué es, cómo se usa y quién lo hizo.

La línea que separa cada sección de esta guía es una línea divisoria.

<details>
<summary>▶ Ver cómo se escribe</summary>

```
> Un buen README responde tres preguntas: qué es, cómo se usa y quién lo hizo.

---
```

</details>

---

## 9. Listas de tareas

- [x] Crear el repositorio
- [ ] Escribir el README

<details>
<summary>▶ Ver cómo se escribe</summary>

```
- [x] Crear el repositorio
- [ ] Escribir el README
```

Con `x` la casilla sale marcada.

</details>

---

## 10. Emojis

🛒 Tienda Don Pedro · 🚀 En marcha · ✅ Funciona · ⚠️ Falta el README

<details>
<summary>▶ Ver cómo se escribe</summary>

Dos formas:

1. **Pegar el emoji directo.** En Windows, **Win + .** abre el selector. Funciona en todas partes.
2. **Escribir su código entre dos puntos.** GitHub lo convierte:

```
:rocket: :white_check_mark: :warning:
```

</details>

Úsalos con medida: uno al inicio de un título ayuda a ubicarse; diez en una línea distraen.

---

## 11. Alertas

> [!NOTE]
> Este proyecto usa Python 3.

> [!TIP]
> Ejecuta el programa desde la carpeta principal.

> [!WARNING]
> No subas el archivo `.env`.

<details>
<summary>▶ Ver cómo se escribe</summary>

```
> [!NOTE]
> Este proyecto usa Python 3.

> [!TIP]
> Ejecuta el programa desde la carpeta principal.

> [!WARNING]
> No subas el archivo `.env`.
```

Hay cinco tipos: `NOTE` (nota), `TIP` (consejo), `IMPORTANT` (importante), `WARNING` (advertencia) y `CAUTION` (peligro). Si en tu vista previa salen como una cita normal, en GitHub sí salen con color.

</details>

---

## 12. Insignias

Son las etiquetas de colores que ves al inicio de esta guía y de muchos README profesionales. Muestran el lenguaje, la versión o el estado del proyecto.

![Python](https://img.shields.io/badge/Python-3.12-blue) ![PHP](https://img.shields.io/badge/PHP-8-purple) ![Estado](https://img.shields.io/badge/estado-en%20desarrollo-orange)

**Una insignia tiene tres partes**, y tú las escribes en la dirección:

| Parte | Ejemplo | Dónde se ve |
|---|---|---|
| Texto | `Python` | Lado izquierdo, en gris |
| Valor | `3.12` | Lado derecho, en color |
| Color | `blue` | El color del lado derecho |

Así se arma la dirección: `https://img.shields.io/badge/` + `Texto-Valor-color`

<details>
<summary>▶ Ver cómo se escribe</summary>

```
![Python](https://img.shields.io/badge/Python-3.12-blue)
![PHP](https://img.shields.io/badge/PHP-8-purple)
![Estado](https://img.shields.io/badge/estado-en%20desarrollo-orange)
```

- Es una **imagen** de Markdown: `![nombre](dirección)`.
- Las partes se separan con guion: `Python-3.12-blue`.
- Los espacios se escriben `%20`: `en%20desarrollo`.
- Colores: `blue`, `green`, `orange`, `red`, `yellow`, `purple`, `black`.

</details>

> [!NOTE]
> Las insignias son imágenes que se descargan de internet. Sin conexión, solo verás su nombre. Úsalas en el README de tu perfil (el reto de la guía) para mostrar las tecnologías que manejas.

---

## 13. Desplegables

<details>
<summary>▶ Ábreme</summary>

Esto estaba escondido. Sirve para instrucciones largas o detalles que no todos necesitan leer. Toda esta guía los usa.

</details>

<details>
<summary>▶ Ver cómo se escribe</summary>

```
<details>
<summary>▶ Ábreme</summary>

Esto estaba escondido.

</details>
```

Deja una línea en blanco después de `</summary>` y antes de `</details>`: sin ellas, el Markdown de adentro no se ve bien.

</details>

---

## 14. Errores comunes

| Escribes | Problema | Corrección |
|---|---|---|
| `#Título` | Falta el espacio después de `#` | `# Título` |
| `-Leche` | Falta el espacio después del guion | `- Leche` |
| Dos párrafos sin línea en blanco | Salen pegados | Deja una línea vacía entre ellos |
| Tabla sin la fila de guiones | No se ve como tabla | Agrega la fila `\|---\|---\|` debajo de los títulos |
| Bloque de código sin cerrar | Todo lo que sigue sale como código | Cierra con tres comillas invertidas |

---

## 15. Plantilla para tu README

Copia esto en tu `README.md` y reemplaza lo que está entre `< >`.

<details>
<summary>▶ Ver la plantilla</summary>

````
# 🛒 Tienda Don Pedro

<Dos o tres líneas: qué es el proyecto y para qué sirve.>

## Productos

| Producto | Precio |
|---|---|
| <producto> | <precio> |

## Estructura

```
tienda-don-pedro/
├── datos/
├── src/
│   └── main.py
├── .gitignore
└── README.md
```

## Cómo ejecutarlo

```
python src/main.py
```

## Autor

<Tu nombre> · [GitHub](https://github.com/<tu-usuario>)
````

</details>

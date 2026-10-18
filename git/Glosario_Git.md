# 📖 Glosario de Git

> [!TIP]
> Ábrelo en VS Code y presiona **Ctrl + Shift + V** para verlo como en GitHub.

Las palabras y los comandos que vas a usar todos los días. Primero el vocabulario; después cada comando con sus opciones más comunes.

## Contenido

1. [Vocabulario](#1-vocabulario)
2. [Empezar un repositorio](#2-empezar-un-repositorio)
3. [El ciclo de cada cambio](#3-el-ciclo-de-cada-cambio)
4. [Ver la historia](#4-ver-la-historia)
5. [Ramas](#5-ramas)
6. [Trabajar con GitHub](#6-trabajar-con-github)
7. [Prefijos de los mensajes de commit](#7-prefijos-de-los-mensajes-de-commit)

---

## 1. Vocabulario

| Palabra | Qué es |
|---|---|
| **Git** | Programa que guarda la historia de un proyecto: qué cambió, cuándo y quién lo hizo. Funciona en tu computador, sin internet |
| **Repositorio** (repo) | Una carpeta cuya historia guarda Git. Cualquier carpeta se convierte en repositorio con `git init` |
| **`.git`** | Carpeta oculta dentro del repositorio donde vive toda la historia. No se borra ni se mueve |
| **Commit** | Una foto del proyecto en un momento. Tiene un código único (hash) y un mensaje que explica el cambio |
| **Hash** | El código de cada commit, por ejemplo `9abdcd4`. Sirve para identificarlo |
| **Working directory** | Tu carpeta: donde editas los archivos |
| **Staging area** (preparación) | La zona donde eliges qué cambios entran en el próximo commit. Se llega con `git add` |
| **Untracked** | Archivo nuevo que Git ve, pero todavía no sigue |
| **Modified** | Archivo que Git ya conocía y que cambió |
| **Rama** (branch) | Una línea de trabajo independiente. Permite trabajar en algo sin tocar la rama principal |
| **`main`** | El nombre de la rama principal. Antes se usaba `master` |
| **HEAD** | Indica en qué commit y en qué rama estás parado en este momento |
| **Merge** | Unir el trabajo de una rama con otra |
| **Conflicto** | Ocurre cuando dos ramas cambiaron las mismas líneas y Git no sabe cuál dejar. Lo resuelve una persona |
| **Remote** (remoto) | La copia del repositorio que está en otro lugar, por ejemplo en GitHub |
| **`origin`** | El nombre que se le da por costumbre al remoto principal |
| **Push** | Enviar tus commits al remoto |
| **Pull** | Traer los commits del remoto y unirlos a tu rama |
| **Fetch** | Traer la información del remoto sin unirla todavía |
| **`.gitignore`** | Archivo que le dice a Git qué no debe guardar ni subir: claves, archivos temporales, carpetas generadas |

---

## 2. Empezar un repositorio

| Comando | Qué hace |
|---|---|
| `git init` | Convierte la carpeta actual en un repositorio |
| `git init -b main` | Lo mismo, y llama `main` a la rama principal |
| `git config user.name "tu-usuario"` | Define el nombre que firma tus commits **solo en este repositorio** |
| `git config user.email "tu@correo.com"` | Define el correo, solo en este repositorio |
| `git config --global user.name "tu-usuario"` | Lo define **para todos tus repositorios** del computador. Úsalo solo en tu computador personal |
| `git config user.name` | Muestra el nombre configurado |

> [!WARNING]
> En un computador compartido, no uses `--global`: tus commits podrían salir con el nombre de otra persona, o los de otra persona con el tuyo.

---

## 3. El ciclo de cada cambio

| Comando | Qué hace |
|---|---|
| `git status` | Muestra el estado: qué cambió, qué está preparado y qué no. Úsalo antes y después de cada paso |
| `git add archivo.txt` | Prepara un archivo |
| `git add .` | Prepara todos los cambios de la carpeta actual |
| `git commit -m "mensaje"` | Guarda lo preparado como un commit, con su mensaje |
| `git commit --amend` | Corrige el último commit: cambia su mensaje o le agrega un archivo que se te olvidó. Úsalo solo si todavía no lo subiste |

**La regla:** un cambio, un commit. Si el mensaje necesita una "y", son dos commits.

---

## 4. Ver la historia

| Comando | Qué hace |
|---|---|
| `git log` | Muestra la historia completa: hash, autor, fecha y mensaje |
| `git log --oneline` | Una línea por commit: hash corto y mensaje |
| `git log --oneline --graph` | Igual, con un dibujo de las ramas |
| `git diff` | Muestra las líneas que cambiaron y aún no están preparadas |

---

## 5. Ramas

| Comando | Qué hace |
|---|---|
| `git branch` | Lista las ramas locales. La actual tiene un `*` |
| `git branch -a` | Lista también las ramas del remoto (`remotes/origin/...`) |
| `git branch nombre` | Crea una rama, sin cambiarte a ella |
| `git switch nombre` | Te cambia a una rama que ya existe |
| `git switch -c nombre` | **Crea** la rama y te cambia a ella. `-c` viene de *create* |
| `git checkout -b nombre` | La forma antigua de `switch -c`. La verás en tutoriales viejos |
| `git branch -m nuevo-nombre` | Renombra la rama actual. Útil si te equivocaste al escribirla |
| `git branch -d nombre` | Borra una rama **ya unida** con merge. Si no lo está, Git te avisa y no borra nada |
| `git branch -D nombre` | Borra una rama **a la fuerza**, aunque no esté unida. Úsalo con cuidado |
| `git merge nombre` | Une la rama `nombre` a la rama en la que estás |

> [!NOTE]
> No puedes borrar la rama en la que estás parado. Primero `git switch main`, luego `git branch -d`.

---

## 6. Trabajar con GitHub

| Comando | Qué hace |
|---|---|
| `git remote add origin URL` | Conecta tu repositorio con uno de GitHub y lo llama `origin` |
| `git remote -v` | Muestra a qué remoto está conectado |
| `git remote set-url origin URL` | Cambia la dirección del remoto, si la pusiste mal |
| `git push -u origin main` | Sube la rama `main` y la deja conectada. El `-u` hace que después baste con `git push` |
| `git push` | Sube tus commits nuevos |
| `git push -u origin nombre` | Sube una rama nueva a GitHub |
| `git pull` | Trae y une los cambios del remoto a tu rama |
| `git fetch` | Trae la información del remoto sin unirla |
| `git fetch --prune` | Trae lo nuevo y **limpia** las referencias a ramas que ya se borraron en GitHub |
| `git clone URL` | Descarga un repositorio de GitHub completo, con toda su historia |

**Después de un merge en GitHub, la limpieza completa es:**
```
git switch main
git pull
git branch -d nombre-de-la-rama
git fetch --prune
```

---

## 7. Prefijos de los mensajes de commit

El mensaje empieza con un prefijo que dice qué tipo de cambio es. Así se lee la historia de un vistazo.

| Prefijo | Cuándo | Ejemplo |
|---|---|---|
| `feat:` | Algo nuevo | `feat: agrega arroz a los productos` |
| `fix:` | Una corrección | `fix: corrige el precio de la leche` |
| `docs:` | Documentación | `docs: README con descripción y estructura` |
| `refactor:` | Reorganizar sin cambiar lo que hace | `refactor: mueve los datos a la carpeta datos` |
| `chore:` | Mantenimiento | `chore: agrega .gitignore` |

---

*Este glosario crece con el tiempo. ¿Falta una palabra? Propónla abriendo un **issue** en este repositorio.*

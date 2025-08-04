Los **alias** en Git te permiten crear **comandos personalizados** para ahorrar tiempo. Puedes definir tanto **alias simples** (abreviaciones) como **alias complejos** (con múltiples comandos).

---

## 📌 **Tipos de Alias en Git**

1. **Alias Locales**: Solo funcionan en tu repositorio actual (se guardan en `.git/config`).
    
2. **Alias Globales**: Funcionan en **todos** tus proyectos (se guardan en `~/.gitconfig`).
    

---

## 🛠 **Cómo Crear Alias**
```sh

git config alias.s "status -s"  # Ahora `git s` equivale a `git status -s`
```

### 2️⃣ **Alias Globales** (para todos tus proyectos)



```sh
git config --global alias.co "checkout"  # `git co` en vez de `git checkout`

```
---

## 🔥 **Alias Útiles que Debes Conocer**

### 📌 **Básicos (Abreviaciones)**

|Alias|Comando Original|Uso|
|---|---|---|
|`git co`|`git checkout`|Cambiar de rama|
|`git br`|`git branch`|Listar ramas|
|`git ci`|`git commit`|Hacer commit|
|`git st`|`git status -s`|Estado resumido|
|`git lg`|`git log --oneline --graph --decorate`|Historial visual|

### 📌 **Avanzados (Combinaciones)**

|Alias|Comando Original|Descripción|
|---|---|---|
|`git unstage`|`git reset HEAD --`|Sacar del staging|
|`git last`|`git log -1 HEAD`|Ver último commit|
|`git undo`|`git reset --soft HEAD~1`|Deshacer último commit (sin perder cambios)|
|`git wip`|`git add . && git commit -m "WIP"`|Guardar cambios temporales (Work In Progress)|
|`git cleanup`|`git branch --merged \| grep -v "main" \| xargs git branch -d`|Borrar ramas ya mergeadas (excepto `main`)|

---

## 📝 **Cómo Definir Alias Manualmente**

Edita tu archivo de configuración global (`~/.gitconfig`) y añade una sección `[alias]`:



```ini
[alias]
    co = checkout
    br = branch
    ci = commit
    st = status -s
    unstage = reset HEAD --
    last = log -1 HEAD
    lg = log --oneline --graph --decorate --all
```

---

## 🔍 **Cómo Listar Tus Alias Existentes**



```sh
git config --get-regexp alias  # Muestra todos los alias definidos
```
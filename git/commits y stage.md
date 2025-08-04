## **Área de Staging (Preparación de Cambios)**

El **staging area** es una "zona intermedia" donde seleccionas qué cambios quieres incluir en tu próximo commit.

###  **COMANDOS BÁSICOS DEL STAGING ÁREA**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git add <archivo>`|Añade un archivo específico al staging|`git add index.html`|
|`git add .`|Añade todos los archivos modificados/eliminados en el directorio actual (excepto nuevos no trackeados)|`git add .`|
|`git add -A`|Añade **todos** los cambios en el repositorio (incluyendo nuevos archivos)|`git add -A`|
|`git add -u`|Añade solo archivos **trackeados** (modificados/eliminados, omite nuevos)|`git add -u`|

---

###  **COMANDOS AVANZADOS DE STAGING**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git add -p`|Modo interactivo: permite seleccionar porciones de cambios ("hunks") para staging|`git add -p`|
|`git add -i`|Entorno interactivo con menú para staging|`git add -i`|
|`git add --patch <archivo>`|Igual que `-p` pero para un archivo específico|`git add --patch script.js`|

---

###  **QUITAR ARCHIVOS DEL STAGING**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git reset <archivo>`|Saca un archivo del staging (**pero mantiene los cambios**)|`git reset config.yml`|
|`git restore --staged <archivo>`|Versión moderna (Git 2.23+) para sacar del staging|`git restore --staged .env`|
|`git reset HEAD <archivo>`|Forma clásica (equivalente a los anteriores)|`git reset HEAD logo.png`|

---

###  **COMPARAR CAMBIOS EN STAGING**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git diff --staged`|Muestra diferencias entre el staging y el último commit|`git diff --staged`|
|`git diff --cached`|Sinónimo de `--staged`|`git diff --cached`|

---

### **CASOS ESPECIALES**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git add *.js`|Añade todos los archivos con extensión `.js`|`git add src/*.js`|
|`git add "*.txt"`|Añade archivos `.txt` en todos los subdirectorios|`git add "**/*.txt"`|
|`git add -f <archivo>`|Fuerza el add de un archivo ignorado (en `.gitignore`)|`git add -f debug.log`|

## **Commits (Guardar Cambios)**

Un **commit** es un "snapshot" (foto) de los cambios que están en el staging area, con un mensaje descriptivo.

### **COMANDOS BÁSICOS DE COMMITS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git commit -m "mensaje"`|Crea un commit con los cambios en staging|`git commit -m "Fix login bug"`|
|`git commit -am "mensaje"`|Añade cambios de archivos **trackeados** y hace commit (evita `git add`)|`git commit -am "Update styles"`|
|`git commit --allow-empty -m "mensaje"`|Crea un commit sin cambios (útil para triggers o CI/CD)|`git commit --allow-empty -m "Trigger deploy"`|

---

###  **MODIFICAR COMMITS EXISTENTES**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git commit --amend`|**Edita el último commit** (cambia mensaje o añade más archivos)|`git commit --amend -m "New message"`|
|`git commit --amend --no-edit`|Añade cambios al último commit **sin modificar el mensaje**|`git add file2.txt && git commit --amend --no-edit`|
|`git rebase -i HEAD~3`|**Reescribe múltiples commits** (interactivo)|`git rebase -i HEAD~3`|

---

###  **INSPECCIONAR COMMITS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git log`|Muestra el historial de commits|`git log --oneline`|
|`git show <commit-hash>`|Muestra cambios de un commit específico|`git show abc123`|
|`git diff <commit1> <commit2>`|Compara diferencias entre commits|`git diff HEAD~2 HEAD`|

---

###  **DESHACER COMMITS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git reset --soft HEAD~1`|**Deshace el último commit** pero mantiene cambios en staging|`git reset --soft HEAD~1`|
|`git reset --mixed HEAD~1`|Deshace commit y saca cambios del staging (por defecto)|`git reset HEAD~1`|
|`git reset --hard HEAD~1`|**Elimina por completo el último commit** (¡peligroso!)|`git reset --hard HEAD~1`|
|`git revert <commit-hash>`|Crea un **nuevo commit** que deshace cambios previos|`git revert abc123`|

---

### **COMMITS ESPECIALES**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git commit --fixup=<commit>`|Crea un commit marcado como "fix" para otro commit (usar con `rebase --autosquash`)|`git commit --fixup=abc123`|
|`git commit --squash=<commit>`|Similar a `--fixup` pero permite editar el mensaje|`git commit --squash=abc123`|

---

### **TRABAJO CON TAGS**

| Comando                        | Descripción                             | Ejemplo                              |
| ------------------------------ | --------------------------------------- | ------------------------------------ |
| `git tag -a v1.0 -m "Release"` | Crea un tag anotado en el último commit | `git tag -a v1.0 -m "First release"` |
| `git tag -d v1.0`              | Elimina un tag local                    | `git tag -d v1.0`                    |
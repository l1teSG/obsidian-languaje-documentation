Una **rama** (o _branch_) en Git es una **línea independiente de desarrollo** que te permite trabajar en nuevas características, experimentos o correcciones **sin afectar el código principal** (generalmente la rama `main` o `master`).

Es como una **versión paralela** de tu proyecto donde puedes hacer cambios libremente y luego decidir si los fusionas (_merge_) con la rama principal o no.

## **COMANDOS BÁSICOS DE RAMAS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git branch`|Lista **todas las ramas locales** (la actual aparece con `*`)|`git branch`|
|`git branch -a`|Lista **todas las ramas (locales + remotas)**|`git branch -a`|
|`git branch <nombre>`|Crea una nueva rama (**pero no cambia a ella**)|`git branch feature-login`|
|`git checkout <rama>`|Cambia a otra rama|`git checkout main`|
|`git switch <rama>`|Alternativa moderna a `checkout` (Git 2.23+)|`git switch feature-login`|
|`git checkout -b <rama>`|Crea una rama **y cambia a ella** (atalho)|`git checkout -b hotfix`|
|`git switch -c <rama>`|Versión moderna del comando anterior|`git switch -c dev`|
|`git branch -d <rama>`|**Elimina** una rama local (solo si está mergeada)|`git branch -d old-feature`|
|`git branch -D <rama>`|Fuerza eliminación (aunque no esté mergeada)|`git branch -D experiment`|

---

## **TRABAJAR CON RAMAS REMOTAS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git fetch`|Descarga ramas remotas **sin fusionarlas**|`git fetch origin`|
|`git pull origin <rama>`|Descarga cambios y fusiona con tu rama actual|`git pull origin main`|
|`git push -u origin <rama>`|Sube una rama local al remoto (**primera vez**)|`git push -u origin feature`|
|`git push origin --delete <rama>`|Elimina una rama **remota**|`git push origin --delete old-branch`|
|`git branch --track <local> <remota>`|Crea una rama local que rastrea una remota|`git branch --track dev origin/dev`|

---

## **FUSIONAR (MERGEAR) RAMAS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git merge <rama>`|Fusiona una rama con la actual|`git merge feature`|
|`git merge --abort`|Cancela un merge con conflictos|`git merge --abort`|
|`git merge --no-ff <rama>`|Fuerza un commit de merge (evita "fast-forward")|`git merge --no-ff hotfix`|
|`git rebase <rama>`|Reorganiza commits sobre otra rama (**reescribe historia**)|`git rebase main`|
|`git rebase --abort`|Cancela un rebase en progreso|`git rebase --abort`|

---

## **INSPECCIONAR RAMAS**

|Comando|Descripción|Ejemplo|
|---|---|---|
|`git log --graph --oneline`|Muestra el historial con gráfico de ramas|`git log --graph --oneline`|
|`git show-branch`|Compara ramas visualmente|`git show-branch`|
|`git branch --merged`|Lista ramas **ya mergeadas** con la actual|`git branch --merged`|
|`git branch --no-merged`|Lista ramas **no mergeadas**|`git branch --no-merged`|

---
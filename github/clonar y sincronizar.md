### **Clonar un repositorio (descargarlo a tu máquina)**

Clonar significa **copiar un repositorio remoto** (de GitHub) a tu computadora local.

#### **Pasos**:

1. **Ve al repositorio en GitHub** que quieras clonar.
    
2. **Haz clic en el botón verde "Code"** y copia la URL (HTTPS o SSH, según tu configuración).  
    Ejemplo:

```sh
    git clone https://github.com/usuario/repositorio.git
```
    
3. **Abre tu terminal** (Git Bash, Terminal, CMD) y ejecuta:
    
    
```sh
    
    git clone <URL-del-repositorio>
    
    Esto creará una carpeta local con el proyecto.
```
    

#### **Opciones útiles**:

- Clonar en una carpeta específica:
    

    
```sh
    git clone https://github.com/usuario/repositorio.git mi-carpeta
```
    
- Usar SSH (si configuraste claves):
    
    
    
```sh
    git clone git@github.com:usuario/repositorio.git
```
    

---

### **Sincronizar cambios (entre tu repositorio local y GitHub)**

Para mantener tu copia local actualizada con los cambios del repositorio remoto (o viceversa), debes usar estos comandos:

#### **🔹 Traer cambios desde GitHub a tu repositorio local**

Si otros colaboradores hicieron cambios en GitHub y quieres actualizar tu copia local:



```sh
git pull origin <rama-principal>  # Normalmente "main" o "master"
```

Esto combina `git fetch` (descarga cambios) + `git merge` (los fusiona localmente).

#### **🔹 Enviar cambios locales a GitHub**

Si modificaste archivos localmente y quieres subirlos:

1. **Agrega los cambios al área de staging**:
    
    
    
```js
    git add .  # Agrega todos los archivos modificados
    # o
    git add archivo.txt  # Agrega un archivo específico
```
    
2. **Haz un commit** (registra los cambios):
    
 
```sh
    
    git commit -m "Descripción de los cambios"
```
    
3. **Sube los cambios a GitHub**:
    
    
```sh
    
    git push origin <nombre-de-la-rama>
```

### **Diferencia entre `git fetch` y `git pull`**

|Comando|Descarga cambios|Fusiona automáticamente|Modifica tu código local|
|---|---|---|---|
|`git fetch`|✅ Sí|❌ No|❌ No|
|`git pull`|✅ Sí|✅ Sí (`git merge`)|✅ Sí|

👉 **`git pull = git fetch + git merge`**
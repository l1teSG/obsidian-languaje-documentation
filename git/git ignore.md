El archivo **`.gitignore`** permite especificar qué archivos o carpetas **no** deben ser rastreados por Git. Es útil para excluir archivos generados automáticamente (como logs, binarios o configuraciones locales).
se puede crear uno global 

---

###  **¿Cómo funciona?**

1. Git verifica el archivo `.gitignore` antes de añadir archivos al staging area.
    
2. Si un archivo/carpeta coincide con un patrón en `.gitignore`, Git lo **ignora**.
    
3. Se puede crear un `.gitignore` **global** (para todos los proyectos) o **local** (solo para el repositorio actual).
    

---

### 📂 **Estructura Básica de un `.gitignore`**



```plaintext
# Comentario (líneas que empiezan con "#")

# Ignorar un archivo específico
config.local.json

# Ignorar una carpeta completa
node_modules/
bin/

# Ignorar todos los archivos con cierta extensión
*.log
*.tmp

# Excepción (no ignorar un archivo aunque coincida con un patrón anterior)
!important.log
```

---

### 🔹 **Patrones comunes en `.gitignore`**

|Patrón|Ejemplo|Descripción|
|---|---|---|
|`/carpeta`|`/dist/`|Ignora solo la carpeta **en la raíz**.|
|`carpeta/`|`temp/`|Ignora la carpeta **en cualquier ubicación**.|
|`*.ext`|`*.exe`|Ignora todos los archivos con esa extensión.|
|`!`|`!main.js`|**Excepción**: No ignores este archivo.|
|`**/`|`**/__pycache__/`|Ignora la carpeta **en todos los subdirectorios**.|

---

### 📌 **¿Dónde colocar el `.gitignore`?**

- **En la raíz del proyecto** (junto al directorio `.git/`).
    
- Puedes tener múltiples archivos `.gitignore` en subcarpetas si necesitas reglas específicas.


### **Estructura básica**

gitignore

# Líneas que empiezan con '#' son comentarios

patrón1  # Ignora archivos/carpetas que coincidan con este patrón
!patrón2 # Excepción: NO ignores esto aunque coincida con un patrón anterior

---

###  **Tipos de patrones** 

1. **Ignorar por nombre exacto**
``` gitignore
    
   
    
    config.ini       # Ignora el archivo 'config.ini' en cualquier carpeta
    /config.ini      # Solo ignora 'config.ini' en la RAIZ del proyecto
    
```
1. **Ignorar por extensión**
    
   
    
``` gitignore
    *.log            # Ignora TODOS los archivos .log (error.log, app.log, etc.)
    *.tmp            # Ej: temp.tmp, cache.tmp
    
```
1. **Ignorar carpetas completas**
    
    
```gitignore
    
    node_modules/    # Ignora la carpeta 'node_modules' en cualquier ubicación
    /build/          # Solo ignora '/build/' en la raíz (no en subcarpetas)
```
    
2. **Patrones con wildcards**
    

```    gitignore
    
    temp-*           # Ignora temp-1.txt, temp-backup/, etc.
    *.?xt            # Ignora .txt, .ext, pero no .text
```
    
3. **Excepciones (!)**
    
    
    
```gitignore
    *.log            # Ignora todos .log
    !important.log   # PERO no ignores este archivo específico
```
    
4. **Doble asterisco (`**`)** (subdirectorios anidados)
    
    
```gitignore    
    **/logs/         # Ignora 'logs/' en cualquier nivel: /logs, /app/logs, /a/b/c/logs
    **/*.cache       # Ignora archivos .cache en cualquier subcarpeta
```
    

---

### 📂 **Estructura jerárquica**

Puedes tener **múltiples archivos `.gitignore`** en diferentes carpetas:


```

proyecto/
│
├── .gitignore          # Reglas globales
├── app/
│   └── .gitignore      # Reglas específicas para /app
└── tests/
    └── .gitignore      # Reglas para /tests
```
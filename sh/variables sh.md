 **Las variables en Shell Scripting (`sh`/`bash`) son fundamentales** para almacenar datos, manipular información y hacer scripts dinámicos. Aquí te explico **desde cero** cómo funcionan, con ejemplos claros y prácticos:

---

## **1. ¿Qué es una Variable en Shell?**

Es un "contenedor" que guarda un valor (texto, números, rutas, etc.) para usarlo después en el script.

- **No tienen tipo** (todos los datos son tratados como texto).
    
- **Sensible a mayúsculas** (`Nombre` y `nombre` son diferentes).
## **2. Sintaxis Básica**

### **Asignar una Variable**
```sh
nombre="Ana"   # Sin espacios alrededor del =
edad=25
ruta="/home/usuario"
```
### **Acceder al Valor**

```sh
Usa `$` antes del nombre de la variable:
echo "Hola, $nombre"    # Imprime: Hola, Ana
echo "Tienes $edad años"
```

## **3. Tipos de Variables**

### **A. Variables Locales (solo en el script actual)**


```sh

animal="perro"
echo "Mi $animal"  # Imprime: Mi perro
```

### **B. Variables de Entorno (globales en el sistema)**


```sh

echo "Tu usuario es: $USER"      # USER es una variable del sistema
echo "Tu terminal es: $TERM"
```

 **Listar todas las variables de entorno**:



```sh
printenv   # o también: env
```

### **C. Variables Especiales**

|Variable|Descripción|Ejemplo|
|---|---|---|
|`$0`|Nombre del script|`echo "Script: $0"`|
|`$1`, `$2`, ...|Argumentos pasados al script|`echo "Primer argumento: $1"`|
|`$#`|Número de argumentos|`echo "Total de argumentos: $#"`|
|`$?`|Estado del último comando (0 = éxito)|`ls && echo "Estado: $?"`|

---
##  **4. Operaciones con Variables**

### **Concatenación**



```sh
saludo="Hola"
nombre="Carlos"
mensaje="$saludo, $nombre"
echo "$mensaje"   # Imprime: Hola, Carlos
```

### **Longitud de una Cadena**



```sh
texto="Shell Script"
echo "${#texto}"  # Imprime: 12 (caracteres)
```

### **Substrings (extraer parte del texto)**



```sh
fruta="manzana"
echo "${fruta:0:3}"  # Imprime: man (desde posición 0, 3 caracteres)
```
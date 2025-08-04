# Argumentos sh
Los argumentos permiten que tus scripts sean dinámicos, aceptando datos de entrada cuando los ejecutas. Son esenciales para hacer herramientas flexibles y reutilizables.

## **📌 1. Argumentos Básicos (`$1`, `$2`, ..., `$9`)**

Cada argumento pasado al script se almacena en variables especiales:

|Variable|Descripción|
|---|---|
|`$0`|Nombre del script|
|`$1`|Primer argumento|
|`$2`|Segundo argumento|
|`...`|...|
|`$9`|Noveno argumento|

### **Ejemplo: `saludo.sh`**

```sh
#!/bin/sh
echo "Script: $0"
echo "Hola, $1"
```

**Ejecución**:

```sh
chmod +x saludo.sh
./saludo.sh Juan

```
**Salida**:

```sh

Script: ./saludo.sh
Hola, Juan
```

---

## **2. Todos los Argumentos (`$@` y `$*`)**

- `$@`: Lista todos los argumentos como elementos separados.
    
- `$*`: Lista todos los argumentos como una sola cadena.

### **Ejemplo: `todos_args.sh`**

```sh
#!/bin/sh
echo "Argumentos individuales (@):"
for arg in "$@"; do
  echo "- $arg"
done

```
echo "Todos como una cadena (*): $*"

**Ejecución**:

```sh
./todos_args.sh uno dos tres

```
**Salida**:

```text
Argumentos individuales (@):
- uno
- dos
- tres
Todos como una cadena (*): uno dos tres
```

---

## **3. Número de Argumentos (`$#`)**

Muestra cuántos argumentos se pasaron al script.

### **Ejemplo: `contar_args.sh`**

```sh
#!/bin/sh
echo "Total de argumentos: $#"
```

**Ejecución**:

```sh
./contar_args.sh a b c d
```

**Salida**:

```text
Total de argumentos: 4

```
---

## **4. Desplazamiento de Argumentos (`shift`)**

Elimina el primer argumento y desplaza los demás (útil para procesar múltiples args en un bucle).

### **Ejemplo: `shift_args.sh`**

sh

#!/bin/sh
while [ "$#" -gt 0 ]; do
  echo "Argumento actual: $1"
  shift   # Elimina $1 y desplaza los demás
done

**Ejecución**:

```sh
./shift_args.sh manzana banana naranja

```
**Salida**:

t
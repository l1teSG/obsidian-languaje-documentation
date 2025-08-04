lo primero que se debe hacer es configurar git 

## configurar correo y nombre

Git necesita saber quién hace los commits. Ejecuta estos comandos (**reemplaza con tus datos**):

```sh
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

## editor de texto 
```sh 
git config --global core.editor "nvim --wait"
```

## para ver la lista de configuraciones 
```sh
git config --list
```
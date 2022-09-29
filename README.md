# Tools

**Todas las herramientas utilizadas en Arch Linux y Kubuntu**

## Conectar un repositorio local con SSH

Antes de generar una llave ssh se debe verificar si el email y el nombre está configurado
```bash
git config -l
```
En caso de no estarlo, se condigura con: 
```bash
git config --global user.email marioriascos1201@gmail.com
git config --global user.name Mario Riascos
```
Cómo generar tus llaves SSH
1. Generar tus llaves SSH**

Recuerda que es muy buena idea proteger tu llave privada con una contraseña.
```bash
ssh-keygen -t rsa -b 4096 -C "tu@email.com"
```
2. Terminar de configurar nuestro sistema.
En Windows y Linux:

Encender el “servidor” de llaves SSH de tu computadora:
```bash
eval $(ssh-agent -s)
```
Añadir tu llave SSH a este “servidor”:
```bash
ssh-add ruta-donde-guardaste-tu-llave-privada
```

# Conexión a GitHub con SSH 

La creación de las SSH es necesario solo una vez por cada computadora. Aquí conocerás cómo conectar a GitHub usando SSH.

Luego de crear nuestras llaves SSH podemos entregarle la llave pública a GitHub para comunicarnos de forma segura y sin necesidad de escribir nuestro usuario y contraseña todo el tiempo.

Para esto debes entrar a la Configuración de Llaves SSH en GitHub, crear una nueva llave con el nombre que le quieras dar y el contenido de la llave pública de tu computadora.

Ahora podemos actualizar la URL que guardamos en nuestro repositorio remoto, solo que, en vez de guardar la URL con HTTPS, vamos a usar la URL con SSH:
```bash
git remote set-url origin url-ssh-del-repositorio-en-github
```

# Tools

**Todas las herramientas utilizadas en Arch Linux y Kubuntu**

**Table**
- [Conectar un Repositorio Local con SSH](#conectar-un-repositorio-local-con-ssh)
- [Conexión a Github con SSH](#conexión-a-github-con-ssh)
- [Cómo autenticarte en GitHub 2022](#cómo-autenticarte-en-github-2022)




# Conectar un repositorio local con SSH

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

# Cómo autenticarte en GitHub 2022

Antes de empezar debemos renombrar la rama ‘máster’ a ‘main’, este es el nuevo estándar en GitHub, para esto:

Primero nos posicionamos en la rama a la que queremos cambiarle el nombre.
Ejecutamos el siguiente comando: git branch -M main
Pasos para crear un token de acceso personal.

Desde el 2022 GitHub ya no deja hacer el push con la contraseña del propio GitHub, para esto tenemos que crear un token, y este token es la contraseña que vamos a colocar cuando nos pida clave

Seguir la secuencia: Ingresamos a nuestra cuenta de GitHub.

Buscamos Settings
Click en Developer settings
Click en Personal access tokens
Click en Generate new token aquí se puede colocar un nombre, la fecha de expiración.
Tildar en repo y luego click en el botón verde Generate token

# Personalizar la Terminal de Comandos 

Comando para dejar por DEFECTO la shell de bash o zsh:
```bash
$ chsh -s $(which bash)

$ chsh -s $(which zsh)
```
## Usa Power Level
Vamos a instalarle un tema (powerLevel10K):
```bash
$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
después vamos a entrar al archivo .zshrc:
```bash
$ vim ~/.zshrc
```
buscamos y cambiamos la parte que dice ZSH_THEME por esto:
```bash
$ ZSH_THEME="powerlevel10k/powerlevel10k"
```
Guardamos y salimos.

Después instalamos estas 4 fuentes de texto 1 2 3 4

Cuando salgamos y volvamos a entrar a la terminal nos va a salir el wizard de powerlevel10k para configurar la terminal como quieras, simplemente sigue los pasos.

Para volver a configurar el tema Powerlevel10k desde el principio en caso de que quieras cambiar algo:
```bash
$ p10k configure
```
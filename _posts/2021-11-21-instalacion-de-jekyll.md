---
layout: single
title: Instalación de Jekyll en Windows y Linux
date: 2021-11-21
classes: wide
header:
  teaser: /assets/images/instalacion-de-jekyll/jekyll-logo-dark-solid.jpg
categories:
  - guia
tags:
  - blog  
  - jekyll
  - windows
---
![](/assets/images/instalacion-de-jekyll/jekyll-logo-dark-solid.jpg)

Jekyll es un generador de páginas estáticas, mediante plantillas y ficheros estáticos, actualmente se utiliza para creación de blogs con mejores resultados de tiempo de respuesta con algunos otros gestores de blogs o sitios web como serian WordPress, Wix, Blogger, entre otros. Está escrito en Ruby y fue desarrollado por Tom Preston-Werner, uno de los cofundadores de GitHub.

Jekyll es utilizado como el motor de creación de todas las páginas que se sirven en GitHub Pages.

Jekyll no utiliza una base de datos para almacenar el contenido como hacen los CMS o Gestores de Contenidos tradicionales, si no que el contenido de nuestra web se define mediante ficheros de texto en formatos markdown.

### ¿Qué podemos hacer con Jekyll?

Crear páginas web o entradas post:
1. Agrupar las entradas o post en categorias.
2. Definir etiquetas para las páginas o las entradas.
3. Asociar un usuario a cada uno de los contenidos.
4. Asignar una fecha de creación a cada uno de los contenidos.
5. Podemos personalizar los enlaces permanentes para cada uno de los contenidos.
6. Podemos crear un buscador de contenidos.

## ¿Como instalar Jekyll en Windows?

La forma mas sencilla de instalar Jekyll en Windows es mediante `Chocolatey`

### Instalando Chocolatey
#### 1. Ingresar a la `Windows PowerShell` como `administrador`
#### 2. Ejecutar 
```bash
> Get-ExecutionPolicy
```
Si la respuesta `Restricted` entonces tenemos que ejecutar el siguiente comando

```bash
> Set-ExecutionPolicy AllSigned
```
ó
```bash
> Set-ExecutionPolicy Bypass -Scope Process
```
Nuevamente podríamos ejecutar `Get-ExecutionPolicy` para obtener la respuesta de `AllSigned`

#### 3. Ejecutar
```bash
> Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Esperamos unos minutos para que termine de ejecutar el comando

#### 4. Al completar la instalación podemos comprobar la instalación con el comando 
```bash
> choco -v
```
Obtendremos la versión instalada de Chocolatey

### Instalando Jekyll
Según la documentación de Chocolatey deberiamos usar `choco install jekyll`, personalmente este comando no me logra instalar todas las dependencias de Jekyll y obtengo errores. Por ello ejecutaremos:
```bash
> gem install jekyll bundler 
```
Esperamos unos minutos a que acabe de instalar todas las dependencias que necesita e incluyendo Jekyll.

Al culminar la instalación podremos comprobar la instalación con el comando 
```bash
> jekyll -v
```
Obtendremos la versión instalada de Jekyll

### ¡Importante!
Para que podamos ejecutar nuestra plantilla de Jekyll necesitamos agregar
```bash
> bundle add webrick
```
Una vez agregado `webrick`, necesitamos actualizar nuestro `bundle`
```bash
> bundle update
```
Esto llega a tardar muchos minutos (20 - 40 min.)

¡Listo! ya tendriamos nuestro Jekyll en Windows para ejecutarlo de manera local

## ¿Como instalar Jekyll en Linux?
La instalación en Linux se encuentra en el siguiente enlace dependiendo la distribución que use 

### Fedora
```bash
> sudo dnf install ruby ruby-devel openssl-devel redhat-rpm-config @development-tools
```
### RHEL8/CentOS8
```bash
> sudo dnf install ruby ruby-devel
> sudo dnf group install "Development Tools"
```
### Debian
```bash
> sudo apt-get install ruby-full build-essential
```
### Gentoo
```bash
> sudo emerge -av jekyll
```
ó
```bash
> sudo emerge --ask --verbose jekyll
```
### ArchLinuxPermalink
```bash
> sudo pacman -S ruby base-devel
```
### OpenSUSE
```bash
> sudo zypper install -t pattern devel_ruby devel_C_C++
> sudo zypper install ruby-devel
```
### OpenSUSE
```bash
> sudo swupd bundle-add ruby-basic
```

##### Referencia 
[https://jekyllrb.com/docs/installation/other-linux](https://jekyllrb.com/docs/installation/other-linux)

## Comentario

Recomiendo los siguientes templates, no olviden realizar mediante un `fork` para poder apoyar a su creador
* [http://joshgerdes.com/jekyll-uno](http://joshgerdes.com/jekyll-uno)
* [http://pavelmakhov.com/jekyll-clean-dark](http://pavelmakhov.com/jekyll-clean-dark)
* [https://taylantatli.github.io/Halve](https://taylantatli.github.io/Halve)
* [http://taylantatli.github.io/Moon](http://taylantatli.github.io/Moon)
* [https://le4ker.github.io/personal-jekyll-theme](https://le4ker.github.io/personal-jekyll-theme)
* [https://yizeng.github.io/jekyll-theme-simple-texture](https://yizeng.github.io/jekyll-theme-simple-texture)
* [https://nrandecker.github.io/particle](https://nrandecker.github.io/particle)
* [https://victorvoid.me/space-jekyll-template](https://victorvoid.me/space-jekyll-template)
* [https://codeasashu.github.io/hcz-jekyll-blog](https://codeasashu.github.io/hcz-jekyll-blog)
* [https://hydejack.com/blog](https://hydejack.com/blog)
* [https://supunkavinda.github.io/jekyll-theme-leaf](https://supunkavinda.github.io/jekyll-theme-leaf)
* [https://chirpy.cotes.info](https://chirpy.cotes.info)
* [https://longpdo.github.io/neumorphism](https://longpdo.github.io/neumorphism)

Este blog fue desarrollado mediante este template
* [https://slemire.github.io](https://slemire.github.io)
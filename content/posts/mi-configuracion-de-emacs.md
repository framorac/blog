---
title: "Mi configuración de Emacs"
date: 2021-01-30T19:50:10-03:00
draft: true
tags: ['emacs']
---
## ¿Por qué uso Emacs?
[Emacs](https://www.gnu.org/software/emacs/) es uno de los mejores editores de texto que conozco, aunque lo de *editor de texto* queda muy corto. Con **Emacs** puedes hacer prácticamente de todo lo que imagines. **Emacs** puede ser tu navegador web, tu IDE para programar, tu herramienta de control de tiempo, una aplicacion de To-Do, un reproductor de música, tu sistema operativo(sí, tu sistema operativo). **Emacs** es parte del proyecto [GNU](https://www.gnu.org/ "GNU") desarrollado en 1975 por [Richard Stallman](https://es.wikipedia.org/wiki/Richard_Stallman "Richard Stallman"), en un principio fue un interprete de [LISP](https://es.wikipedia.org/wiki/Emacs_Lisp "LISP"), el cual, se ha ido nutriendo de un sin fin de nuevas caracteristicas a través de los años. Actualmente es considerado junto con [VIM](https://es.wikipedia.org/wiki/Vim "VIM") uno de los editores de texto más potentes que existen (aunque esto no significa sencillo de aprender).

Hace unos 5 años atrás comencé a usar **Emacs** como mi editor preferido para programar **PHP** en esos tiempos, pero no fue hasta que conocí [Org-Mode](https://orgmode.org/ "Org-Mode") donde me olvidé por completo de [Sublime Text](https://www.sublimetext.com/ "Sublime Text"). Ahora uso **Emacs** para programar en **Ruby On Rails**, **PHP**, **Javascript**, **Python** y como mi herramienta **GTD** para organizar mi vida, proyectos y que haceres.

Es por eso que a continuación te muestro mi configuración por si te ánimas a probar el mejor editor que existe[^1].

## Instalación

**Emacs** está desarrollado para sacar toda su potencia en sistemas operativos [GNU/Linux](https://www.gnu.org/gnu/linux-and-gnu.html "GNU/Linux"), aunque existen versiones para sistemas **Windows**, **MacOS** y **BSDs** veamos como instalar en cada uno:

### GNU/Linux
En el sistema del pingüino *emacs* se encuentra en los repositorios[^2] oficiales de cada distribución y lo único que debes tener en cuenta es la versión disponible en estos repositorios, por ejemplo para instalar en:

#### Archlinux
```bash
sudo pacman -S emacs
```
#### Debian y derivadas
```bash
sudo apt install emacs-gtk
```
#### Fedora
```bash
sudo dnf install emacs
```
#### Void Linux
```bash
sudo xbps-install emacs
```
### BSDs
#### FreeBSD
```bash
pkg install emacs-devel
```
### MacOS
#### Homebrew
```bash
brew cask install emacs
```
#### MacPorts
```bash
sudo port install emacs-app
```
### Windows
En windows basta descargar el ejecutable ```.exe``` desde un [GNU Mirror](http://ftpmirror.gnu.org/emacs/windows "Emacs Windows Download") y seguir el proceso de instalación.

## Configuración
Los archivos de configuración de **emacs** deben tener la extensión ```.el``` y se ubican dentro de la carpeta ```.emacs.d```, la cual, está oculta en tu directorio personal(fijate en el punto inicial). En windows esta carpeta se encuentra en la ruta ```C:\Users\username\AppData\Roaming```

[^1]: Esta es una opinión personal y puede que no estes de acuerdo conmigo.

[^2]: Siempre existe la opción de compilar desde los archivos fuentes, pero no es recomendable para alguien que no tiene experiencia en este proceso.

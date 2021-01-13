---
title: "Instalar JDK para desarrollo en Java"
date: 2021-01-11T23:24:54-03:00
tags: ['java']
draft: true
---
## Introducción

Para comenzar a desarrollar con el lenguaje de programación **Java** es necesario instalar un software denominado **JDK** o **Java Development Kit**, la cual, nos provee de algunas herramientas necesarias para la creación de programas en este lenguaje de programación tan utilizado en la actualidad. Entre las herramientas que nos provee **JDK** podemos nombrar a:

1. **JRE** o *Java Runtime Environment*, la cual, nos permite ejecutar aplicaciones en este lenguaje.
2. **Java Virtual Machine** máquina virtual de Java.
3. **API Java** contiene todas las librerias del lenguaje.

**JDK**, **JRE** y **JVM** son los denominados corazón[^1] de Java y la instalación es obligatoria si queremos desarrollar aplicaciones. En cambio, si sólo deseamos ejecutar aplicaciones basta con instalar solamente el **JRE**.

## Versiones de JDK

En la actualidad 2 son las versiones de JDK oficialmente soportadas, en primer lugar el **JDK** oficial de [**Oracle Java**](https://www.oracle.com/java/)(dueña de las licencias del lenguaje) y en segundo lugar tenemos la versión comunitaria denominada [**OpenJDK**](https://openjdk.java.net/), la cual, es un esfuerzo colaborativo y open-source de la plataforma Java.

### ¿Cúal versión debo elegir?

En pocas palabras, dependerá de tu sistema operativo y si tu desarrollo tiene interés comercial, podrías seguir la siguiente lógica:

+ Desarrollo personal, sistema operativo Windows, sin fines comerciales usa *JDK OFICIAL* u *OpenJDK*.
+ Desarrollo personal, sistema operativo Windows, con fines comerciales usa *OpenJDK*.
+ Desarrollo personal, sistemas **UNIX**, **BSD**, **GNU/Linux**, cualquier fin usa siempre *OpenJDK*
+ Desarrollo empresarial con fines comerciales, lo mejor es usar *JDK OFICIAL* y pagar las licencias correspondientes para obtener además soporte oficial por parte de Oracle. Aunque siempre puedes usar *OpenJDK* si el soporte no es prioritario para tu proyecto.

## Instalar JDK Oficial

La instalación del *JDK OFICIAL* de Oracle es la siguiente:

### Windows
En sistemas Windows basta con:

1. Dirigirse al [centro de descarga de oracle](https://www.oracle.com/java/technologies/javase-downloads.html)
2. Seleccionar ```JDK Download``` de la versión de **Java** que usarás en tu desarrollo, en la actualidad está disponible *JDK 8*, *JDK 11(LTS)* y *JDK 15*.
3. Descargar el instalador *.exe* correspondiente a tu arquitectura.
4. Aceptar la Oracle License.
5. Ejecutar el instalador con los valores por defecto. Esto creará una variable de entorno **PATH** en tu sistema con la ruta ```C:\Program Files\Java\jdk-{numVersion}\bin```.

Para validar la correcta instalación del *JDK* ejecuta en un ```cmd```, lo siguiente:
```shell
C:\Users>java -version
java version "11.0.8" 2020-07-14 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.8+10-LTS)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.8+10-LTS, mixed mode)
```
Si se muestra la información de la versión de Java es por que estamos listos, en caso contrario prueba a reiniciar tu equipo y volver a intentar ejecutar el comando ```java -version```

### GNU/Linux
Para el sistema del pingüino la instalación del *JDK OFICIAL* esta disponible tanto en paquete **.DEB**, **.RPM** y *.TAR.GZ*.

#### Instalador .deb 
Para las distribuciones con paqueteria **.DEB** tales como [**Debian**](https://www.debian.org/) o [**Ubuntu**](https://ubuntu.com/), la instalación sería:

1. Dirigirse al [centro de descarga de oracle](https://www.oracle.com/java/technologies/javase-downloads.html)
2. Seleccionar ```JDK Download``` de la versión de **Java** que usarás en tu desarrollo, en la actualidad está disponible *JDK 8*, *JDK 11(LTS)* y *JDK 15*.
3. Descargar el instalador *jdk-numeroversion_linux-arquitectura_bin.deb* correspondiente a tu arquitectura.
4. Aceptar la Oracle License.
5. Moverse a la carpeta donde se descargó el instalador(asumiendo ~/Descargas)
```bash
$ cd ~/Descargas
```
6. Ejecutar el comando de instalacion para la versión *jdk 15*(cambiar según versión descargada):
```bash
$ sudo dpkg -i jdk-15_linux-x64_bin.deb
```
7. Validar la correcta instalación con el comando ```java --version```

#### Instalador .rpm
Para las distribuciones con paqueteria **.RPM** tales como [**Fedora**](https://getfedora.org/) u [**OpenSuse**](https://www.opensuse.org/), la instalación sería:

1. Dirigirse al [centro de descarga de oracle](https://www.oracle.com/java/technologies/javase-downloads.html)
2. Seleccionar ```JDK Download``` de la versión de **Java** que usarás en tu desarrollo, en la actualidad está disponible *JDK 8*, *JDK 11(LTS)* y *JDK 15*.
3. Descargar el instalador *jdk-numeroversion_linux-arquitectura_bin.rpm* correspondiente a tu arquitectura.
4. Aceptar la Oracle License.
5. Moverse a la carpeta donde se descargó el instalador(asumiendo ~/Descargas)
```bash
$ cd ~/Descargas
```
6. Ejecutar el comando de instalacion para la versión *jdk 15*(cambiar según versión descargada):
```bash
$ sudo rpm -ivh jdk-15_linux-x64_bin.rpm
```
7. Validar la correcta instalación con el comando ```java --version```

#### Archivo fuente .tar.gz
La instalación a través de archivos fuente **.tar.gz** está orientada a usuarios más experimentados. Por ende, si no tienes los conocimientos necesarios te recomiendo siempre usar *.deb* o *.rpm*:

1. Descargamos el archivo fuente con wget.
```bash
$ wget --no-check-certificate -c --header "Cookie: oraclelicense=accept-securebackup-cookie" https://download.oracle.com/otn-pub/java/jdk/15+36/779bf45e88a44cbd9ea6621d33e33db1/jdk-15_linux-x64_bin.tar.gz
```
2. Creamos un directorio para el fuente
```bash
$ sudo mkdir /usr/lib/jvm
```
3. nos movemos al direcetorio creado
```bash
cd /usr/lib/jvm
```
4. Extraemos el contenido del archivo *.tar.gz*
```bash
$ sudo tar -xvzf ~/Descargas/jdk-15_linux-x64_bin.tar.gz
```
5. Editamos el archivo ```/etc/environment```.
```bash
$ sudo nano /etc/environment
```
6. Agregamos a la variable ```PATH``` lo siguiente(tener en cuenta los dos puntos que separa cada directorio):
```bash
/usr/lib/jvm/jdk-15/bin
```
7. Agregamos al final del archivo la variable ```JAVA_HOME```
```bash
JAVA_HOME="/usr/lib/jvm/jdk-15"
```
8. El archivo ```/etc/environment``` debe quedar de la siguiente manera:
```bash
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/jvm/jdk-15/bin"
JAVA_HOME="/usr/lib/jvm/jdk-15"
```
9. Guardamos los cambios realizados con <kbd>Ctrl</kbd>+<kbd>O</kbd> y cerramos con <kbd>Ctrl</kbd>+<kbd>X</kbd>
10. Informaremos al sistema donde se encuentran ubicados los archivos de Java(un comando a la vez):
```bash
$ sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk-15/bin/java" 0
$ sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk-15/bin/javac" 0
$ sudo update-alternatives --set java /usr/lib/jvm/jdk-15/bin/java
$ sudo update-alternatives --set javac /usr/lib/jvm/jdk-15/bin/javac
```
11. Verificamos la configuración correcta del ```PATH```
```bash
$ update-alternatives --list java
$ update-alternatives --list javac
```
12. Reiniciar el equipo o cerrar sesión.
13. Validar la correcta instalación del JDK con el comando ```java --version```.

## Instalar OpenJDK
La instalación de la alternativa open-source **OPENJDK** es de la siguiente manera:

### Windows
Para la instalación de **OPENJDK** en sistemas windows tenemos instaladores oficiales gracias al esfuerzo del equipo de [Adopt OpenJDK](https://adoptopenjdk.net/index.html?variant=openjdk15&jvmVariant=hotspot). Lo que reduce los pasos a los siguientes:

1. Dirigirse a la web de [Adopt Openjdk](https://adoptopenjdk.net/index.html?variant=openjdk15&jvmVariant=hotspot).
2. Seleccionar una versión de *OpenJDK* (8 LTS, 11 LTS, 15 latest).
3. Seleccionar una versión de *JVL* (HotSpot, Eclipse OpenJ9).
4. Desarcargar el archivo **.msi** correspondiente a tu arquitectura(x86 o x64).
5. Ejecutar el instalador **.msi**.
6. Ejecutar el instalador con los valores por defecto. Esto creará una variable de entorno **PATH** en tu sistema con la ruta ```C:\Program Files\OpenJDK\openjdk-{numVersion}\bin```.
7. Reiniciar tu equipo y validar la correcta instalación del OpenJDK con el comando ```java --version```.

### GNU/Linux
En sistemas **GNU/Linux** la tenemos muy sencilla, ya que, *OpenJDK* se encuentra en los repositorios oficiales de la mayoría[^2] de distribuciones conocidas. Por ejemplo:

+ Para Debian y derivadas los comandos de instalación serían:
```bash
$ sudo apt install openjdk-11-jdk
$ export JAVA_HOME=/usr/lib/jvm/openjdk-11-jdk
$ export PATH=$PATH:$JAVA_HOME/bin
$ java --version
java version "11" 2020-**-**
Java(TM) SE Runtime Environment (build 11+36-1461)
Java HotSpot(TM) 64-Bit Server VM (build 11+36-1461, mixed mode, sharing)
```
+ Para Fedora usar lo siguiente:
```bash
$ sudo dnf install java-11-openjdk-devel.x86_64
$ java --version
java version "11" 2020-**-**
Java(TM) SE Runtime Environment (build 11+36-1461)
Java HotSpot(TM) 64-Bit Server VM (build 11+36-1461, mixed mode, sharing)
```
+ Para [Archlinux](https://wiki.archlinux.org) usar:
```bash
$ sudo pacman -Syyu jdk-openjdk
$ source /etc/profile.d/jre.sh
$ java --version
openjdk 15.0.1 2020-10-20
OpenJDK Runtime Environment (build 15.0.1+9)
OpenJDK 64-Bit Server VM (build 15.0.1+9, mixed mode)
```
Y con esto finalizamos la configuración e instalación de **JDK** u **OpenJDK** en tu sistema y solo quedaría elegir un IDE[^3] como [Eclipse](https://www.eclipse.org/ide/) o [IntelliJIDEA](https://www.jetbrains.com/idea/)

[^1]: Esta es una opinión personal y no técnica.
[^2]: Me atrevería a decir que practicamente en todas las distribuciones GNU/Linux está disponible de forma oficial.
[^3]: Entorno de desarrollo integrado.

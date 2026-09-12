# Instalación y configuración de Android Studio + GitHub para PMUL

## Programación Multimedia y Dispositivos Móviles --- DAM

> **Objetivo:** instalar y configurar un entorno común para las
> prácticas del módulo, utilizando Android Studio, Kotlin, Jetpack
> Compose, un emulador Android y un repositorio GitHub llamado `PMUL`.

------------------------------------------------------------------------

## 1. Configuración común del aula

Se utilizará, como referencia, la siguiente configuración:

  Elemento                  Configuración
  ------------------------- -------------------------
  Android Studio            Versión **Stable**
  Lenguaje                  **Kotlin**
  Interfaz                  **Jetpack Compose**
  SDK de compilación        **Android 16 / API 36**
  Target SDK                **API 36**
  Minimum SDK               **API 26**
  Emulador                  **Pixel 8**
  SO del emulador           **Android 16 / API 36**
  Git                       Última versión estable
  Rama principal            `main`
  Repositorio GitHub        `PMUL`
  Visibilidad recomendada   **Private**
  Carpeta local             `C:\DAM\PMUL`

------------------------------------------------------------------------

# PARTE I. ANDROID STUDIO

## 2. Comprobar la virtualización

Antes de instalar Android Studio conviene comprobar que la
virtualización del procesador está activada, ya que el emulador Android
necesita aceleración por hardware.

En Windows:

1.  Pulsar `Ctrl + Shift + Esc`.
2.  Abrir **Administrador de tareas**.
3.  Seleccionar **Rendimiento → CPU**.
4.  Comprobar que aparece:

``` text
Virtualización: Habilitada
```

Si aparece **Deshabilitada**, será necesario activarla desde la
BIOS/UEFI.

Dependiendo del equipo puede aparecer como:

-   Intel Virtualization Technology / Intel VT-x.
-   AMD-V.
-   SVM Mode.

------------------------------------------------------------------------

## 3. Activar Windows Hypervisor Platform

1.  Abrir el menú **Inicio**.
2.  Buscar:

``` text
Activar o desactivar las características de Windows
```

3.  Abrir la herramienta.
4.  Localizar:

**Plataforma del hipervisor de Windows**\
o **Windows Hypervisor Platform**.

5.  Marcar la casilla.
6.  Pulsar **Aceptar**.
7.  Reiniciar el ordenador si Windows lo solicita.

------------------------------------------------------------------------

## 4. Descargar Android Studio

Acceder a la página oficial de Android Developers:

https://developer.android.com/studio

Descargar siempre la versión:

**Stable**

Para los ordenadores habituales del aula con Windows de 64 bits,
utilizar el:

**Instalador `.exe` para Windows de 64 bits**

No utilizar para las clases:

-   Canary.
-   Nightly.
-   Beta.
-   Release Candidate.

> **Importante:** todos los alumnos deberían utilizar la misma versión
> estable durante las prácticas, siempre que sea posible.

------------------------------------------------------------------------

## 5. Ejecutar el instalador

1.  Ejecutar el archivo `.exe` descargado.
2.  Si Windows pregunta si se permiten cambios en el dispositivo, pulsar
    **Sí**.
3.  En la pantalla inicial del instalador, pulsar **Next**.

------------------------------------------------------------------------

## 6. Elegir los componentes

En **Choose Components**, dejar marcados:

-   [x] **Android Studio**
-   [x] **Android Virtual Device**

La segunda opción es necesaria para trabajar con emuladores.

Pulsar **Next**.

------------------------------------------------------------------------

## 7. Carpeta de instalación

Dejar la ruta propuesta por el instalador. Normalmente será similar a:

``` text
C:\Program Files\Android\Android Studio
```

Pulsar **Next**.

------------------------------------------------------------------------

## 8. Menú Inicio

Dejar como carpeta del menú Inicio:

``` text
Android Studio
```

Pulsar:

**Install**

Al terminar:

**Next → Finish**

Dejar marcada la opción para iniciar Android Studio.

------------------------------------------------------------------------

## 9. Primera ejecución

Si Android Studio pregunta si se desea importar una configuración
anterior, para una instalación nueva seleccionar:

**Do not import settings**

Pulsar **OK**.

------------------------------------------------------------------------

## 10. Estadísticas de uso

Puede aparecer una pantalla solicitando permiso para enviar estadísticas
de uso.

Para los equipos del aula se puede seleccionar:

**Don't send**

Esta decisión no afecta al funcionamiento de Android Studio.

------------------------------------------------------------------------

## 11. Android Studio Setup Wizard

En el asistente inicial:

1.  Pulsar **Next**.
2.  Si pregunta por el tipo de instalación, seleccionar:

**Standard**

Para las prácticas iniciales no es necesario utilizar **Custom**.

------------------------------------------------------------------------

## 12. Tema visual

Android Studio puede permitir elegir entre:

-   Light.
-   Dark.
-   System.

Esta elección no afecta al desarrollo.

Cada alumno puede escoger el tema que prefiera.

------------------------------------------------------------------------

## 13. Componentes del SDK

El asistente instalará componentes como:

-   Android SDK.
-   Android SDK Platform.
-   Android SDK Build-Tools.
-   Android Emulator.
-   Android SDK Platform-Tools.

Aceptar las licencias cuando se solicite y pulsar:

**Finish**

Esperar hasta que finalicen todas las descargas.

------------------------------------------------------------------------

# PARTE II. CONFIGURACIÓN DEL SDK

## 14. Abrir SDK Manager

En Android Studio ir a:

**Tools → SDK Manager**

------------------------------------------------------------------------

## 15. SDK Platforms

Abrir la pestaña:

**SDK Platforms**

Para las prácticas del módulo instalar:

-   [x] **Android 16 / API 36**

Pulsar **Apply** si es necesario descargarlo.

> **Nota:** no es necesario instalar muchas versiones de Android al
> comenzar el módulo.

------------------------------------------------------------------------

## 16. SDK Tools

Entrar en:

**SDK Tools**

Comprobar que están instalados:

-   [x] Android SDK Build-Tools
-   [x] Android SDK Command-line Tools
-   [x] Android Emulator
-   [x] Android SDK Platform-Tools

Inicialmente no es necesario instalar:

-   NDK.
-   CMake.

Pulsar:

**Apply → OK**

------------------------------------------------------------------------

## 17. Comprobar la ruta del SDK

En **SDK Manager** aparecerá **Android SDK Location**.

Normalmente será similar a:

``` text
C:\Users\alumno\AppData\Local\Android\Sdk
```

No es necesario modificarla.

------------------------------------------------------------------------

# PARTE III. EMULADOR ANDROID

## 18. Abrir Device Manager

Ir a:

**Tools → Device Manager**

Seleccionar:

**+ → Create Virtual Device**

o la opción equivalente para añadir un dispositivo virtual.

------------------------------------------------------------------------

## 19. Elegir el dispositivo

Seleccionar la categoría:

**Phone**

Para unificar las prácticas se recomienda:

**Pixel 8**

Pulsar **Next**.

------------------------------------------------------------------------

## 20. Elegir la imagen de Android

Seleccionar una imagen estable de:

**Android 16 / API 36**

Si todavía no está instalada, pulsar **Download**.

Aceptar la licencia y esperar a que termine la descarga.

Después seleccionar la imagen y pulsar **Next**.

------------------------------------------------------------------------

## 21. Configurar el AVD

Como nombre puede utilizarse:

``` text
Pixel_8_API_36
```

Dejar el resto de opciones por defecto.

Para gráficos:

``` text
Graphics: Automatic
```

Pulsar **Finish**.

------------------------------------------------------------------------

## 22. Probar el emulador

En **Device Manager**, localizar:

``` text
Pixel_8_API_36
```

Pulsar el botón ▶ para iniciarlo.

Debe aparecer un teléfono Android virtual.

La primera ejecución suele tardar más que las siguientes.

------------------------------------------------------------------------

# PARTE IV. INSTALACIÓN DE GIT

## 23. Descargar Git

Acceder a:

https://git-scm.com/download/win

Descargar:

**Git for Windows x64 Setup**

------------------------------------------------------------------------

## 24. Instalar Git

Ejecutar el instalador.

En **Select Components** pueden mantenerse las opciones predeterminadas.

Conviene mantener:

-   [x] Git Bash Here
-   [x] Git GUI Here

Git GUI no es imprescindible, pero puede dejarse instalado.

------------------------------------------------------------------------

## 25. Editor predeterminado de Git

El instalador puede preguntar por el editor predeterminado.

Si el alumno tiene Visual Studio Code instalado, puede elegirlo.

En cualquier caso, esta opción no es especialmente importante para las
prácticas, ya que los commits se realizarán principalmente desde Android
Studio.

------------------------------------------------------------------------

## 26. Rama inicial

Cuando aparezca la configuración del nombre de la rama inicial,
seleccionar:

**Override the default branch name for new repositories**

Escribir:

``` text
main
```

Así todos los alumnos utilizarán el mismo nombre de rama.

------------------------------------------------------------------------

## 27. Git en el PATH

Seleccionar:

**Git from the command line and also from 3rd-party software**

Esta opción permite utilizar Git desde:

-   MCD. 
-   PowerShell.
-   Git Bash.
-   Android Studio.
-   Otros programas.

------------------------------------------------------------------------

## 28. Resto de opciones de Git

Mantener las opciones predeterminadas para:

-   SSH.
-   HTTPS.
-   Finales de línea.
-   Terminal.
-   `git pull`.
-   Credential Manager.

Es recomendable mantener habilitado:

**Git Credential Manager**

Finalizar la instalación.

------------------------------------------------------------------------

## 29. Comprobar Git

Abrir CMD, PowerShell o Git Bash.

Ejecutar:

``` bash
git --version
```

Debe mostrarse la versión instalada.

------------------------------------------------------------------------

## 30. Configurar nombre y correo

Cada alumno debe configurar su identidad:

``` bash
git config --global user.name "Nombre Apellidos"
```

Después:

``` bash
git config --global user.email "correo@ejemplo.com"
```

Ejemplo:

``` bash
git config --global user.name "Ana García López"
git config --global user.email "ana@gmail.com"
```

Es recomendable utilizar el mismo correo asociado a GitHub.

Comprobar la configuración:

``` bash
git config --global --list
```

------------------------------------------------------------------------

# PARTE V. CONFIGURAR GIT EN ANDROID STUDIO

## 31. Comprobar el ejecutable de Git

En Android Studio:

**File → Settings → Version Control → Git**

En **Path to Git executable** debería aparecer automáticamente una ruta
similar a:

``` text
C:\Program Files\Git\bin\git.exe
```

Pulsar:

**Test**

Android Studio debe indicar que Git se ha ejecutado correctamente.

------------------------------------------------------------------------

# PARTE VI. CUENTA DE GITHUB

## 32. Crear una cuenta

Acceder a:

https://github.com

Pulsar:

**Sign up**

Completar el registro y verificar la cuenta.

Cada alumno debe utilizar su propia cuenta.

------------------------------------------------------------------------

## 33. Vincular GitHub con Android Studio

En Android Studio:

**File → Settings → Version Control → GitHub**

Pulsar:

**+**

Seleccionar:

**Log In via GitHub**

Se abrirá el navegador.

1.  Iniciar sesión en GitHub.
2.  Autorizar el acceso solicitado.
3.  Volver a Android Studio.

La cuenta debería aparecer configurada.

------------------------------------------------------------------------

# PARTE VII. CREAR EL REPOSITORIO PMUL

## 34. Crear PMUL en GitHub

En GitHub:

**+ → New repository**

En **Repository name** escribir exactamente:

``` text
PMUL
```

Como descripción se puede utilizar:

``` text
Programación Multimedia y Dispositivos Móviles - DAM
```

------------------------------------------------------------------------

## 35. Visibilidad

Para las prácticas evaluables se recomienda:

**Private**

De esta forma el código del alumno no estará disponible públicamente.

------------------------------------------------------------------------

## 36. Crear inicialmente un repositorio vacío

Al crear `PMUL`, no marcar:

-   [ ] Add a README file
-   [ ] Add .gitignore
-   [ ] Choose a license

Pulsar:

**Create repository**

------------------------------------------------------------------------

# PARTE VIII. ORGANIZACIÓN LOCAL DE PMUL

## 37. Crear la carpeta general

Crear en el ordenador:

``` text
C:\DAM\PMUL
```

Esta será la carpeta raíz para las prácticas del módulo.

------------------------------------------------------------------------

## 38. Estructura recomendada

Todos los proyectos se guardarán dentro de `PMUL`.

Por ejemplo:

``` text
PMUL/
│
├── HolaMundo/
├── ControlesBasicos/
├── Navegacion/
├── Multimedia/
├── Sensores/
└── ...
```

También se podrían organizar por unidades:

``` text
PMUL/
│
├── UD01/
├── UD02/
├── UD03/
├── UD04/
└── ...
```

> **Importante:** se recomienda utilizar **un único repositorio PMUL por
> alumno** y guardar dentro las diferentes prácticas.

------------------------------------------------------------------------

# PARTE IX. INICIALIZAR GIT EN PMUL

## 39. Abrir una terminal

Abrir PowerShell, CMD o Git Bash.

Situarse en:

``` bash
cd C:\DAM\PMUL
```

------------------------------------------------------------------------

## 40. Inicializar el repositorio

Ejecutar:

``` bash
git init
```

Establecer `main` como rama principal:

``` bash
git branch -M main
```

------------------------------------------------------------------------

## 41. Conectar con GitHub

Copiar la URL del repositorio `PMUL` del alumno.

Será similar a:

``` text
https://github.com/USUARIO/PMUL.git
```

Añadirlo como repositorio remoto:

``` bash
git remote add origin https://github.com/USUARIO/PMUL.git
```

Ejemplo:

``` bash
git remote add origin https://github.com/agarcia/PMUL.git
```

Comprobar:

``` bash
git remote -v
```

------------------------------------------------------------------------

# PARTE X. CREAR EL PRIMER PROYECTO ANDROID

## 42. Crear un proyecto

En Android Studio:

**File → New → New Project**

Elegir una plantilla sencilla compatible con:

**Jetpack Compose**

Por ejemplo:

**Empty Activity**

Pulsar **Next**.

------------------------------------------------------------------------

## 43. Datos del proyecto

Ejemplo:

**Name**

``` text
HolaMundo
```

**Package name**

``` text
com.nombrealumno.holamundo
```

**Save location**

``` text
C:\DAM\PMUL\HolaMundo
```

------------------------------------------------------------------------

## 44. Lenguaje

Seleccionar:

**Kotlin**

Para los nuevos proyectos del módulo utilizaremos Kotlin.

------------------------------------------------------------------------

## 45. Minimum SDK

Seleccionar:

**API 26: Android 8.0 (Oreo)**

Configuración de referencia:

``` text
Language: Kotlin
Minimum SDK: API 26
```

El proyecto utilizará como referencia:

``` text
compileSdk = 36
targetSdk = 36
```

> **Importante:** `minSdk`, `compileSdk` y `targetSdk` son conceptos
> diferentes.

------------------------------------------------------------------------

## 46. Crear el proyecto

Pulsar:

**Finish**

Esperar a que Android Studio termine la sincronización de Gradle y
descargue las dependencias necesarias.

------------------------------------------------------------------------

# PARTE XI. EJECUTAR LA PRIMERA APP

## 47. Seleccionar el emulador

En la barra superior de Android Studio seleccionar:

``` text
Pixel_8_API_36
```

------------------------------------------------------------------------

## 48. Ejecutar

Pulsar:

▶ **Run**

Android Studio:

1.  Compilará el proyecto.
2.  Iniciará el emulador si no está iniciado.
3.  Instalará la aplicación.
4.  Ejecutará la aplicación.

Si aparece la pantalla de la app, la configuración es correcta.

------------------------------------------------------------------------

# PARTE XII. `.gitignore`

## 49. Archivos que no deben subirse

Los proyectos Android contienen archivos generados o configuraciones
locales que no deben versionarse.

Debe existir un archivo:

``` text
.gitignore
```

Una configuración sencilla puede contener:

``` gitignore
*.iml
.gradle/
local.properties
.idea/
.DS_Store
build/
captures/
.externalNativeBuild/
.cxx/
```

> **MUY IMPORTANTE:** `local.properties` no debe subirse a GitHub porque
> contiene información específica del equipo, como la ruta local del
> SDK.

------------------------------------------------------------------------

# PARTE XIII. PRIMER COMMIT

## 50. Comprobar los cambios

Desde la raíz de `PMUL` se puede ejecutar:

``` bash
git status
```

Git mostrará los archivos nuevos.

------------------------------------------------------------------------

## 51. Añadir los archivos

Ejecutar:

``` bash
git add .
```

------------------------------------------------------------------------

## 52. Crear el primer commit

Ejecutar:

``` bash
git commit -m "Añadido proyecto HolaMundo"
```

Un **commit** guarda una versión de los cambios en el repositorio Git
local.

Todavía no significa que los archivos estén en GitHub.

------------------------------------------------------------------------

# PARTE XIV. SUBIR PMUL A GITHUB

## 53. Realizar el primer push

Ejecutar:

``` bash
git push -u origin main
```

GitHub puede solicitar autenticación.

Una vez realizada, los archivos se enviarán al repositorio.

------------------------------------------------------------------------

## 54. Comprobar GitHub

Abrir el repositorio:

``` text
https://github.com/USUARIO/PMUL
```

Debe aparecer el proyecto:

``` text
PMUL/
└── HolaMundo/
```

------------------------------------------------------------------------

# PARTE XV. TRABAJAR DESDE ANDROID STUDIO

## 55. Commit desde Android Studio

También se puede utilizar:

**Git → Commit**

Atajo habitual:

``` text
Ctrl + K
```

Seleccionar los archivos modificados.

Escribir un mensaje descriptivo.

Ejemplo:

``` text
Añadida pantalla principal
```

Pulsar:

**Commit**

------------------------------------------------------------------------

## 56. Push desde Android Studio

Después:

**Git → Push**

o utilizar el atajo correspondiente del IDE.

Comprobar que se envía:

``` text
main → origin/main
```

Pulsar:

**Push**

------------------------------------------------------------------------

## 57. Pull

Antes de comenzar a trabajar, especialmente si el repositorio se utiliza
desde varios ordenadores:

**Git → Pull**

También puede realizarse desde terminal:

``` bash
git pull
```

------------------------------------------------------------------------

# PARTE XVI. FLUJO DE TRABAJO DIARIO

## 58. Secuencia recomendada

Cada vez que se trabaje con una práctica:

``` text
PULL
  ↓
PROGRAMAR
  ↓
COMPROBAR / EJECUTAR
  ↓
COMMIT
  ↓
PUSH
```

### Desde terminal

``` bash
git pull
git status
git add .
git commit -m "Descripción del cambio"
git push
```

------------------------------------------------------------------------

# PARTE XVII. MENSAJES DE COMMIT

## 59. Evitar mensajes poco descriptivos

No utilizar:

``` text
cambios
```

``` text
cosas
```

``` text
prueba
```

``` text
asdf
```

------------------------------------------------------------------------

## 60. Utilizar mensajes descriptivos

Ejemplos:

``` text
Añadida pantalla de inicio
```

``` text
Implementada navegación entre pantallas
```

``` text
Corregido error en MainActivity
```

``` text
Añadido reproductor de audio
```

``` text
Implementado acceso a la cámara
```

------------------------------------------------------------------------

# PARTE XVIII. INFORMACIÓN QUE NO DEBE SUBIRSE A GITHUB

## 61. No versionar información sensible

No subir:

-   Contraseñas.
-   Tokens.
-   API keys privadas.
-   Credenciales.
-   `local.properties`.
-   Ficheros personales.
-   Builds generados.
-   APK innecesarios.
-   Datos privados de usuarios.

Nunca escribir una contraseña o token directamente en el código que se
vaya a subir al repositorio.

------------------------------------------------------------------------

# PARTE XIX. NUEVAS PRÁCTICAS

## 62. Crear otro proyecto

Para una nueva práctica:

**File → New → New Project**

Guardar, por ejemplo, en:

``` text
C:\DAM\PMUL\Multimedia
```

La estructura quedaría:

``` text
PMUL/
│
├── HolaMundo/
└── Multimedia/
```

------------------------------------------------------------------------

## 63. Guardar la nueva práctica en Git

Desde `C:\DAM\PMUL`:

``` bash
git status
git add .
git commit -m "Añadida práctica Multimedia"
git push
```

La nueva práctica aparecerá en el mismo repositorio GitHub.

------------------------------------------------------------------------

# PARTE XX. RESUMEN DE COMANDOS GIT

## 64. Comandos fundamentales

### Consultar versión

``` bash
git --version
```

### Inicializar repositorio

``` bash
git init
```

### Consultar estado

``` bash
git status
```

### Añadir cambios

``` bash
git add .
```

### Crear commit

``` bash
git commit -m "Mensaje"
```

### Añadir repositorio remoto

``` bash
git remote add origin https://github.com/USUARIO/PMUL.git
```

### Ver repositorios remotos

``` bash
git remote -v
```

### Establecer `main`

``` bash
git branch -M main
```

### Enviar cambios

``` bash
git push
```

### Primer envío

``` bash
git push -u origin main
```

### Descargar cambios

``` bash
git pull
```

------------------------------------------------------------------------

# PARTE XXI. CONFIGURACIÓN FINAL RECOMENDADA

Al finalizar la instalación, todos los alumnos deberían disponer de:

``` text
Android Studio: versión Stable
Lenguaje: Kotlin
UI: Jetpack Compose
Android SDK: API 36
Minimum SDK: API 26
Emulador: Pixel 8
Emulador Android: API 36
Git: instalado y configurado
Rama Git: main
GitHub: cuenta individual
Repositorio: PMUL
```

Y una estructura local similar a:

``` text
C:\DAM\
└── PMUL\
    ├── .git\
    ├── .gitignore
    ├── HolaMundo\
    ├── Practica02\
    ├── Multimedia\
    └── ...
```

------------------------------------------------------------------------

# Checklist final del alumno

Antes de comenzar las prácticas comprobar:

-   [ ] Android Studio arranca correctamente.
-   [ ] Android SDK API 36 está instalado.
-   [ ] El emulador `Pixel_8_API_36` funciona.
-   [ ] Se puede ejecutar una aplicación Kotlin + Jetpack Compose.
-   [ ] Git está instalado.
-   [ ] `git --version` funciona.
-   [ ] Nombre y correo de Git están configurados.
-   [ ] Existe una cuenta de GitHub.
-   [ ] Existe el repositorio privado `PMUL`.
-   [ ] La carpeta local es `C:\DAM\PMUL`.
-   [ ] El repositorio local utiliza la rama `main`.
-   [ ] `origin` apunta al repositorio `PMUL` del alumno.
-   [ ] `local.properties` no se sube al repositorio.
-   [ ] Se ha realizado al menos un `commit`.
-   [ ] Se ha realizado correctamente el primer `push`.
-   [ ] El proyecto aparece en GitHub.

------------------------------------------------------------------------

## Flujo que utilizaremos durante el curso

``` text
GitHub (PMUL)
      ↑
     PUSH
      ↑
   COMMIT
      ↑
 PROGRAMAR
      ↑
     PULL
      ↑
GitHub (PMUL)
```

**Regla de trabajo:** antes de empezar, `pull`; después de realizar
cambios coherentes, `commit`; al finalizar la sesión, `push`.


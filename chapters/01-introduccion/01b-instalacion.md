# 1.2 Instalación Ionic

Como en Ionic, las aplicaciones de Ionic 2 se pueden crear y testear rápidamente desde el de interfaz de lineas de comandos
 (CLI por sus siglas en inglés) o directamente en el navegador.
Para instalar el SDK y crear proyectos de Ionic 2, es necesario instalar la última versión beta:

``
$ npm install -g ionic@beta
``

No está familiarizado con NPM? Aprenda más sobre como utilizar el gestor de paquetes [aquí] (../ 07-resources / 07e-using-npm.md)
Preocupados por sus proyectos Ionic v1? ¡No se preocupe! La versión beta tiene toda la funcionalidad para trabajar con ambos
 proyectos proyectos v1 y v2.

Una vez hecho esto, cree su primera aplicación Ionic:

``
$ ionic start cutePuppyPics --v2
``

Para ejecutar la aplicación, entre en el directorio que se ha creado y ejecute el comando:

``
$ cd cutePuppyPics
$ ionic serve
``

Se puede jugar con ella directamente en su navegador!

Creando una aplicación movil
Una vez que haya instalado Ionic, puede crear su aplicación móvil. Si no tiene un dispositivo físico en la mano, 
todavía puede desarrollar con un emulador. Compruebe los documentos del simulador de iOS si estás en un Mac, o los documentos 
Genymotion si está buscando emular un dispositivo Android. También necesitará Cordova para ejecutar la aplicación en un dispositivo nativo. 
Para instalar Cordova, ejecute:

``
$ sudo npm install -g cordova
``

Una vez que haya instalado Córdoba y un dispositivo o emulador está listo para comenzar, puede seguir adelante y empezar a construir 
su aplicación!

## El desarrollo para iOS
Para desarrollar para iOS, tenemos que añadir el módulo de plataforma de IOS a Córdoba:

``
$ ionic platform add ios
``

Luego hay que instalar [Xcode] (../../ glossario.md). Xcode permite crear y construir un dispositivo de destino con iOS.
A partir de ahí, usted debe ser capaz de ejecutar el emulador de iOS usando el siguiente comando:

``
$ ionic emulate ios
``

## El desarrollo para Android
Para desarrollar para Android, tendrá que añadir el módulo de plataforma Android a Córdoba:

``
$ ionic platform add android
``

A continuación, tendrá que instalar [Android SDK] (../../ glossario.md). El SDK de Android le permite construir un dispositivo 
de destino con Android. Aunque el SDK Android viene con un emulador en sí, Genymotion es recomendable, ya que es mucho más rápido. 
Una vez instalado, inicie una imagen Android y ejecuta:

``
$ ionic run android
``


[Siguiente] (01c-tutorial.md)
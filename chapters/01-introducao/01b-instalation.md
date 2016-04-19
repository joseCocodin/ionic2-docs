# 1.2 Instalación Ionic
Como nadie iónico, iónico 2 aplicaciones se pueden crear rápidamente desde la CLI iónico o una herramienta de interfaz gráfica de usuario o construido y probado directamente en el navegador.
Para instalar el SDK y crear Ionic Ionic 2 proyectos, es necesario instalar la última versión beta:
`` `
$ npm install -g ionic@beta
`` `
Usted no está familiarizado con la NGP? Aprender más sobre él y lo utiliza paquetes [aquí] (../ 07-resources / 07e-using-npm.md)
Preocupados por sus proyectos iónico V1? ¡No se preocupe! La versión beta tiene toda la funcionalidad para trabajar con ambos proyectos proyectos V2 V1 y.
Una vez hecho esto, crear su primera aplicación Ionic:
`` `
$ ionic start cutePuppyPics --v2
`` `
Para ejecutar la aplicación, ** ** entra en el directorio que se ha creado y ejecute ** ** Ionic sirve comando:
`` `
$ cd cutePuppyPics
$ ionic serve
`` `
Se puede jugar con ella directamente en su navegador!
dispositivo ## para el desarrollo
Una vez que haya instalado Ionic, puede desarrollar su aplicación a un dispositivo físico. Si usted no tiene un dispositivo físico en la mano, todavía se puede desarrollar para un emulador de dispositivos. Compruebe el simulador de iOS docs si estás en un Mac, o documentos Genymotion si usted está buscando para emular un dispositivo Android. También necesitará Cordova para ejecutar la aplicación en un dispositivo nativo. Para instalar Cordova, ejecute:
`` `
$ sudo npm install -g cordova
`` `
Una vez que haya instalado Córdoba y un dispositivo o emulador listo para comenzar, puede seguir adelante y empezar a construir su aplicación!
## El desarrollo para iOS
Para desarrollar para iOS, tenemos que añadir el módulo de plataforma de IOS a Córdoba:
`` `
$ ionic platform add ios
`` `
Luego hay que instalar [Xcode] (../../ glossario.md). Xcode permite crear y construir un dispositivo de destino con iOS.
A partir de ahí, usted debe ser capaz de ejecutar iOS emulador usando el siguiente comando:
`` `
$ ionic emulate ios
`` `
## El desarrollo para Android
Para desarrollar para Android, tendrá que añadir el módulo de plataforma Android a Córdoba:
`` `
$ ionic platform add android
`` `
A continuación, tendrá que instalar [Android SDK] (../../ glossario.md). El SDK de Android le permite construir y construir un dispositivo de destino con Android. Aunque el SDK Android viene con un emulador en sí, Genymotion es recomendable, ya que es mucho más rápido. Una vez instalado, inicie una imagen Android y ejecuta:
`` `
$ ionic run android
```

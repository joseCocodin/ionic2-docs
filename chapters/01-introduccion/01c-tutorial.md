# 1.3 Ionic 2 Tutorial

Ahora que ha de [Ionic instalado junto con sus dependencias](01b-instalation.md),puede desarrollar su primera aplicación! Esta sección le guiará a través del proceso de iniciar una nueva aplicación mediante la adición de páginas, la navegación entre las páginas, y más. ¡Vamos a empezar!

## Inicio de una nueva aplicación Ionic 2

Vamos a desarrollar una aplicación! Utilice el comando **start** para inicializar una nueva aplicación Ionic. Especifica que desea que sea una aplicación Ionic 2 a través de la opción **--v2**. ambién se especifica que el modelo **tutorial** podería ser usado.
```
$ ionic start MyIonic2Project tutorial --v2
```

Esto va a descargar el Ionic 2, instale el [módulos npm](../../glossario.md) para la aplicación, y obtener [Cordova](../../glossario.md) configurado e listo para utilizar.

Desea utilizar TypeScript en su lugar? Pasar el indicador **--ts** y obtener un ajuste del proyecto de TypeScript en su lugar.
Usted puede haber notado que hemos pasado **tutorial** para el comando **ionic start**. Esto le dice al Ionic iniciar una aplicación utilizando el [modelo tutorial](https://github.com/driftyco/ionic2-starter-tutorial). Si no se especifica un modelo de funcionamiento **ionic start MyIonic2Project --v2**, o [tab starter](https://github.com/driftyco/ionic2-starter-tabs) será utilizado.

## Visualizando o aplicativo em um navegador

Ahora usted puede **cd** para entrar en la carpeta que creó. Para una visión rápida de su aplicación en el navegador, utilice el comando **serve**.
```
$ cd MyIonic2Project/
$ ionic serve
```

![tutorial-screen](tutorial-screen.png)

Debería ver el mensaje de bienvenida se muestra arriba si se ha instalado correctamente.
En la siguiente sección, vamos a hablar de la estructura del proyecto creado por el comando **ionic**.

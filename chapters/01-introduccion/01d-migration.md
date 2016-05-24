# 1.4 Conceitos de Migração

Ionic 2 se basa en Angular 2, que es una reescritura completa del framework original. Todas las partes do Angular que usted sabe que todavía están allí, pero hay nuevos cambios en la sintaxis y estructurales en las que los desarrolladores deben tener en cuenta. Para una visión general de los cambios en el Angular 2, echar un vistazo a [Aprenda Angular 2](http://learnangular2.com/).

En Ionic 2, deben sentirse muy familiarizados con las cosas. Todos los conceptos de Ionic V1 aun están en la V2, aunque pueden ser ligeramente diferentes. Vtodavía tiene vistas y controladores como lo hace en V1, mas em V2, que se fusionaron en una instancia.

Vea este exemplo V1.

V1

```ts
.config(function($stateProvider){
  $stateProvider
  .state('main', {
    url: '/',
    templateUrl: 'templates/main.html',
    controller: 'MainCtrl'
  })
})

.controller('MainCtrl', function(){

})
```

Puede escribirlo en V2 de esta manera:

```ts
@Page({
  templateUrl:'main/main.html'
})
export class MainCmp {
  constructor(){

  }
}
```

Otros cambios, como los cambios de navegación son muy diferentes, pero por una buena razón, como nos prometieron. Ahora se puede tratar como componentes vistas arbitrarias y navegar por ellas de la manera deseada. Esto hace que la navegación mucho más flexible y permite estilo baterías de navegación más nativo.

# Migrando de Angular 1

Enquanto Angular 2 requer aplicativos para ser atualizado para a mudança de sintaxe, os desenvolvedores podem ser pró-ativos e certificar se o seu aplicativo é atualizável, seguindo as melhores práticas e trabalhar com o guia Angular Style de John Papa ou o guia Angular Style de Todd Motto. Ambos irão fornecer-lhe os passos necessários para preparar seu código para a migração.
Mientras Angular 2 dispone que las solicitudes para ser ascendidos a la variación de la sintaxis, los desarrolladores pueden ser proactivos y asegurarse de que su aplicación es actualizable, siguiendo las mejores prácticas y el trabajo con la guía de estilos de Angular de John Papa o la guía de estilos de Angular Todd Motto. Ambos le proporcionará los pasos necesarios para preparar su código para la migración.

## ControllerAs Syntax

ControllerAs sintaxis es una característica de Angular 1.x donde en lugar de enlazar los datos de **$scope**, puede llamar a la instancia directa del responsable del controlador, como alternativa. Esto hace que la migración de un controlador de  Angular 1.x para una clase Angular 2 sea mucho mas fácil. É bastante fácil migrar para controllerAs de un controlador tradicional:

_index.html_

```ts
<ion-content ng-controller="MainCtrl">
  <ion-item>
    {{data.text}}
  </ion-item>
</ion-content>
```

_app.js_

```ts
.controller('MainCtrl', function($scope){
  $scope.data ={
    text: 'Hello World'
  }
})
```

Para convertir eso em sintasis **controllerAs** sólo hay que cambiar algunas cosas.

_index.html_

```ts
<ion-content ng-controller="MainCtrl as main">
  <ion-item>
    {{data.text}}
  </ion-item>
</ion-content>
```

_app.js_

```ts
.controller('MainCtrl', function(){
  this.data ={
    text: 'Hello World'
  }
})
```

## TypeScript

TypeScript es un superconjunto dee JavaScript que proporciona Classes ES6 y escribir anotaciones en su código. Ahora, con la adopción de TypeScript se puede escribir el código como Classes ES6 que serán fáciles de emigrar a Ionic 2.La mejor parte es que cualquier JavaScript válido también es TypeScript válido, por lo que puede convertir su código por partes. Si a aprovechar su controlador anterior, se puede convertir fácilmente en una classe TypeScript como esta:

_app.js_

```ts
.controller('MainCtrl', function(){
  this.data ={
    text: 'Hello World'
  }
})
```

_app.ts_

```ts
export class MainCtrl{
  constructor(){
    this.data ={
      text: 'Hello World'
    }
  }
}
```

## Estrutura do projeto

Con Angular 1 era una práctica para mantener toda sus JavaScript juntos y separados de sus modelos. Desde Ionic 2 y Angular 2 cambiará a una configuración basada en componentes, puede organizar su proyecto para ayudar a aplicar este concepto mental. Por lo tanto, un directorio de un proyecto con este aspecto...

```
|-www/
|
|--js/
|--|-app.js
|--|-HomeCtrl.js
|--|-DetailCtrl.js
|
|--templates/
|--|-Home.html
|--|-Detail.html
|
|-index.html
```

podría comenzar a reorganizarse para tener este aspecto::

```
|-www/
|
|--Home/
|--|-HomeCtrl.js
|--|-Home.html
|
|--Detail/
|--|-DetailCtrl.js
|--|-Detail.html
|
|-index.html
|-app.js
```

Organizar su proyecto de esta manera le puede ayudar a concienciarse de que cada vista / estados de aplicación son un componente con un modelo y un controlador.

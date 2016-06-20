# Alertas

Las alertas son una buena forma de ofrecer al usuario la habilidad de elegir una acción específica o una lista de acciones.
También pueden ofrecer al usuario información importante, o solicitarles tomar una decisión (o múltiples decisiones).

Desde una perspectiva de UI, puede pensar de las alertas como un tipo de ventana modal, que cubren solo una porción de la pantalla.
Esto significa que las alertas deberian solo ser usadas para acciones rápidas como verificación de contraseñas, pequeñas notificaciones 
de la applicación ó opciones rápidas. Profundizando, el control del usuario, debería estar reservado para modales con pantalla completa.

Las alertas son bastante flexibles, y pueden ser personalizadas fácilmente. Compruebe la documentación del API para más información.


* Contenido
* Uso básico
* Prompt Alerts
* Confirmation Alerts
* Radio Alerts
* Checkbox Alerts

## Uso básico:

Las alertas básicas son generalmente usadas para notificar al usuario sobre información nueva (un cambio en la app, una nueva característica), una situación de emergencia que necesita conocer, or como confirmación para el usuario que una acción tuvo éxito o no.

``` ts
doAlert() {
  let alert = Alert.create({
    title: 'New Friend!',
    subTitle: 'Your friend, Obi wan Kenobi, just accepted your friend request!',
    buttons: ['Ok']
  });
  this.nav.present(alert);
}
```

## Prompt Alerts

Las alerta prompt ofrecen al usuario una forma de introducir datos. Por ejemplo, a menudo las alertas prompt se usarán para preguntar al 
usuario que confirme la contraseña como medio de seguridad antes de avanzar en el flujo de la app.


``` ts
let prompt = Alert.create({
  title: 'Login',
  message: "Enter a name for this new album you're so keen on adding",
  inputs: [
    {
      name: 'title',
      placeholder: 'Title'
    },
  ],
  buttons: [
    {
      text: 'Cancel',
      handler: data => {
        console.log('Cancel clicked');
      }
    },
    {
      text: 'Save',
      handler: data => {
        console.log('Saved clicked');
      }
    }
  ]
});
```

## Confirmation Alerts

Las alertas de confirmación son usadas cuando es obligatorio que el usuario confirme explícitamente una elección en particular antes de continuar el proceso en la app. Un ejemplo común de la alerta de confirmación es asegurárse que el usuario quiere borrar un contacto de su lista de contactos.

``` ts
let confirm = Alert.create({
  title: 'Use this lightsaber?',
  message: 'Do you agree to use this lightsaber to do good across the intergalactic galaxy?',
  buttons: [
    {
      text: 'Disagree',
      handler: () => {
        console.log('Disagree clicked');
      }
    },
    {
      text: 'Agree',
      handler: () => {
        console.log('Agree clicked');
      }
    }
  ]
});
```

## Radio Alerts

Las alertas radio son otro tipo sencillo de alertas de confirmación, pero usan un componente de tipo radio para ofrecer varias opciones. Estas ofrecen al usuario un conjunto de opciones para elegir, pero solo se permite hacer una selección antes de continuar.

``` ts
doRadio() {
  let alert = Alert.create();
  alert.setTitle('Lightsaber color');

  alert.addInput({
    type: 'radio',
    label: 'Blue',
    value: 'blue',
    checked: true
  });

  alert.addButton('Cancel');
  alert.addButton({
    text: 'Ok',
    handler: data => {
      this.testRadioOpen = false;
      this.testRadioResult = data;
    }
  });
```

## Checkbox Alerts

Las alertas checkbox son otro tipo sencillo de alertas de confirmación, pero usan un componente checkbox para ofrecer varias opcines. Ofrecen al usuario un conjunto de opciones para elegir.


``` ts
doCheckbox() {
  let alert = Alert.create();
  alert.setTitle('Which planets have you visited?');

  alert.addInput({
    type: 'checkbox',
    label: 'Alderaan',
    value: 'value1',
    checked: true
  });

  alert.addInput({
    type: 'checkbox',
    label: 'Bespin',
    value: 'value2'
  });

  alert.addButton('Cancel');
  alert.addButton({
    text: 'Okay',
    handler: data => {
      console.log('Checkbox data:', data);
      this.testCheckboxOpen = false;
      this.testCheckboxResult = data;
    }
  });
}
```

# MVP Sendgrid

<p align="center">
  <img src="images/logo.png" width="150" length="200">
</p>


## Descripción

SendGrid, el servicio de entrega de correo electrónico de IBM Cloud, es un servicio de retransmisión de correo electrónico que le permite utiliza un smarthost para retransmitir sus servicios de correo saliente. Un smarthost retransmite tráfico de SMTP de un servidor SMTP, cliente de correo electrónico o cualquier otro servicio o lenguaje de programación capaz de gestionar SMTP. Este servicio también genera métricas, realiza el seguimiento de listas de correo electrónico, realiza el seguimiento de la actividad del correo electrónico, como por ejemplo, correos electrónicos rechazados, pulsados, descartados y abiertos.

## Crear proyecto

-Descargamos Node.js
-Comenzamos el proyecto en Node.js creando una carpeta nombrada 'Envio_mail' y corremos el comando ***npm init***.
-Agregamos en el archivo ***package.json*** en la seccion de ***scripts*** "start": "node sendgrid.js"
-Luego agregamos el archivo que se encuentra en este repositorio nombrado 'sendgrid.js' a la carpeta 
-Cuando hagamos cambios en el archivo debemos guardarlo y para probar corremos el comando ***npm start***


## Envio de Mail usando Sendgrid + Node.js


Debemos correr el comando en Node.js: ***npm install @sendgrid/mail*** 

El campo `to` puede contener una serie de destinatarios. Este mensaje

```js
const sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_API_KEY);
const msg = {
  to: ['recipient1@example.org', 'recipient2@example.org'],
  from: 'sender@example.org',
  subject: 'Hello world',
  text: 'Hello plain world!',
  html: '<p>Hello HTML world!</p>',
};
sgMail.send(msg);
```

If you want to send multiple _individual_ emails to multiple recipient where they don't see each other's email addresses, use `sendMultiple` instead:

```js
const sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_API_KEY);
const msg = {
  to: ['recipient1@example.org', 'recipient2@example.org'],
  from: 'sender@example.org',
  subject: 'Hello world',
  text: 'Hello plain world!',
  html: '<p>Hello HTML world!</p>',
};
sgMail.sendMultiple(msg);
```






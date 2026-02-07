Notas sobre la dosificadoras

Lo que viene en el correo



Se nos quedó pendiente comentaros que hemos aprovechado esta especificación para describir cómo funcionan las señales de las dosificadoras y los skids de dosificación que suministramos, aprovechando que lleva una dosificación de coagulante a la entrada del filtro.

La dosificadora, como equipo, lleva 4 señales, 2 DI, 1 DO y 1 AO:

-  "XSL" (DO), que activa/desactiva la señal de marcha. Es una señal mantenida.
-  "YA" (DI), que es el relé de fallo de la dosificadora.
-  "YL" (DI), que es una señal que se activa con cada pulso de la dosificadora; cuando la dosificadora esté en marcha esta señal debe estar parpadeando.
-  "SC" (AO), que es la referencia de velocidad de la dosificadora en 4-20 mA; 4 mA: 0%, 20 mA: 100%.

Depende de cómo se configure la electrónica de cada dosificadora, estas señales tendrán un comportamiento distinto.

- Normalmente, la "XSL" se usa como señal de "pausa", es decir, que un contacto cerrado va a parar la dosificadora y un contacto abierto va a permitir que funcione; al revés que los contactores de los motores. Esto se puede resolver invirtiendo la señal en el programa ("1" paro y "0" marcha) o si en el cuadro de marshalling hay relés de contactos conmutados, cogiendo el NC en vez del NO.
- La señal "YA" se utiliza como señal de alarma y nos dará un contacto cerrado si todo está OK ("1" OK, "0" alarma).
- La señal "YL" se puede usar como confirmación de marcha con un temporizador como se ha explicado en el documento, pero si "falla", es decir, si la señal no se recibe durante más tiempo no se lleva a fallo la dosificadora, aunque sí se da la alarma en el alarmero del SCADA. En el pasado hemos tenido alguna experiencia negativa con este tipo de sensor, por lo que si se pudiera meter en el faceplate del SCADA una opción para habilitar o no la monitorización de esta señal, mucho mejor.
- Si la señal "SC" baja a 4 mA en teoría se para la dosificadora, pero alguna vez hemos tenido instalaciones que, bien sea por el ruido electrónico, mala referencia a tierra, etc., daban pulsos esporádicamente aunque la referencia fuera 4 mA y por eso preferimos usar también la señal XSL.

En cuanto al skid, indicar simplemente que todas las válvulas de estos skid son motorizadas, con orden de abrir y cerrar, de modo que al recibir el final de carrera correspondiente (con un pequeño retraso entre 0.5 y 1.0 seg) debería dejar de dar la orden, aunque internamente el final de carrera corta la maniobra. Igualmente, si pasa un tiempo determinado con una orden de maniobra (abrir o cerrar) activada y la señal de final de carrera correspondiente no llega, se debe desactivar la orden de marcha para proteger el motor del actuador.

Si lo necesitáis, podemos incluir todo esto en la descripción de control.

Muchas gracias.
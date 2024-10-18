## Descripción 
Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos a la pagina web.
- Vamos a llenar el formulario que nos aparece al inicio, no importa lo que introduzcamos, solo hay que llenar los campos y dar click en el botón de `Register`.
- Aparecerá un nuevo formulario que nos pedirá una clave `OTP`
- Inspeccionarnos la pagina web y nos vamos al apartado de `Network` en ese momento ingresaremos cualquier cosa al apartado de `OTP`, nos aparecerá una petición con método `POST` lo seleccionamos y en el apartado de la derecha daremos al botón de `Reenviar`
- En el nuevo apartado que aparecerá, de las `Nuevas solicitudes`, bajaremos hasta el apartado de `Cuerpo` ahí nos aparecerá lo que introducimos en el formulario de `OTP`, borraremos el cuerpo y daremos click en `Enviar`.
- En el apartado de la derecha, iremos al aparato de `Respuesta` y encontraremos la bandera.
	- Flag:
```bash
Welcome, admin you sucessfully bypassed the OTP request. 
Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/419

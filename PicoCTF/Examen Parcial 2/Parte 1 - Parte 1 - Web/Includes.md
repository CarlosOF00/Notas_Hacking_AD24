## Descripción 
Can you get the flag?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos a la pagina web.
- Inspeccionamos en la pagina e ingresamos al apartado de `Sources` ahí podremos ver dos archivos.
	- `style.css` que en su contenido tiene un comentario: `/* picoCTF{1nclu51v17y_1of2_ */`
	- `script.js` que en su contenido tiene un comentario: `//  f7w_2of2_6edef411}
- Juntando ambos comentarios, obtenemos la bandera

```bash
picoCTF{1nclu51v17y_1of2_f7w_2of2_6edef411}
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/274
http://saturn.picoctf.net:62729

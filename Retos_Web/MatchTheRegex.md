## Descripción  
How about trying to match a regular expression

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali 
password:

## Solución
- Ingresamos la pagina e inspeccionamos el código fuente.
- Tras analizar la siguiente sección, nos podemos dar cuenta de lo siguiente: 
```bash
<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>
```
- El comentario del patrón de regex nos indica, que de primer carácter espera una p, seguido de 5 caracteres cualquiera, seguido de una F y finalmente !? indica que puede haber 0 o una exclamación después de la F.
- Podemos escribir picoCTF y nos manda una alerta.
- picoCTF{succ3ssfully_matchtheregex_08c310c6}

## Notas Adicionales
Las **regex** (expresiones regulares) son secuencias de caracteres que forman un patrón de búsqueda. Se utilizan para buscar, coincidir, manipular y analizar texto de manera flexible y potente. Aquí te explico algunos aspectos clave:

***Componentes Básicos
- **Literales**: Coinciden con caracteres exactos. Por ejemplo, `abc` coincide con "abc".
- **Metacaracteres**: Tienen significados especiales. Algunos ejemplos son:
    - `.`: Coincide con cualquier carácter.
    - `*`: Coincide con cero o más repeticiones del carácter anterior.
    - `+`: Coincide con una o más repeticiones del carácter anterior.
    - `?`: Coincide con cero o una repetición del carácter anterior.
    - `[]`: Define un conjunto de caracteres. Por ejemplo, `[a-z]` coincide con cualquier letra minúscula.
    - `^`: Coincide con el inicio de una línea.
    - `$`: Coincide con el final de una línea.
- **Grupos y Captura**: Los paréntesis `()` se utilizan para agrupar partes de la expresión y capturar el texto coincidente.

## Referencias 
https://play.picoctf.org/practice/challenge/356?page=1&search=match
http://saturn.picoctf.net:65001/
https://desarrollowp.com/blog/tutoriales/buscando-patron-con-expresiones-regulares/
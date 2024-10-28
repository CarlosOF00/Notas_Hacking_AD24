## Descripción 
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir vault-door-5
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd vault-door-5
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-5]
└─$ wget https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java
--2024-10-27 23:40:07--  https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1847 (1.8K) [application/octet-stream]
Saving to: ‘VaultDoor5.java’

VaultDoor5.java                           100%[=====================================================================================>]   1.80K  --.-KB/s    in 0s      

2024-10-27 23:40:08 (23.5 MB/s) - ‘VaultDoor5.java’ saved [1847/1847]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-5]
└─$ cat VaultDoor5.java 
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
        return base64Encoded.equals(expected);
    }
}
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-5]
└─$ 

```
- Copiamos el valor de la `String expected`, quitaremos las comillas dobles y los símbolos de igual e ingresamos a la pagina de `CyberChef` con los filtros de `Base64` y `URL Decode`,  [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm0KSlRZMkpUY3lKVE13SlRaa0pUVm1KVFl5SlRZeEpUTTFKVFkxSlRWbUpUTTIKSlRNMEpUVm1KVFkxSlRNekpUTXhKVE0xSlRNeUpUWXlKVFkySlRNMAo)obteniendo lo siguiente:
	- Antes:
		- JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm
		 JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2
		 JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0
	- Después:
		- c0nv3rt1ng_fr0m_ba5e_64_e3152bf4
- Ahora solo le damos formato a la bandera:
	- Flag: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/77
[CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm0KSlRZMkpUY3lKVE13SlRaa0pUVm1KVFl5SlRZeEpUTTFKVFkxSlRWbUpUTTIKSlRNMEpUVm1KVFkxSlRNekpUTXhKVE0xSlRNeUpUWXlKVFkySlRNMAo)

## Descripción 
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir timer 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd timer 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/timer]
└─$ wget https://artifacts.picoctf.net/c/449/timer.apk       
--2024-10-30 18:44:44--  https://artifacts.picoctf.net/c/449/timer.apk
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4678467 (4.5M) [application/octet-stream]
Saving to: ‘timer.apk’

timer.apk                                 100%[===================================================================================>]   4.46M  1.42MB/s    in 3.1s    

2024-10-30 18:44:48 (1.42 MB/s) - ‘timer.apk’ saved [4678467/4678467]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/timer]
└─$ ls
timer.apk
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/timer]
└─$ unzip timer.apk                                                                                                        
Archive:  timer.apk
 extracting: META-INF/androidx.fragment_fragment.version  
 extracting: META-INF/androidx.interpolator_interpolator.version  
 extracting: META-INF/androidx.legacy_legacy-support-core-utils.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-livedata-core.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-livedata.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-process.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-runtime.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-viewmodel-savedstate.version  
 extracting: META-INF/androidx.lifecycle_lifecycle-viewmodel.version  
 extracting: META-INF/androidx.loader_loader.version  
 extracting: META-INF/androidx.localbroadcastmanager_localbroadcastmanager.version  
 extracting: META-INF/androidx.print_print.version  
 extracting: META-INF/androidx.recyclerview_recyclerview.version  
 extracting: META-INF/androidx.savedstate_savedstate.version  
 extracting: META-INF/androidx.startup_startup-runtime.version  
 extracting: META-INF/androidx.tracing_tracing.version  
 extracting: META-INF/androidx.transition_transition.version  
 extracting: META-INF/androidx.vectordrawable_vectordrawable-animated.version  
 extracting: META-INF/androidx.vectordrawable_vectordrawable.version  
 extracting: META-INF/androidx.versionedparcelable_versionedparcelable.version  
 extracting: META-INF/androidx.viewpager2_viewpager2.version  
 extracting: META-INF/androidx.viewpager_viewpager.version  
 extracting: META-INF/com.google.android.material_material.version  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/timer]
└─$ ls
AndroidManifest.xml  META-INF  classes.dex  classes2.dex  classes3.dex  kotlin  res  resources.arsc  timer.apk
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/timer]
└─$ cd ..   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ grep -r "picoCTF" timer          

grep: timer/classes3.dex: binary file matches
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ strings timer/classes3.dex | grep "picoCTF"

*picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ 

```

- Bandera:
	- picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/381

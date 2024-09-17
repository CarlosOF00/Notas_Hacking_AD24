## Descripción 
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.iTN5lXw3Yk
carlosof-picoctf@webshell:~$ cd /tmp/tmp.iTN5lXw3Yk/
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
--2024-09-15 20:30:11--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                          100%[======================================================================================================>]   8.18K  --.-KB/s    in 0s      

2024-09-15 20:30:11 (221 MB/s) - 'static' saved [8376/8376]

carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
--2024-09-15 20:30:27--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                        100%[======================================================================================================>]     785  --.-KB/s    in 0s      

2024-09-15 20:30:27 (349 MB/s) - 'ltdis.sh' saved [785/785]

carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ ls
ltdis.sh  static
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ cat 
ltdis.sh  static    
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ cat 
ltdis.sh  static    
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ cat ltdis.sh 
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"


8#TT 1tt$DN
 @@ 0@)pp V``^okycarlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ ^C
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ grep -r "picoCTF"
grep: static: binary file matchesogram-file>"
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ grep -ar 'picoCTF' 
static:
 picoCTF{d15a5m_t34s3r_f5aeda17}GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.08Tt`
carlosof-picoctf@webshell:/tmp/tmp.iTN5lXw3Yk$ 
                                          = 
       H                                    Y h "libc.so.6puts__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_registerTMCloneTableui    1
 Ht5
 %
 @%
 h%
H=1I^HHPTLH
 DH=
 UH
 H9HtHZ
]f.]@f.H=
 H5
 UH)HHHH?HHtH!
 Ht
   ]f]@f.=I
 u/H=    UHt
H!          H=   
 ]fDUH]fUHH=]f.DAWAVIAUATL%F UH-F SAIL)HWHt 1LLDAHH9u[]A\A]A^A_Ðf.Oh hai! Wait what? A flag? Yes, it's around here somewhere!8
                                                                                                                              T<,zRx
                                                                                                                                   Rx
                                                                                                                                     FJ
R                                                                                                                                      ?;*3$"D\JAC
D|PeBBE B(H0H8M@r8A0A(B BBx0
o`

 picoCTF{d15a5m_t34s3r_f5aeda17}GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.08Tt`


   @ 
 $  k  1C@ Ji v `eH o0+@ :@     "
                                 crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.7698__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entrystatic.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5_edata__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTableflag__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.ABI-tag.note.gnu.build-id.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/163
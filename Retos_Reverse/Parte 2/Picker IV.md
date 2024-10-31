## Descripción 
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 62980`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash 
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ wget https://artifacts.picoctf.net/c/528/picker-IV.c
--2024-10-30 18:34:06--  https://artifacts.picoctf.net/c/528/picker-IV.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 839 [application/octet-stream]
Saving to: ‘picker-IV.c’

picker-IV.c                               100%[===================================================================================>]     839  --.-KB/s    in 0s      

2024-10-30 18:34:07 (19.0 MB/s) - ‘picker-IV.c’ saved [839/839]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ wget https://artifacts.picoctf.net/c/528/picker-IV  
--2024-10-30 18:34:16--  https://artifacts.picoctf.net/c/528/picker-IV
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17272 (17K) [application/octet-stream]
Saving to: ‘picker-IV’

picker-IV                                 100%[===================================================================================>]  16.87K  --.-KB/s    in 0s      

2024-10-30 18:34:17 (146 MB/s) - ‘picker-IV’ saved [17272/17272]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ ls
picker-IV  picker-IV.c
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ cat picker-IV.c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>


void print_segf_message(){
  printf("Segfault triggered! Exiting.\n");
  sleep(15);
  exit(SIGSEGV);
}

int win() {
  FILE *fptr;
  char c;

  printf("You won!\n");
  // Open file
  fptr = fopen("flag.txt", "r");
  if (fptr == NULL)
  {
      printf("Cannot open file.\n");
      exit(0);
  }

  // Read contents from file
  c = fgetc(fptr);
  while (c != EOF)
  {
      printf ("%c", c);
      c = fgetc(fptr);
  }

  printf("\n");
  fclose(fptr);
}

int main() {
  signal(SIGSEGV, print_segf_message);
  setvbuf(stdout, NULL, _IONBF, 0); // _IONBF = Unbuffered

  unsigned int val;
  printf("Enter the address in hex to jump to, excluding '0x': ");
  scanf("%x", &val);
  printf("You input 0x%x\n", val);

  void (*foo)(void) = (void (*)())val;
  foo();
}
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ cat picker-IV  
@@@@@@�▒▒@▒@@@hh@@UU  @ @00.>@>@p� . >@ >@�88@8@ XX@X@DDS�td88@8@ P�td� � @� @TTQ�tdR�td.>@>@��/lib64/ld-linux-x86-64.so.2GNU�GNU�<_��▒uQ��wC$�U��lGNU)�1,M9@b%� Z
                                                                                                                                                                  TF▒�tu▒ic.so~�?@�?�@@▒@@ @@(@@0@@8@@@@@H@@lpP@@putcharprintffgetcstdoutfclosesleepsetvbuf__libc_start_mainGLIBC_2.7GLIBC_2.2.5__gmon_start__ii
X@@
   `@@
��H�H��/H��t��H���5�/��%�/��h���������h���������h���������h���������h���������h���������h���������h��q��������a������h  ��Q������h
/D����%/D����%�.D����%�.D����%�.D����%�.D����%�.D��1�I��^H��H���PTI��@@H���@H��4@�2.�����f.����@@H=�@@t�H��t    ��@@��f��ff.�@��@@H���@@H��H��?H��H�H��t�H��t��@@���ff�f�������������z����+.]Ð�ff.�@������UH��H�=�
����������H�E�H���*����E��▒�E��������H�E�H�������E��}��u��
�����H�E�H������������UH��H��H�5/����
                                     �����H�(-���H�������H�=�
                                                             ������H�E�H��H�=�
                                                                              �������E���H�=�
                                                                                             ��b����E���H�E�H�E��и��f.�f���AWL�=3*AVI��AUI��ATA��UH�-$*SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��Segfault triggered! Exiting.You won!rflag.txtCannot open file.Enter the address in hex to jump to, excluding '0x': %xYou input 0x%x
P       �����D��������l$�����������������4���4����|zRx
                                                     ����/D0����$D�����F▒J
�                                                                         �?▒:*3$"l�����▒�����(E�C
����E�C
�������E�C
D�����eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B, ���p@@@
H@>▒▒>���o�@0@�@                              @
�
 ▒@`@▒H ▒���o�@���o���o�@ >@0@@@P@`@p@�@�@�@�@�@�@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒@8@X@|@�@�@0�@     �@
▒@
  `@
 @�@�@H@ @� @� @>@▒>@ >@�?@▒@@p@@▒�@@�
                                      �@@!@@7▒�@@F▒>@mp@y>@������,"@���▒>@� >@�>@�� @�▒@@@▒-▒�@� p@@Av@(Tf�@@mH@����p@@�� �x@@ @�@e#�@��▒�@@'�@��@/?▒�@@K4@�Pex���@@�
                                                                                                                                                                     @crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entrypicker-IV.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_finiputchar@@GLIBC_2.2.5stdout@@GLIBC_2.2.5print_segf_messageputs@@GLIBC_2.2.5_edatafclose@@GLIBC_2.2.5printf@@GLIBC_2.2.5fgetc@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_startsignal@@GLIBC_2.2.5__gmon_start____dso_handle_IO_stdin_used__libc_csu_initwin_dl_relocate_static_pie__bss_startmainsetvbuf@@GLIBC_2.2.5fopen@@GLIBC_2.2.5__isoc99_scanf@@GLIBC_2.7exit@@GLIBC_2.2.5__TMC_END__sleep@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.got.got.plt.data.bss.comment▒@▒#8@86X@X$I|@| W���o�@�a
                                                                                                                       �@�▒i0@0�q���o�@�~���o�@��▒@▒▒�B`@▒�@ @ ���@���� @ �� @� T�� @� ��▒>� >@ .��?@@@0p
                                 p@@�@@�0�0+�0 ▒        �7��:                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ objdump -D picker-IV | grep win 
000000000040129e <win>:
  4012d2:       75 16                   jne    4012ea <win+0x4c>
  4012f9:       eb 1a                   jmp    401315 <win+0x77>
  401319:       75 e0                   jne    4012fb <win+0x5d>
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ nc saturn.picoctf.net 55712
Enter the address in hex to jump to, excluding '0x': 40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/picker4]
└─$ 

```


## Notas Adicionales
- `objdump`: es una herramienta que forma parte del paquete binutils, utilizada para mostrar información sobre archivos binarios.
- `-D`: es una opción que indica que se debe desensamblar todo el contenido del archivo, mostrando todas las secciones de código en formato ensamblador.

## Referencias 
https://play.picoctf.org/practice/challenge/403

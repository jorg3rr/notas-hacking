#### Descripción

La recepción de Special ha sido genial, por decir lo menos. Es por eso que hicimos un versión exclusiva de Special, llamada Secure Comprehensive Interface para Afectando a Linux Empíricamente Rad, o simplemente 'Especial'. Con Specialer, realmente Trató de eliminar las distracciones del uso de un caparazón. Sí, nosotros sacamos el hechizo checker porque todo el mundo se queja. Pero creemos que estarás emocionado acerca de nuestro nuevo conjunto de funciones reducido para mantenerlo enfocado en lo que lo necesita más. Inicie una instancia para probar su propia copia de Specialer.ssh -p 62986 ctf-player@saturn.picoctf.net. La contraseña es 3f39b042

## Solución

Se trata de una continuación del [reto anterior](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Special.md).

### Conéctese al servidor
Comience conectándose al servidor con SSH

shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/picoCTF_2023/General_Skills/Specialer]
└─$ ssh -p 62169 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62169 ([13.59.203.175]:62169)' can't be established.
ED25519 key fingerprint is SHA256:lMXKIC17ONzyUJx7ZYBY5VSwoxCz20uq5/Nm+IhXKew.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62169' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Specialer$ 


### Obtener una lista de los comandos disponibles

[](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Specialer.md#get-a-list-of-available-commands)

Podemos usar [la finalización de la línea de comandos](https://en.wikipedia.org/wiki/Command-line_completion) para averiguar qué comandos están disponibles presionando dos veces`TAB`

shell
Specialer$ 
!          ]]         break      command    coproc     done       esac       false      function   if         local      pushd      return     source     times      ulimit     wait
./         alias      builtin    compgen    declare    echo       eval       fc         getopts    in         logout     pwd        select     suspend    trap       umask      while
:          bash       caller     complete   dirs       elif       exec       fg         hash       jobs       mapfile    read       set        test       true       unalias    {
[          bg         case       compopt    disown     else       exit       fi         help       kill       popd       readarray  shift      then       type       unset      }
[[         bind       cd         continue   do         enable     export     for        history    let        printf     readonly   shopt      time       typeset    until   


No, así que no podemos usar el truco que usamos en el [desafío anterior](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Special.md).  
Y no o . Pero hay .grepcatlsbash

### Intenta lanzar un shell real

[](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Specialer.md#try-to-launch-a-real-shell)

Vamos a intentar lanzar bash

shell
Specialer$ bash
Specialer$ 
!          ]]         break      command    coproc     done       esac       false      function   if         local      pushd      return     source     times      ulimit     wait
./         alias      builtin    compgen    declare    echo       eval       fc         getopts    in         logout     pwd        select     suspend    trap       umask      while
:          bash       caller     complete   dirs       elif       exec       fg         hash       jobs       mapfile    read       set        test       true       unalias    {
[          bg         case       compopt    disown     else       exit       fi         help       kill       popd       readarray  shift      then       type       unset      }
[[         bind       cd         continue   do         enable     export     for        history    let        printf     readonly   shopt      time       typeset    until      
Specialer$ exit
exit
Specialer$ 


Funcionó, pero también fue limitado, así que cerré la sesión de S.A.

### Mapear archivos y directorios

[](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Specialer.md#map-out-files-and-directories)

A continuación, mapeé archivos y directorios con cualquier comando (que se usa a continuación) presionando dos veces como antes`pushd`TAB

shell
Specialer$ pushd 
.bash_history  .hushlogin     .profile       abra/          ala/           sim/   
Specialer$ pushd abra/cada
cadabra.txt   cadaniel.txt  
Specialer$ pushd ala/
kazam.txt  mode.txt  
Specialer$ pushd sim/
city.txt     salabim.txt  


### Consigue la bandera

[](https://github.com/Cajac/picoCTF-Writeups/blob/main/picoCTF_2023/General_Skills/Specialer.md#get-the-flag)

Dado que está disponible para nosotros, podemos usar la [sustitución de comandos](https://www.gnu.org/software/bash/manual/html_node/Command-Substitution.html) y la [redirección de entrada](https://www.gnu.org/software/bash/manual/html_node/Redirections.html) para leer archivos`echo`

shell
Specialer$ echo $(<abra/cadabra.txt)
Nothing up my sleeve!
Specialer$ echo $(<abra/cadaniel.txt)
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ echo $(<ala/kazam.txt)
return 0 picoCTF{<REDACTED>}


Y ahí tenemos la bandera.

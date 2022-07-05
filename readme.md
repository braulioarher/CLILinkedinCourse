# Linux

Linux is just the name of the kernel wich allows sofware to communicate with the computer's harware.

All linux systems run a version of linux

## CLI comand line interface

    -Allows us to interact with programs using text commands
    -Command-line programas can red text inputs and output text to screen
    -Command-line programs can rea and write from files and network

Bash is the most used CLI in linux is widly available on linux.

Diferences between CLI and shell: CLI is a place where we can enter text commands and sheel is a piece of software that interprets typed commands and runs them

## How command are structured

command    +     options    +     arguments

        -Options tell the command how to operate se puede agragar las opciones que queramos ejemplo:
                -ls -a -h -l
                -ls -ahl
        -arguments tell the command what to operate on

## Copy move and delete

        cp              -Copia
        mv              -Mueve tambien renombra el nombre de un documeto
        rm              -Elimina

## Wildcards

        mv *.txt deparments/marketing           -Mueve todos los documentos que terminen en .txt
        mv deparparments/marketing/* .          -Regresa todos los archivos a su ruta original
        rm poems?.txt                           -Elimina archivos que contengan algun caracter donde "?"

        -r                      recursion aplica el comandoa todos lo elementos en una carpeta

## Comando Find

        find . -name "poe*"     -Dentro de carpeta actual busca los elementos que contenga poe en inicio
        find . -name "*d*"      -Contiene "d" antes o despues

## Roles de usuario

        rwx-rwx-rwx
        user
        group
        others

        chmod           -Cambia los permisos en modo de string

        cat test.ch     -Output the content of a file
        sudo chown root test.sh         -Cambia quien posee al archivo

## Links

Links are files that reference other files

        ln -s poems.txt writing.txt             -Hace un symlink link entre poems and writing
        ln -s

## Correct answers

        cd ~            Comando para ir a home
        ls ~            Comando correcto para listar home
        mv ~/log.tar.gz ~
        chmod u+x ~/log.tar.gz

## Uso de pipes

        Para unir la salida de un comando con otro se usa el operador "|"
        comando "cat" se usa para concatenar y tambien se usa para ver el contenido de un archivo
        head -n5 poems.txt   -Vizualiza las primeras lineas del contenido de un archivo
        tail -n3 poems.txt   -Vizualiza las ultimas linea del contenido de un archivo
        less poems.txt       -Vizualiza en pantalla completa el contenido del archivo

## Grep se usa para buscar texto dentro de archivos

        grep "the" poems.txt
        grep -in "The" poems.txt    -Retorna todas la lineas que contenga the sin importar las mayusculas
        grep -vi "the" poems.txt    -Retorna las lineas que no usan "the"
        grep -E "[hijk]" poems.txt  -Retorna las lineas que usan las letras [hijk]
        grep -E "\w{6,}" poems.txt  -Retorna las lineas que tenga 6 caracteres o mas

## Manipular text con awk, sed and sort

### awk

        awk '{print $2}' poems.txt  -Muestra la segunda columna de la tabla o la segunda palabra
        awk '{print $2 "\t" $1}' simple_data.txt | sort -n
        imprime y ordena de forma ascendente la tabla con el id y el nombre

### sed

        sed s/Orange/Red simple_data.txt        -Remplaza la palabra Orange por Red en el archivo

### sort

        sort simple_data.txt            -Ordena la primer columna de forma ascendente
        sort -k2 -n simple_data.txt        -Ordena la segunda columna de froma ascendente

## Editar texto con vim

Usar vim sirve para editar texto dentor de la consola

        -Para editar texto se debe de usar "i" que inserta texto
        :w new.txt      -Crea y guarda la informacion en un nuevo documento

## Editar texto con nano

Nano es otro editor de texto disponible y este es mas sencillo de utilizar

## Usar tar y zip

        tar -cvf myfiles.tar Exercise\ Files/   -Crea un archivo tar con el contenido de Exercise Files
        tar -caf myfiles.tar.gz Exercise\ Files/
        tar -caf myfiles.tar.gz.bz2 Exercise\ Files/

### Descomprimir

        tar -xf myfiles.tar.bx2                 -Extrae los archivos
        tar -xf myfiles.tar.bx2 -C direc        -Extrae los archivos en una carpeta en especifico

### Usar zip

        zip -r exfile.zip Execersice\ files     -Comprime directorio en formato zip
        unzip exfile.zip                        -Descomprime archvo .zip
        unzip unpack3/ecfiles.zip -d unpack4    -Descomprime archivo en el directorio indicado

## Output redirenction

        0       Standard input
        1       Standard output
        2       Standard error

        ls 1> filelist.txt              -escribe el estandar output a un documento txt
        ls notreal 2> filelist3.txt     -escribe el standar error en un documento txt
        >> filelist3.txt                -Agrega del standar output al dicumento sin sobre escribir

## Variables de entorno y PATH

## Informacion a cerca de la distribucion linux

        ls -l /etc/*release     -Busca las referencia que contenga la palabra releace

        uname -a encuaentra de distribucion de linux se usa

## Informacion a cerca del harware y disco

        free -h                 -revisa la memoria RAM disponible en la compurtadora
        cat /proc/cpuinfo       -revisa informacion a cerca del cpu
        df -h                   -revisa el espacio disponible en el equipo
        sudo lshw | less        -Muestra que piezas estan conectadas al sistema
        ip a                    -Muestra el ip adress

## Manejar software

        apt search tree         -Busca los paquetes que contienen tree
        apt show tree           -Da informacion a cerca de tree
        apt install tree        -Instala el paquete tree
        sudo apt update         -Busca por actualizaciones
        sudo apt upgrade        -Actualiza

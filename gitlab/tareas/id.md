Tarea: git-id
=============

En cualquier sistema no anónimo se necesita un sistema de identificación. En
Git, por su uso histórico para el desarrollo del kernel de Linux a través de
una lista de correo, la identificación que se usa es el nombre, más la
dirección de correo electrónico. (En Github, por el contrario, se da mayor
visibilidad al nombre de la cuenta.)

Si no se configura correctamente, Git usará una dirección de correo basada en
el nombre (arbitrario) de nuestra máquina, por ejemplo:

    Author: dato <dato@geertz.local>

cuando en realidad querríamos una identidad del tipo:

    Author: Adeodato Simó <dato@fi.uba.ar>

Esto se puede configurar con la herramienta `git-config`, o editando
directamente el archivo `~/.gitconfig`.

La herramienta `git-config`, por omisión, altera solamente el repositorio
actual; para que la configuración tenga efecto sobre todo nuestros repositorios
se debe invocar con la opción `--global`, así:

    $ git config --global user.name "Adeodato Simó"
    $ git config --global user.email dato@fi.uba.ar

Tras hacer esto, se puede verificar el resultado visitando el archivo
`~/.gitconfig`.


Configuración avanzada (y opcional)
-----------------------------------

A veces es útil tener distintas identidades (principalmente direcciones de
correo) para distintos _grupos_ de repositorios, por ejemplo: trabajo,
facultad, y repositorios personales.

El archivo de configuración global es insuficiente para esto, pero a la vez
sería tedioso modificar a mano la configuración de cada uno de estos
repositorios.

Para esto, es útil reagrupar los repositorios en distintos “directorios top
level” (por ejempo `~/work`, `~/uni`  y `~/proyectos`) y utilizar la
funcionalidad [includeIf] de Git:

    $ cat ~/.gitconfig
    [user]
        name = Dato Simó
        email = dato@net.com.org.es
    [includeIf "gitdir:~/uni/"]
        path = ~/.gitconfig.uba
    $ cat ~/.gitconfig.uba
    [user]
        name = Adeodato Simó
        email = dato@fi.uba.ar

[includeIf]: https://git-scm.com/docs/git-config#_includes

Repositorio de código para Organización del Computador
------------------------------------------------------

Este es tu repositorio personal para la materia; a través de él se
realizan las entregas de los trabajos prácticos.

Para poder trabajar en un repositorio, se lo debe descargar vía Git a
una computadora. Git funciona en todos los sistemas operativos, pero
para esta materia se necesita una computadora (o máquina virtual) que
corra Linux.

En Git, el nombre técnico para la descarga es "clonar", y se realiza
mediante la orden "git clone", pasando como argumento la dirección web
del repositorio. Por ejemplo:

    git clone https://github.com/fiubatps/orga_2019_moreno

Durante la cursada se proporcionará para cada lab o TP algunos archivos
de código base, o "esqueleto". Estos esqueletos irán apareciendo en el
repositorio público de la cátedra, https://github.com/fisop/orga_2019,
en un subdirectorio único a cada entrega. Por ejemplo, ya existe allí un
pseudo-lab inicial llamado "gitlab" con el que practicar el proceso.

Para acceder a los esqueletos se deberá configurar por una única y
primera vez la dirección del repositorio de la cátedra, así:

    git remote add --fetch catedra https://github.com/fisop/orga_2019

Una vez realizado este paso, la descarga del último lab disponible se
realiza con la orden:

    git pull --no-edit catedra master

De realizar estos dos pasos ahora, se descargaría el esqueleto de ese
primer pseudo-lab en un subdirectorio llamado "gitlab".

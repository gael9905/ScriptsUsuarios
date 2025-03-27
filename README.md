# Scripts en bash para crear usuarios de forma interactiva
En este repositorio encontraras 3 versiones de programas que permiten crear usuarios en sistemas
Linux. A continuación se describe las características de cada versión.
## Versión 0
Es la más básica, con ella podrás crear un usuario, indicando su login, el grupo al que pertencerá,
un comentario para describir al usuario, el nombre de su directorio home, el shell que usará, y 
su contraseña, para la cual hay una función de validación en la que solo podrás avanzar si usas
una contraaseña fuerte (8 caracteres, al menos una mayuscula, un caracter espcial y un número).
Cabe mencionar que el grupo al que pertenecerá el usuario ya debe existir, por lo que se agrega
la opción de crear un grupo.
## Versión 1
Nota: para esta versión la partición de home debe tener habilitadas las cuotas. 
Además de la versión 0, una vez creado el usuario se pregunta si desea agregar quotas al usuario,
para que tenga un límite de espacio a ocupar en el directorio home.
Entonces, si decides poner quotas, se activarán las quotas en la partición por si no están activas,
y se pedirá una cantidad en megabytes para el límite suave y el límite duro. 
Por último, mediante el comando setquota se impone la cuota.
## Versión 2
Además de las características anteriores, se preguntará si desea que el usuario puede ejecutar comandos
con sudo. Si quiere hacerlo, preguntará si quiere que ejecute todo como sudo o solo ciertos comandos.
Si eliges la primera opción, mediante el comando usermod se agrega el usuario al grupo sudo.
Si eliges la segunda opción, deberás poner la ruta completa de los comandos que quieres que ejecute.
Por ejemplo: /usr/bin/passwd
Nota: puedes ejecutar el comando whereis nombre_comando para saber la ruta absoluta de los comandos. 


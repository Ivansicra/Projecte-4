Per fer aquesta guia i com a prova de concepte, usaràs una màquina virtual amb un Ubuntu Server instal·lat i li afegiràs un segon disc de 10 GB que simularà una unitat auxiliar.

1.       Inicialitza i formata en format xfs. Com simula una unitat externa, es muntarà manualment a /media/backup (primer cal crear la carpeta).
   
3.       Instal·la duplicity.
   
4.       Crea un parell d’usuaris més al sistema de manera que tinguin carpeta personal. Crea 4 arxius de 10 MB a la carpeta home del teu usuari.
   
5.       Fes un còpia de seguretat de la carpeta /home.
   
6.       Esborra els arxius i fes un restore per comprovar com es recuperen els arxius.
   
7.       Afegeix un nou arxiu de 4 MB i fes una nova còpia. Observa com ara ha fet una còpia  incremental.
   
Desmunta la unitat de backup.

Ara passaràs a automatitzar el procés de les còpies utilitzant uns scripts bàsics i el programador de tasques (cron). Un aspecte molt important a nivell de seguretat, és que la unitat de backup ha d’estar per defecte, desmuntada. De manera que el primer pas sempre serà muntar la unitat i el darrer desmuntar-la, un cop s’ha fet la còpia.

7.       Crea un script anomenat fullbackup.sh que realitzi la còpia completa de la carpeta /home i l’emmagatzemi al volum muntat. Usa la variable d’entorn PASSPHRASE (per donar valor a una variable d’entorn cal afegir a 
l’script una línia amb export PASSPHRASE=contrasenya) per no haver d’escriure la passphrase en el moment de l’execució. Recorda de donar permisos d’execució a l’script.

8.       Programa al cron com a root  l’execució de l’script els diumenges a les 23:00.

9.       Crea un segon script anomenat incrementalbackup.sh que realitzi còpies incrementals de la mateixa carpeta que abans. Heu de fixar el valor de la variable PASSPHRASE igual que al punt 5 i donar permisos d’execució 
a l’script.

10.   Programa al cron l’execució d’aquest script com a root de dilluns a dissabte a les 23:00.

Materials i links de suport

●        Duplicati: https://duplicati.com/

●        WayToIT. Creando archivos con fsutil [blog]. Març 2015. Disponible a:

 https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/
 
●        WayToIT. Creando archivos de prueba en Linux [blog]. Març 2015. Disponible a:

 https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/
 
●        Duplicity man page:

  http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html
  
Programant tasques amb cron:

                      https://geekytheory.com/programar-tareas-en-linux-usando-crontab


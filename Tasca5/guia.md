#### 1. Configuro l’arxiu netplan amb la comanda sudo nano, per a que la xarxa funcioni correctament.

![Captura 12](img/1.png)

#### 2. Instalo el servei ssh amb la comanda apt install.

![Captura 12](img/2.png)

#### 3. Comprovo la ip que m’ha assignat automaticament amb la comanda ip addr show.

![Captura 12](img/3.png)

#### 4. Comprovo la connexió mitjançant la comanda ssh usuari@ i escric la meva ip a continuació.

![Captura 12](img/4.png)

#### 5. Verifico que treballo exactament igual com si ho fes desde la maquina Zorin.

![Captura 12](img/5.png)

#### 6. Habilito l’usuari root i agregant-li una contrasenya

![Captura 12](img/6.png)

#### 7. Afegeixo la última linea del codi, en la que autoritzo l’usuari “usuari”

![Captura 12](img/7.png)

#### 8. Iniciare sessió de manera local amb l’usuari root.

![Captura 12](img/8.png)

#### 9. Obro configuració i vaig a caracteristiques:

![Captura 12](img/30.png)
![Captura 12](img/31.png)

#### 10. En caracteristiques disponibles afegeixo SSH buscant-lo en el buscador.

![Captura 12](img/32.png)

#### 11. Seguidament, realitzo el mateix procés pero a través de la consola de comandes.

![Captura 12](img/33.png)
![Captura 12](img/34.png)
![Captura 12](img/35.png)
![Captura 12](img/36.png)

#### 12. A continuació comfiguro un tunel SSH: Afegeixo una interficie NAT als dos equips.

![Captura 12](img/37.png)

#### 13. Comprovo quina IP s'ha asignat:

![Captura 12](img/38.png)

#### 14. Configuro la màquina client per a que es redirigeixi el trafic de la xarxa: Obro propietats del internet i seguidament accedeixo a la configuració de la LAN:

![Captura 12](img/39.png)

#### 15. Faig clic a opcions avanzades:

![Captura 12](img/40.png)

#### 16. Afegeixo port al túnel:

![Captura 12](img/41.png)

#### 17. Comprovo el tràfic amb Wireshark: Sense túnel:

![Captura 12](img/42.png)

#### 18. Comprovo el tràfic amb Wireshark: Amb túnel:

![Captura 12](img/44.png)

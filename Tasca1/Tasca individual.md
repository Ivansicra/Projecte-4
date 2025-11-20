# 1. Què copiar?:
El més important a copiar sempre són les dades del servidor; com els documents, carpetes compartides i projectes, la base de dades (ERP, CRM o el que faci servir l’empresa), Ll configuració del servidor: usuaris, permisos, Active Directoris. Perquè si peta, reinstal·lar-ho tot seria un drama i per últim aplicacions importants i, si es pot, una imatge del sistema per recuperar el servidor ràpid.
Les aplicacions i el sofware de la màquina es pot tornar a instal·lar novament des del web oficial en cas de que es perdí.



### Cal fer còpia dels 10 equips clients?
Normalment no cal fer còpia completa dels ordinadors dels usuaris. Perquè la idea és que les coses importants estiguin al servidor, no als ordinadors. Si un treballador perd l'informació del seu ordinador, es reinstal·la el sistema i el programari un altre cop sense cap probelma.




# 2. Periodicitat i Tipus de Còpia:
La idea és fer un pla setmanal fàcil que funcioni correctament:
Durant la setmana, de dilluns a dijous, faria còpies incrementals. Aquest tipus només guarda els fitxers que han canviat des de l’última còpia, així és ràpid i ocupa poc espai.
Els divendres faria una còpia diferencial, que guarda tot el que ha canviat des de l’última còpia completa. D’aquesta manera tens un “punt fort” cada final de setmana.
Un cop al mes, el primer dia, faria una còpia completa de tot. Aquesta és la còpia grossa i més important.




# 3. Mitjans que utilitzaria:
NAS → per tenir les còpies automàtiques dins de l’empresa.

Cloud → perquè si hi ha un incendi, robatori o ransomware, tens tota la info fora.

Discs durs externs (xifrats) → per tenir una còpia offline, desconnectada, que és la més segura contra virus i atacs.



### Organització de les còpies:
Còpia de seguretat principal → NAS a l’empresa.

Còpia de seguretat externa → al Cloud.

Còpia de sguretat offline → disc dur extern guardat en un lloc diferent (i desconnectat sempre).



## Fase 2: Esquema 3-2-1 de Còpies

| **Element**                | **Proposta de la Parella**                                                                 | **Justificació**                                                                 |
|---------------------------|-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Dades Crítiques**       | - Base de dades Comptabilitat/Clients (20 GB)<br>- Documents de Projectes (300 GB)<br>- Carpetes Personals (100 GB) | La base de dades és la més crítica (ús diari i RTO/RPO estrictes). Documents i carpetes són importants però poden tenir RPO 24 h. |
| **Periodicitat (BD)**     | Cada 4 hores                                                                             | Complim RPO de 4 h per BD crítica.                                             |
| **Tipus de Còpia (BD)**   | Incremental + còpia completa diària                                                      | Incremental per reduir temps i espai; completa per seguretat.                  |
| **Mitjà 1 (Local)**       | NAS o disc extern al servidor                                                            | Recuperació ràpida en cas d’avaria local.                                      |
| **Mitjà 2 (Extern)**      | Núvol (AWS, Azure, Backblaze)                                                            | Protecció davant desastres físics (incendi, robatori).                         |

---

### Esquema 3-2-1
- **3 còpies**: Original + còpia local + còpia al núvol.
- **2 mitjans**: Disc local (NAS) + Cloud.
- **1 fora de lloc**: Núvol.

---

### Flux de Còpies
- **Servidor Ubuntu** → **NAS Local** (diària + BD cada 4 h)
- **Servidor Ubuntu** → **Cloud** (setmanal completa + incrementals diàries)

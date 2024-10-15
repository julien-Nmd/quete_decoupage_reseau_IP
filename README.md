# Quete_decoupage_reseau_IP  

  Une société fictive a 4 pôles informatiques. Le réseau est en 172.16.1.0/24.
Découper ce réseau de 2 manières, symétrique et asymétrique, pour que chaque pôle ci-dessous puissent avoir assez d'adresse pour chaque équipement.

Le Pôle informatique (6 bureaux, environ 50 équipements au total)
Le Pôle développement (6 bureaux, environ 12 équipements au total)
Le Pôle Administratif (4 bureaux, environ 20 équipements au total)
Le Pôle Technicien (4 bureaux, environ 15 équipements au total)

  Effectuer le découpage réseau pour une entreprise en donnant la formule utilisée pour chaque réseau découpé ainsi que le CIDR qui lui correspond pour permettre d'adresser ses équipements.
  Calculer pour chaque réseau, l'adresse réseau et l'adresse de diffusion (Broadcast)
  Présenter ce découpage dans un fichier texte en markdown, à la suite, ou sous forme de tableau, et poster le dans la solution, par exemple en le publiant dans un gist.


### Réseau 172.16.1.0/24 
#### Découpage assymétrique :  

On cherche en premier le nombre d'hôte pour chaque département de la liste ci-dessus :  

    Pole info. => 50 équipements => 2⁶ - 2 = 64-2 = 62 équipements possibles   
    Pole dév.  => 12 équipements => 2⁴ - 2 = 16-2 = 14 équipements possibles  
    Pole Admin.=> 20 équipements => 2⁵ - 2 = 32-2 = 30 équipements possibles  
    Pole Tech. => 15 équipements => 2⁵ - 2 = 32-2 = 30 équipements possibles  

Les sous-réseaux seront dans cette ordre :

    1- Pôle Info. (62 hôtes)
    2- Pôle Admin. (30 hôtes)
    3- Pôle Tech. (30 hôtes)
    4- Pôle Dév. (14 hôtes)  
    
Pour le réseau 172.16.1.0/24, on a donc les 4 sous-réseaux suivants :
  
Sous-réseau 1 : Pôle Info  
Adresse de réseau : 172.16.1.0/58  
Début de plage IP disponible : 172.16.1.1  
Fin de plage IP disponible : 172.16.1.62  
Adresse de broadcast : 172.16.1.63    
  
Sous-réseau 2 : Pôle Admin.  
Adresse de réseau : 172.16.1.64/27  
Début de plage IP disponible : 172.16.1.65  
Fin de plage IP disponible : 172.16.1.94  
Adresse de broadcast : 172.16.1.95  
  
Sous-réseau 3 : Pôle Tech.  
Adresse de réseau : 172.16.1.96/27  
Début de plage IP disponible : 172.16.1.97  
Fin de plage IP disponible : 172.16.1.126  
Adresse de broadcast : 172.16.1.127  
  
Sous-réseau 4 : Pôle Dév.  
Adresse de réseau : 172.16.1.128/12  
Début de plage IP disponible : 172.16.1.129  
Fin de plage IP disponible : 172.16.1.142  
Adresse de broadcast : 172.16.1.143  
  
Donc cela donne :  

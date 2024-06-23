
# 1. Découpage symétrique
Nous allons d'abord découper le réseau en quatre sous-réseaux de tailles égales.

Un /26 (255.255.255.192) donne 64 adresses IP (0-63, 64-127, 128-191, 192-255).

Voici les sous-réseaux résultants :


| Pôle  | Adresse  Réseau | CIDR | Adresses  Utilisables | Broadcast |
|---------|-------------- |----|---------------|--------------- |
| Informatique | 172.16.1.0 |/26 |172.16.1.1 - 172.16.1.62| 172.16.1.63
| Développement | 172.16.1.64 |/26| 172.16.1.65 - 172.16.1.126 | 172.16.1.127
| Administratif | 172.16.1.128 |/26|172.16.1.129 - 172.16.1.190 | 172.16.1.191
| Technicien | 172.16.1.192 | /26 |172.16.1.193 - 172.16.1.254 | 172.16.1.255 


# 2. Découpage asymétrique
Pour un découpage asymétrique, nous allons allouer des sous-réseaux de différentes tailles en fonction des besoins de chaque pôle.

Pôle Informatique (50 équipements)

Nécessite un sous-réseau de 64 adresses (prochaine puissance de 2 supérieure à 50)
CIDR: /26 (255.255.255.192)
Pôle Administratif (20 équipements)

Nécessite un sous-réseau de 32 adresses (prochaine puissance de 2 supérieure à 20)
CIDR: /27 (255.255.255.224)
Pôle Technicien (15 équipements)

Nécessite un sous-réseau de 32 adresses (prochaine puissance de 2 supérieure à 15)
CIDR: /27 (255.255.255.224)
Pôle Développement (12 équipements)

Nécessite un sous-réseau de 16 adresses (prochaine puissance de 2 supérieure à 12)
CIDR: /28 (255.255.255.240)
Voici les sous-réseaux résultants :

|Pôle | Adresse  Réseau | CIDR | Adresses Utilisables | Broadcast
|----|--------|----|--|----|
|Informatique | 172.16.1.0 | /26 | 172.16.1.1 - 172.16.1.62 | 172.16.1.63
|Administratif | 172.16.1.64 | /27 | 172.16.1.65 - 172.16.1.94 | 172.16.1.95
|Technicien | 172.16.1.96 | /27 | 172.16.1.97 - 172.16.1.12 | 172.16.1.127
|Développement | 172.16.1.128 | /28 | 172.16.1.129 - 172.16.1.142 | 172.16.1.143

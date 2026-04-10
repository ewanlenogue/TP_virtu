# 📡Adressage et VM

## 🌐Plage IP
IPs : 172.16.135.50 ==> 172.16.135.59

Masque : /16 | 255.255.0.0

## 🖥️ Les VM

### Information reseaux :
TAG : g5

| Nom          | Reseau          | IP               | Gateway        | user | mdp      |
|--------------|-----------------|------------------|----------------|------|----------|
| grp5-routeur | net0 (vmbr0)    | 172.16.135.50/16 | 172.16.255.254 | g5   | epsi1234 |
| grp5-routeur | net1 (VNetGRP5) | 10.100.50.10/24  | None           | g5   | epsi1234 |
| grp5-client  | net0 (VNetGRP5) | 10.100.50.11/24  | 10.100.50.10   | g5   | epsi1234 |

### Connexion ssh :

Pour la connexion a la VM (gr5-routeur) :
```bash
ssh g5@172.16.135.50
```

Pour la connexion a la VM (grp5-client) :
```bash
ssh g5@172.16.135.50 -p 2222
```

## SDN et Permissions :

### Zones :
ID : Grp5
Type : vxlan
MTU : 1450
IPAM : pve

### VNets :
ID : VNetGRP5
Zone : Grp5
Tag : 5

Subnet : 10.100.50.0/24
Gateway : 10.100.50.10

### Groups :
Name : Grp5
Users : Grp5_u1@pve,Grp5_u2@pve

### Users :
| User Name | Realm | Enabled | Expire | Name | TFA | Groups |
|:---------:|:-----:|:-------:|:------:|:----:|:---:|:------:|
|Grp5_u1    |pve    |Yes      |never   |      |No   |Grp5    |
|Grp5_u2    |pve    |Yes      |never   |      |No   |Grp5    |
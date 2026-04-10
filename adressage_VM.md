# 📡Adressage et VM

## 🌐Plage IP

| Élément         | Valeur                        |
|-----------------|-------------------------------|
| **Plage IP**    | 172.16.135.50 → 172.16.135.59 |
| **Masque**      | /16                           |
| **Subnet Mask** | 255.255.0.0                   |

## 🖥️ Les VM

### 🔧 Information reseaux :
TAG : g5

| Nom              | Reseau          | IP               | Gateway        | User | Mdp      |
|------------------|-----------------|------------------|----------------|------|----------|
| **grp5-routeur** | net0 (vmbr0)    | 172.16.135.50/16 | 172.16.255.254 | g5   | epsi1234 |
| **grp5-routeur** | net1 (VNetGRP5) | 10.100.50.10/24  | None           | g5   | epsi1234 |
| **grp5-client**  | net0 (VNetGRP5) | 10.100.50.11/24  | 10.100.50.10   | g5   | epsi1234 |

### Connexion ssh :

🖧 Routeur :
```bash
ssh g5@172.16.135.50
```

💻 Client :
```bash
ssh g5@172.16.135.50 -p 2222
```

## 🌐 SDN et Permissions :

### 🧩 Zone :
| Propriété | Valeur |
|------------|--------|
| **ID**    | Grp5   |
| **Type**  | vxlan  |
| **MTU**   | 1450   |
| **IPAM**  | pve    |


### 🔗 VNets :
| Propriété   | Valeur         |
|-------------|----------------|
| **ID**      | VNetGRP5       |
| **Zone**    | Grp5           |
| **Tag**     | 5              |
| **Subnet**  | 10.100.50.0/24 |
| **Gateway** | 10.100.50.10   |

### 👥 Groups :
| Nom      | Utilisateurs             |
|----------|--------------------------|
| **Grp5** | Grp5_u1@pve, Grp5_u2@pve |


### Users :
| Nom utilisateur | Realm | Actif  | Expiration | TFA    | Groupe |
|-----------------|-------|--------|------------|--------|--------|
| **Grp5_u1**     | pve   | ✅ Oui | Jamais    | ❌ Non | Grp5   |
| **Grp5_u2**     | pve   | ✅ Oui | Jamais    | ❌ Non | Grp5   |

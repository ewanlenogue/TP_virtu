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

### Port ssh depuis Wan : 
port : 2222

group : Grp5
user1 : p4eCF5u6
user2 : r8unCP56
pool : Grp5
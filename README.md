# tpHub-ARM

![Hub](./Hub.drawio.png)

1. Important :

* __Choix Subnet__  
- `Afin de Déployer nos ressources (Firewall, Bastion Gateway), on doit créer pour chacune des ressources un subnet Unique avec une convention de nommage spécifique`  
- `Exemple: pour le firewall on doit créer un subnet AzureFirewallSubnet`  
- `Chacune des ressources doit avoir un CIDR d'au moins /26`

* __Découpage__  
- ` Chaque Subnet présent dans notre Vnet en /16, possède une Host Address Range de 63 adresses IP, auxquelles on retire l'address de Broadcast 63 `  
- `Concrètement nous devons faire notre découpage de sorte qu'il n'y ait pas de "trous", ainsi on peut éviter le gaspillage`
- `Exemple: 10.16.0.0 - 10.62.0.64 - 10.16.0.128 le 63 et le 127 étant l'address de Broadcast`.
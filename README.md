# M04
Configuration de l’interface réseau FastEthernet0 du routeur Commençons par configurer l’interface réseau de ce routeur. Revenir maintenant dans la vue logique. Cliquer sur le routeur, puis aller dans l’onglet « Config » et choisir « FastEthernet0/0 ». Fixer l’adresse IPv4 192.168.50.254 et le masque 255.255.255.0. Enfin, cliquer sur la case à cocher On pour le « Port Status » pour activer le port FastEthernet0/0. Remarquez les commandes qui sont automatiquement saisies dans Equivalent IOS commands :
obsidian://open?vault=Langage%20de%20programmation&file=R%C3%A9seau%2FPNG%2FPasted%20image%2020231223005927.png
Création du pool DHCP et activation du service Sur le routeur, nous allons maintenant configurer le service DHCP et l’activer. Les adresses IP disponibles sont pour les machines sont rassemblées dans des pools. Vous allez paramétrer le pool DHCP du serveur pour lui indiquer toutes les adresses IP disponibles pour les machines. Dans notre cas, notre serveur DHCP pourra distribuer toutes les adresses IP du réseau 192.168.50.0/24 soit les adresses IP allant de 192.168.50.1 à 192.168.50.254. Nous exclurons l’adresse 192.168.50.254, puisque c’est l’adresse que le routeur possède. Il ne conviendrait pas que le routeur la distribue à une autre machine, sinon, cela créerait un conflit d’adresse IP. Ouvrir la configuration du serveur. Sélectionner l’onglet « CLI » : Comand Line Interface. Passer en mode administrateur en tapant la commande « enable » :
![[Pasted image 20231223010025.png]]

![[Pasted image 20231223010049.png]]
Afficher la configuration actuelle de votre routeur (vérifier que vous n’êtes plus en mode config) et taper la commande (vous trouverez ci-dessous un extrait des informations affichées) :
![[Pasted image 20231223010117.png]]
Sauvegarde de la configuration du routeur Pour sauvegarder la configuration du routeur, taper la commande :
![[Pasted image 20231223010141.png]]

![[Pasted image 20231223010407.png]]
![[Pasted image 20231223010518.png]]
Commande pour permettre d'empêcher le trafic entre le VLAN 10 et le VLAN 20.
![[Pasted image 20231223010613.png]]
Commande pour spécifier l'adresse du serveur DNS sur un routeur :
**Accéder à la configuration du routeur :**

- Utilisez la commande `enable` suivi du mot de passe si nécessaire, puis `configure terminal` pour entrer en mode de configuration globale.
- ![[Pasted image 20231223011444.png]]
**Accéder à l'interface connectée aux PC :**
![[Pasted image 20231223011217.png]]
**Configurer DHCP :**
![[Pasted image 20231223011324.png]]
**Spécifier l'adresse du serveur DNS :**
Utilisez la commande `dns-server <adresse_ip_du_serveur_dns>`
![[Pasted image 20231223011410.png]]



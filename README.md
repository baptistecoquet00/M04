# M04
# Switch
Mise en place des 2 VLAN La mise en place des 2 VLAN se fait exclusivement sur les switches. Tous les switches ne permettent pas la création de VLAN, il faut disposer de switches paramétrables. 
Création de 2 VLAN : 
Se placer sur le switch, ouvrir la CLI et taper les commandes suivnates pour créer le VLAN 10 nommé PME :

![Pasted image 20231223010300](https://github.com/baptistecoquet00/M04/assets/114006454/e56b135f-2867-4ee3-85d8-569cbcaaac21)


![Pasted image 20231223010317](https://github.com/baptistecoquet00/M04/assets/114006454/bf9f516c-9f76-4896-91fc-e268832b00ac)


![Pasted image 20231223010353](https://github.com/baptistecoquet00/M04/assets/114006454/18baaa86-e1cb-494b-9309-5c4ef4160f78)


# Routeur
Configuration de l’interface réseau FastEthernet0 du routeur Commençons par configurer l’interface réseau de ce routeur. Revenir maintenant dans la vue logique. Cliquer sur le routeur, puis aller dans l’onglet « Config » et choisir « FastEthernet0/0 ». Fixer l’adresse IPv4 192.168.50.254 et le masque 255.255.255.0. Enfin, cliquer sur la case à cocher On pour le « Port Status » pour activer le port FastEthernet0/0. Remarquez les commandes qui sont automatiquement saisies dans Equivalent IOS commands :
![Pasted image 20231223005927](https://github.com/baptistecoquet00/M04/assets/114006454/9c545b71-be66-4255-bedb-fbadfb7a02f9)

Création du pool DHCP et activation du service Sur le routeur, nous allons maintenant configurer le service DHCP et l’activer. Les adresses IP disponibles sont pour les machines sont rassemblées dans des pools. Vous allez paramétrer le pool DHCP du serveur pour lui indiquer toutes les adresses IP disponibles pour les machines. Dans notre cas, notre serveur DHCP pourra distribuer toutes les adresses IP du réseau 192.168.50.0/24 soit les adresses IP allant de 192.168.50.1 à 192.168.50.254. Nous exclurons l’adresse 192.168.50.254, puisque c’est l’adresse que le routeur possède. Il ne conviendrait pas que le routeur la distribue à une autre machine, sinon, cela créerait un conflit d’adresse IP. Ouvrir la configuration du serveur. Sélectionner l’onglet « CLI » : Comand Line Interface. Passer en mode administrateur en tapant la commande « enable » :

![Pasted image 20231223010025](https://github.com/baptistecoquet00/M04/assets/114006454/1754685c-e945-48d5-9f29-0b75ca8dff89)


![Pasted image 20231223010049](https://github.com/baptistecoquet00/M04/assets/114006454/09a9e3af-1b2f-43a4-ae20-2de8a4e18b07)

Afficher la configuration actuelle de votre routeur (vérifier que vous n’êtes plus en mode config) et taper la commande (vous trouverez ci-dessous un extrait des informations affichées) :

![Pasted image 20231223010117](https://github.com/baptistecoquet00/M04/assets/114006454/31ea79e8-cca2-4bbb-ad74-2aa01e3e57ea)

Sauvegarde de la configuration du routeur Pour sauvegarder la configuration du routeur, taper la commande :

![Pasted image 20231223010141](https://github.com/baptistecoquet00/M04/assets/114006454/18f0f9f6-909b-4a49-b4bc-c8573c331e49)


![Pasted image 20231223010407](https://github.com/baptistecoquet00/M04/assets/114006454/1ccad3fb-d44c-43c0-8571-505cc0d103e5)


![Pasted image 20231223010518](https://github.com/baptistecoquet00/M04/assets/114006454/8188d01a-c02d-478d-b41d-24078ac94234)




Commande pour permettre d'empêcher le trafic entre le VLAN 10 et le VLAN 20.

![Pasted image 20231223010613](https://github.com/baptistecoquet00/M04/assets/114006454/6a0809da-8ab4-401d-a579-e7df2573c323)


Commande pour spécifier l'adresse du serveur DNS sur un routeur :
**Accéder à la configuration du routeur :**

- Utilisez la commande `enable` suivi du mot de passe si nécessaire, puis `configure terminal` pour entrer en mode de configuration globale.
- ![Pasted image 20231223011124](https://github.com/baptistecoquet00/M04/assets/114006454/8141041a-ad05-45e7-a9df-a00bf595ed7e)

**Accéder à l'interface connectée aux PC :**

![Pasted image 20231223011217](https://github.com/baptistecoquet00/M04/assets/114006454/8e9185ed-e2c0-4633-acd6-096cc49d87f6)

**Configurer DHCP :**

![Pasted image 20231223011324](https://github.com/baptistecoquet00/M04/assets/114006454/db9702b3-f48c-4291-89b6-8f216a59d5ff)

**Spécifier l'adresse du serveur DNS :**
Utilisez la commande `dns-server <adresse_ip_du_serveur_dns>`

![Pasted image 20231223011410](https://github.com/baptistecoquet00/M04/assets/114006454/a3f2a61f-dbf6-4477-8e27-335e0eef873f)






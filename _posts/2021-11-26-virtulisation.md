---
layout: post
title: "Virtualisation with VirtualBox"
subtitle: "The Virtualisation it's so important in IT"
background: '/img/posts/vb_background.png'
---
##  Background
Dans le domaine informatique la virtuallissation est un atout indeniable pour realiser dess tests et des architectures isoles 
Machine hôte

La machine hôte représente la machine physique qui va "héberger" une ou plusieurs machines virtuelles.

VirtualBox est installé sur la machine hôte.

En anglais, on la nomme "Host".
Système hôte

Le système hôte représente le système d'exploitation (OS) (Windows, MacOS ou Linux) qui est installé sur la machine hôte.
Machine invitée

La machine invité représente la machine virtuelle qui sera allouée et gérée par l'hyperviseur VirtualBox.

On l'appelle aussi parfois "client" mais ce terme est moins adapté, il ne faut pas le confondre avec le client d'un système client/serveur.

En anglais, on la nomme "guest".
<img class="img-fluid" src="/img/posts/v1.png" alt="Demo Image">

    Configuration de la machine virtuelle

    Configuration de la machine virtuelle

Système invité

Le système invité représente le système d'exploitation (OS) qui est installé sur la machine virtuelle.

N'importe quel système d'exploitation peut être utilisé comme système invité sur VirtualBox.
Suppléments invités

Les suppléments invité (Guest Additions) sont une sorte de pack logiciel à installer sur la machine virtuelle pour optimiser son fonctionnement et ajouter de nouvelles fonctionnalités (dossiers partagés, glisser-déposer2, ajustement automatique de la résolution de l'écran, etc.). Les suppléments invité (Guest Additions) font partie de la licence GPLv2 donc libre d'utilisation 3.
Fonctionnalités
Hyperviseur de type 2

VirtualBox est un hyperviseur de type 2, c'est-à-dire qu'il doit être installé sur un système d'exploitation, et non directement sur un ordinateur en tant que système d'exploitation.
Systèmes hôtes

VirtualBox peut être installé sur les systèmes hôtes suivants4 :

    Linux (en 32 et 64 bits ; en .deb, en .rpm et en source)
    Mac OS X (10.9, 10.10 et 10.11 en 64 bits)
    Solaris (10 et 11 en 64 bits)
    Windows (XP, Vista, 7, 8, 8.1 et 10 en 32 et 64 bits)

À partir de VirtualBox v5.x, Windows XP n'est plus supporté.

    Windows Server (2008, 2008R2, 2012,2012 R2, 2016 et 2019 en 64 bits)
    FreeBSD
    Genode

Système invités

En tant qu'invité, il supporte5 :

    IBM OS/2 Warp ;
    Linux 2.x/3.x/4.x ;

    Debian, Red Hat/CentOS;

    FreeBSD, NetBSD, OpenBSD ;
    Mac OS X ;
    Windows, de 3.1 à 10 et pour les serveurs, de NT4 à 2019.

Disque VDI

Le VDI est le format d'enregistrement par défaut des disques durs virtuels pour VirtualBox6. Selon les choix de l'utilisateur lors de la création de ce disque, il peut avoir une taille fixe ou variable. La taille sera fixe si l'utilisateur a choisi "taille fixe" dans les options. Si l'utilisateur choisit 8 Go, le disque pèsera 8 Go et ce, sans possibilité de le modifier par la suite, même si cet espace se révèle insuffisant lors de l'utilisation de la machine virtuelle. Cependant si la taille est dynamiquement allouée, le disque occupera l'espace qu'il nécessite et il pourra augmenter cet espace jusqu'à la limite fixée par l'utilisateur. Néanmoins, la taille de ce disque ne pourra jamais être réduite. Le disque nécessitera de l'espace supplémentaire lorsque sur le système virtuel, des logiciels ou des fichiers seront installés par exemple.

Ces deux choix de stockage ont chacun avantages et inconvénients. Un disque de taille dynamiquement allouée utilise en gros simplement l'espace où sont écrites des données, au prix d'un léger surcoût en lecture/écriture, à la manière d'un logical volume manager (LVM) en Linux ou AIX. A contrario, une taille fixe occupe un espace fixe qui est mobilisé dès sa création, mais assure des performances proches d'un disque natif. En 2016 où une taille typique de disque est 1 To, et si l'on ne doit pas stocker des dizaines de machines virtuelles, 40 Go s'allouent typiquement en espace fixe.

Le VDI est récupérable facilement aussi comme fichier de disque dur virtuel : on copie aisément ce fichier, que l'on peut ensuite importer dans d'autres machines virtuelles devenant des copies conformes de la première. Cela permet une redondance des serveurs dans un réseau, et aussi des sauvegardes commodes.
Pack d'extension

Le logiciel peut être étendu au moyen de packs d'extension. L'éditeur en fournit un qui ajoute notamment le support de l'USB 2.0 (EHCI), l'USB 3 (xHCI), la webcam, la connexion directe à l'invité par RDP, le Boot PXE ou encore le chiffrement des images disques avec l'algorithme AES. Il est fourni sous une licence différente : VPUEL pour VirtualBox Personal Use and Evaluation License.
VBoxManage

VBoxManage est l'interface en ligne de commandes de VirtualBox. Cette interface intègre toutes les fonctions disponibles à partir de l'interface graphique (GUI) mais dispose également de commandes supplémentaires pour la gestion, le contrôle et la configuration des machines virtuelles. On peut par exemple démarrer et arrêter une machine virtuelle en ligne de commande.

Quelques exemples :

    Création d'une machine virtuelle avec enregistrement : VBoxManage createvm --name "[[SUSE]] 10.2" --register​
    Modification de la quantité de mémoire vive (RAM) d'une machine virtuelle : VBoxManage modifyvm "Windows XP" --memory 512​
    Démarrage d'une machine virtuelle : VBoxManage startvm "[[Ubuntu]] 15.04"​

Licence (GPL2, CDDL et VPUEL)

VirtualBox est libre d'utilisation pour sa partie principale mais les Add-on, quant à eux, sont disponibles uniquement pour un usage privé, à titre privé. En bref, il est interdit d'utiliser les Add-on en entreprise ou en université.
Historique

Après plusieurs années de développement, VirtualBox a été publié par InnoTek en Allemagne sous la licence GNU GPL v2 en janvier 2007. Le 12 février 2008, Sun Microsystems a annoncé un accord d'acquisition d'InnoTek.
Versions 1.x
version 1.6

La version 1.6.0 de VirtualBox est sortie le 30 avril 20087, elle inclut les principales nouveautés suivantes :

    Prise en charge des hôtes Solaris et Mac OS X.
    Prise en charge du "Seamless windowing" pour les invités Linux et Solaris.
    Le supplément Client "Guest Additions" pour Solaris.
    Une API de service web.
    Contrôleur AHCI pour les disques durs SATA.
    Prise en charge expérimentale du PAE (Physical Address Extension).

Cette version n'est plus supportée.

Première version : v1.6.0 (30/04/2008)

Dernière version : v1.6.6 (26/08/2008)
versions 2.x
version 2.0

La version 2.0.0 de VirtualBox est sortie le 4 septembre 2008, elle intègre notamment des fonctionnalités supplémentaires8 dont le support des hôtes 64 bits, une interface Qt4 (Qt3 dans les versions précédentes) qui améliore l'intégration sous KDE et l'utilisation de l'interface native sous Mac OS X9.

Cette version n'est plus supportée.

Première version : v2.0.0 (04/09/2008)

Dernière version : v2.0.12 (20/10/2009)
version 2.1

La version 2.1.0 de VirtualBox est sortie le 17 décembre 2008. Cette version est une mise à jour importante, du fait des nouvelles fonctionnalités apportées10, à savoir :

    le support de la virtualisation matérielle (support des instructions VT-x et AMD-V) sur les hôtes Mac OS X.
    le support expérimental d'invité 64 bit sur des hôtes 32 bit.
    l'amélioration du support de la virtualisation sur les processeurs Intel Nehalem.
    le support expérimental de l'accélération 3D via OpenGL.
    le support expérimental des contrôleurs SCSI LsiLogic et BusLogic.
    le support VMDK/VHD support incluant les "snapshots".
    un nouveau moteur de NAT, plus fiable et ayant de meilleures performances, ainsi que le support de l'echo ICMP (ping).
    une nouvelle mise en œuvre de l'interface réseau pour les hôtes Windows et Linux, avec une configuration facilitée.

Cette version n'est plus supportée.

Première version : v2.1.0 (17/12/2008)

Dernière version : v2.1.4 (16/02/2009)
version 2.2

La version 2.2.0 de VirtualBox est sortie le 8 avril 200911, elle inclut les nouvelles fonctionnalités suivantes :

    Importation et l'exportation des machines virtuelles au format OVF (Open Virtualization Format).
    Ajout du mode réseau "hôte seul" (Host-Only).
    Optimisations de l'hyperviseur avec des gains significatifs de performance lorsque le "niveau de commutation" est élevé.
    Augmentation de la taille maximale de la mémoire pour les machines virtuelles à 16 Go sur les hôtes 64 bits.
    VT-x / AMD-V sont maintenant activés par défaut lors de la création de nouvelles machines virtuelles.
    USB (OHCI & EHCI) est maintenant activé par défaut lors de la création de nouvelles machines virtuelles (GUI Qt seulement).
    Support expérimental de l'USB pour les hôtes OpenSolaris.
    Dossiers partagés pour les invités Solaris et OpenSolaris.
    Accélération 3D OpenGL pour les invités Linux et Solaris.
    Ajout de l'API C en plus du C++, du Java, du Python et des services web.

Cette version n'est plus supportée.

Première version : v2.2.0 (08/04/2009)

Dernière version : v2.2.4 (29/05/2009)
versions 3.x
version 3.0

La version 3.0.0 de VirtualBox est sortie le 30 juin 2009. Les modifications les plus importantes sont12 :

    Les systèmes invités peuvent accéder à un maximum de 32 processeurs virtuels, mais seulement quand la machine hôte dispose des instructions VT-x ou AMD-V.
    Systèmes Windows invités : possibilité d’utiliser les applications et les jeux DirectX 8 et 9 (expérimental).
    Support d’OpenGL 2.0 pour les systèmes invités Windows, Linux et Solaris.

Cette version n'est plus supportée.

Première version : v3.0.0 (30/06/2009)

Dernière version : v3.0.14 (18/03/2010)
version 3.1

La version 3.1.0 de VirtualBox est sortie le 30 novembre 200913.

Cette version n'est plus supportée.

Première version : v3.1.0 (30/11/2009)

Dernière version : v3.1.8 (10/05/2010)
version 3.2

Le 20 avril 2009, Oracle Corporation rachète Sun Microsystems. La version 3.2.0, sortie le 18 mai 2010, est la première version officiellement publiée par Oracle Corporation. Le logiciel est renommé à cette occasion Oracle VM VirtualBox14.

Cette version n'est plus supportée depuis juin 2015.

Première version : v3.2.0 (18/05/2010)

Dernière version : v3.2.28 (19/05/2015) 
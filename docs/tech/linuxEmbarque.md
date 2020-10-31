#<center>Linux Embarqué</center>
<font size="2"><center><span style="color:grey">Laurent MASSON</span></center></font>

<center><img src="https://www.techspot.com/images2/downloads/topdownload/2014/05/linux.png" alt="drawing" width="200"/></center>

##<center>Jour 1</center>
***
###INTRODUCTION

**Organisation du cours:**

La matière sera évalué avec:

- Un présentation orale en anglais (2-3 points)
- Une interro: 50% Cours / 50% Autres (8-9 points)
- Des TPs (8-9 points)

Pas de stresse, c'est pas un cours universitaire. Plutôt une formation d'entreprise.

Dans l'idée on va bosser [Linux][1] ! 

Soyez cool et participez !


*8h30, petit tour de table, présentation, etc.*

***
Etape exploratoire
Prérequis: toolchain(cross compil, binoutils, flasher)
Conception (choix du bootloader, choix du noyau, config du bootloader, rootfs, busybox, bibiliotèques)

***


##<center>Jour 2</center>
***
###TP0: préparation

On commence par noter l'adresse physique du Pc qui servira aux manips pour l'identifier sur le réseau via le [DHCP][2] du prof.

Pour sécuriser la connexion [SSH][3] entre notre groupe et le serveur (ordi du prof) on créer une paire de clé [rsa][4] avec PuTTyGEN.

On lance Putty, dans connection/Data, mettre le nom du groupe dans Auto-login
Puis dans ssh/Auth/"Private key file" et sélectionner la clé privé sauvegarder avant.

On configure le SSH:

Dans session: Host name : `192.168.1.10`, puis on save session :sshlinux et cliquer sur save.

On a utiliser Filezilla pour récupérer des documents sur le serveur via le protocole [SFTP][5].

A présent on set-up la connexion série entre la box et le pc de manip.

La variable exécutée au démarrage est: `bootcmd`
Son équivalent pour un démarrage pour disque dur est: `run boot_hda_hda`
Sauvegarder les variables même après poweroff: **saveenv**
Modifier la variable de démarrage pour démarrer sur un disque dur: `setenv bootcmd "run boot_hda_hda"`


***
###TP1: Hello World

On a créer un fichier .c faisant Hello World.
via FileZilla on le transfert sur le serveur. Via gcc ça fonctionne
Via sh4... ça marche pas mais c'est fait exprès

On voit grâce au readelf que le programme compiler pour l’ordinateur est en architecture 64bit contrairement a celui dédié a la box qui est en 32bit.

On essaye de monter la clé usb wtf

Pour monter la clé usb:

```bash
- mkdir montage
- mount /dev/sdb1 /wymedia/montage/
```

**TADA**

***
###TP2: Gestion de ventilateur

Pour gérer la vitesse du ventilateur on a chercher le fichier dans lequel est stocker la valeur du pwm du moteur.

Ce fichier est: `/sys/devices/platform/stm-pwm/pwm1`

Pour pouvoir modifier la valeur il faut désactiver la gestion automatique du ventilateur en tapant: `ngc -d wyclimd`


***
###TP3: Utilisation de Git
```bash
mkdir TP3
cp TP2 TP3
cd /TP3
git init
git add .
git commit -m Vitesse 
git branch smooth
git checkout smooth
git commit -m Smooth 
```

***
###TP4: Script Bash
```bash
#!/bin/bash

if [ "$1" == "sh4" ] ; then
    export PATH=$PATH:/opt/STM/STLinux-2.3/devkit/sh4/bin/sh4-linux-gcc
    echo "édité"
    
elif [ "$1" == "x86" ] ; then
    export PATH="Le PATH original"
    echo "édité"

else
    echo "Erreur, met le paramètre abruti"
fi

```


***
###TP5: Compiler le Kernel

```bash
tar -xjf kernel-wyplay.tar.bz2
```

Dans le Makefile un commentaire indique que pour spécifier l'archtecture on peut le mettre en argument du make `make ARCH=ia64`, ou en ajoutant un variable d'environnement correspondante

On modifie donc le script:

```bash
#!/bin/bash

if [ "$1" == "sh4" ] ; then
    export ARCH=sh
    export CROSS_COMPILE=sh4-linux-
    export PATH=$PATH:/opt/STM/STLinux-2.3/devkit/sh4/bin/
 
    echo "édité"
    
elif [ "$1" == "x86" ] ; then
    export ARCH=
    export CROSS_COMPILE=
    export PATH= "Le PATH original"
    echo "édité"

else
    echo "Erreur, met le paramètre abruti"
fi

```

PARTIE 2

```bash
source script.sh sh4
cd Cours/soucres/TP05-kernel/kernel-wyplay
make help
make wymdbox01_defconfig
make uImage -j
```

##<center>Jour 3</center>
***
###TP6: Bootloader en NFS
```bash
cd Cours/soucres/TP05-kernel/kernel-wyplay/arch/sh/boot
cp uImage ~/boot/
```

NFS     Appropriate NFS support is enabled.

SERIAL  Serial support is enabled.

Recherches:
>`nfsaddrs=` [NFS] :Deprecated.  Use ip= instead. See Documentation/filesystems/nfs/nfsroot.txt.

>`nfsroot=` [NFS] :nfs root filesystem for disk-less boxes.See Documentation/filesystems/nfs/nfsroot.txt.

>`nfs.enable_ino64=` [NFS] :enable 64-bit inode numbers. If zero, the NFS client will fake up a 32-bit inode number for the readdir() and stat() syscalls instead of returning the full 64-bit number. The default is to return 64-bit inode numbers.

>`acpi_no_auto_serialize`  [HW,ACPI] :Disable auto-serialization of AML methods AML control methods that contain the opcodes to create named objects will be marked as "Serialized" by the auto-serialization feature. This feature is enabled by default. This option allows to turn off the feature.


Dans le boot loader on modifie certain paramètre comme suivant:

```bash
setenv bootcmd "run boot_nfs_nfs"
saveenv

```


***
###TP7: Gestion des LEDS

On repère dans le schéma éléctrique que les led sont appeller:
>PIO1_3/SC1CG_CLK/DSSMCD_CLK
>PIO1_4/NRSSA_CLKOUT/ASC1_CTS
>PIO1_5/NRSSA_DATAIN/ASC1_RTS

On a ajouter des lignes dans
```bash
/home/groupe5/Cours/TP05-kernel/kernel-wyplay/arch/sh/boards/st/wymdbox01/gpio.c
```

```cpp
pio_ptr = stpio_request_set_pin(1, 3, "LED3", STPIO_OUT, 1);
pio_ptr = stpio_request_set_pin(1, 4, "LED2", STPIO_OUT, 1);
pio_ptr = stpio_request_set_pin(1, 5, "LED1", STPIO_OUT, 1);
```

Puis on a recompiler le kernel
```bash
cd TP/TP4/
source script.sh sh4
cd Cours/soucres/TP05-kernel/kernel-wyplay
make help
make wymdbox01_defconfig
make uImage -j

cp Cours/soucres/TP05-kernel/kernel-wyplay/arch/sh/boot/uImage ~/boot/
```

**TADAM on a les leds qui brillent**

***
###TP8 : Compilation statique


***
###TP9 : Création d'un rootfs

Pour la création de l'architecture
```bash
mkdir -p {boot,dev,etc,lib,usr,bin,sbin,usr/bin,proc,sys,var,root,home,mnt,opt,tmp,media}
```
On attend le prof pour le MAKEDEV*

On *make* les modules via:

```bash
cd TP/TP4/
source script.sh sh4
cd Cours/soucres/TP05-kernel/kernel-wyplay
make help
make modules
export INSTALL_MOD_PATH=~/rootfs/
make modules_install
```


***
###TP10 : Création du initramfs

**On le fait pas**

***
###TP11 : Compilation de busybox
```bash
cd ~/Cours/sources/TP11-busybox/busybox
tar -xjf busybox.tar.bz2
make menuconfig
```
On choisi plein de trucs...c'est chiant

Pour le cross-compile de busybox on fait `make busybox`

On positionne dans menuconfig: `/home/groupeX/rootfs`

`make install`

`setenv stlinux /home/groupe5/rootfs/`

`setenv bootfile ../boot/uImage` 

##<center>Jour 4</center>

***
###TP12 : libc

On va dans *~/Cours/sources*, on copie libc.tar.bz2 dans *~/rootfs*
On décompresse via `tar -xjf libc.tar.bz2`

On lance le programme

**TADAM ça marche !!**


***
###TP13 : L'Init

On créer un script qui monte ce qu'il faut correctement

Pour se faire on a d'abord modifier une variable systeme de uImage, il s'agit de la variable *arg_kgdb*, on y met dedans `init=/sbin/script.sh`. Cette modification permet de lancer notre programme init.

```bash
#!/bin/bash
echo "Debut montage"
/bin/mount proc /proc/ -t proc
/bin/mount sys /sys/ -t sysfs
echo "Fin montage"
```

***
###TP14 : Le Process d'Init

`setenv arg_kgdb init=/sbin/init.sh`
`saveenv`

On cherche le module a charger en RAM
Il faut ensuite le charger

`depmod -ae`
`modprobe stm-pwm`

On modifie notre script **init.sh**:
```bash
#!/bin/bash

echo "Debut montage"
/bin/mount proc /proc/ -t proc
/bin/mount sys /sys/ -t sysfs
echo "Fin montage"

echo "On va bientot allumer le ventilo"
source /sbin/fan start
echo "Le ventilo doit tourner"

/bin/bash
```

Et on créer un script **fan.sh** qui permettra via un paramètre de lancer ou arreter le ventilateur:
```bash
#!/bin/bash

depmod -ae
modprobe stm-pwm
echo "Module chargé"

if [ "$1" == "start" ] ; then
    echo "On allume le ventilateur"
    echo 255 > /sys/devices/platform/stm-pwm/pwm1

    echo "Ventilateur allumé"


elif [ "$1" == "stop" ] ; then
    echo "On eteint le ventilateur"
    echo 0 > /sys/devices/platform/stm-pwm/pwm1

    echo "Ventilateur eteint"


else
    echo "met le paramètre abruti"

fi
```
























[1]: https://fr.wikipedia.org/wiki/Linux
[2]: https://fr.wikipedia.org/wiki/DHCP
[3]: https://fr.wikipedia.org/wiki/Secure_Shell
[4]: https://fr.wikipedia.org/wiki/Chiffrement_RSA
[5]: https://fr.wikipedia.org/wiki/SSH_File_Transfer_Protocol
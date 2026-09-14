Une analyse croisée entre la mémoire vive et l’image disque a été réalisée afin de relier les processus actifs aux fichiers présents sur le système.

Dans la mémoire, Volatility a permis de retrouver plusieurs processus Res.exe.

Sur l’image disque, FTK Imager a permis de retrouver les fichiers suivants :

C:\WindSyst\Env.exe
C:\WindSyst\Res.exe
C:\WindSyst\log.txt

Le processus Res.exe retrouvé dans la RAM correspond donc bien à un fichier présent sur le disque.

Une persistance a également été identifiée dans la clé de registre :

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

avec :

Res -> C:\WindSyst\Res.exe
Env -> C:\WindSyst\Env.exe

Cela montre que le malware cherche à se relancer automatiquement à l’ouverture de session.

Le fichier log.txt présent sur le disque contient bien les frappes clavier enregistrées par le malware.

Ces différents éléments permettent de confirmer que les données retrouvées dans la RAM, sur le disque et dans le registre sont cohérentes entre elles et correspondent au même comportement malveillant.

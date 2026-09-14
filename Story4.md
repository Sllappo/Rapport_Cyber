
## Analyse du comportement

Le malware `env.exe` a été exécuté dans une machine virtuelle isolée afin d'observer son comportement réel.

Avant son exécution, un état de référence du système a été réalisé avec `tasklist` et `netstat` afin de pouvoir comparer les processus et connexions réseau avant et après le lancement du malware.

### Capture des frappes clavier

Lors de l'analyse statique avec Ghidra, un fichier suspect avait été identifié à l'emplacement suivant :

`C:\WindSyst\log.txt`

Après exécution du malware, ce fichier a bien été créé/utilisé.

Des caractères saisis au clavier pendant l'exécution ont ensuite été retrouvés dans `log.txt`.

Cela permet de confirmer dynamiquement que le malware possède bien un comportement de keylogger et enregistre les frappes clavier de l'utilisateur.

### Création / modification de fichier

Le fichier suivant a été observé :

`C:\WindSyst\log.txt`

Ce fichier est utilisé pour stocker les frappes clavier capturées.

Cette observation confirme les éléments identifiés précédemment lors de l'analyse statique, notamment la présence de fonctions d'écriture comme `fwrite`.

### Analyse réseau avec Wireshark

Une capture réseau a été réalisée pendant l'exécution du malware.

L'hypothèse d'un envoi des données par e-mail, identifiée lors de l'analyse statique, n'a donc pas pu être confirmée pendant cette analyse dynamique.


L'analyse dynamique permet de confirmer le comportement principal du malware.

Le programme agit bien comme un keylogger :

1. Il capture les frappes clavier de l'utilisateur.
2. Il enregistre les données capturées dans `C:\WindSyst\log.txt`.

En revanche, aucune exfiltration réseau vers `smtp.gmail.com` n'a été observée durant la période de capture.

L'analyse dynamique confirme donc le mécanisme de capture et de stockage des frappes clavier, mais ne permet pas encore de confirmer leur transmission par e-mail.

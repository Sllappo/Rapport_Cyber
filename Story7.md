Une image du disque logique `C:` a été réalisée avec FTK Imager.

L'image a été enregistrée sur un second disque virtuel `E:` afin de ne pas modifier le disque source pendant l'acquisition.

L'option de vérification de l'image a été activée afin de contrôler l'intégrité de l'acquisition à l'aide des hashes générés par FTK Imager.

L'analyse de l'image disque a permis de retrouver plusieurs fichiers liés au malware dans :

`C:\WindSyst\`

Fichiers identifiés :

- `C:\WindSyst\Env.exe`
- `C:\WindSyst\Res.exe`
- `C:\WindSyst\log.txt`

Ces éléments correspondent aux artefacts déjà identifiés lors des analyses statique, dynamique et mémoire.

J'arrive aussi à voir les log contenue dans le fichier log.txt du malware.

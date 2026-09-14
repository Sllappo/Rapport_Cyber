Le niveau de risque est très élever car il capture chaque entrée du clavier, et les envoies ensuite par mail, le fichier est dur à détecter car il est à la racine de la machine après s'être copier dessus, il se relance aussi à chaque démarrage grâce aux clés de registre qu'on as trouver via : ` reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" `

Pour se protéger, on isole la machine, on supprime le malware et sa persistance dans le registre, on analyse complètement le poste, puis on change les mots de passe saisis sur la machine car ils ont pu être enregistrés par le keylogger.

Pour éviter ce type d’infection, il faut éviter d’exécuter des fichiers non fiables, garder l’antivirus et le système à jour, limiter les droits administrateur et surveiller les mécanismes de persistance comme les clés Run.

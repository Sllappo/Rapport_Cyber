Le dump mémoire a été analysé avec Volatility 3.

La commande utilisée est :

```cmd
py vol.py -f "C:\Forensic\memory.raw" windows.info
```
puis

```cmd
py vol.py -f "C:\Forensic\memory.raw" windows.pslist
```

L'analyse du dump RAM avec Volatility 3 a permis d'identifier plusieurs instances du processus `Res.exe`.

Trois processus ont été retrouvés :

- PID `12884`
- PID `12032`
- PID `9032`

Les trois processus possèdent le même processus parent, avec le PPID `8028`.

Ce comportement est cohérent avec la persistance observée précédemment dans la clé de registre `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`, où `Res.exe` était configuré pour être lancé automatiquement.

Aucune instance de `Env.exe` n'a été retrouvée avec `windows.pslist` au moment du dump.

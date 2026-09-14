Decryptage avec Ghidra : 

Sur le mémory map j'ai toruver le .text qui relie le env.exe et qui nous sort cette fonction : UndefinedFunction_0040100


On as vue dans les imports qu'il y as des fonctions de KeyPress qui correspondent potentiellement à un catch des touches presser

Après recherche de string : j'ai trouver la création d'un fichier log.txt à cet adress : "c:\\WindSyst\\log.txt"	"c:\\WindSyst\\log.txt"

suite à cette recherche j'ai aussi trouver qu'il y avait une adresse email lier au .exe :	"smtp.gmail.com" "aaaaaaaaaaaa@gmail.com"	

<img width="911" height="661" alt="image" src="https://github.com/user-attachments/assets/cf745b04-4f88-40fa-85d9-48e6404e83d1" />

Ainsi que des fonctions SendMail etc 

<img width="1325" height="103" alt="image" src="https://github.com/user-attachments/assets/bb7c8ef3-fce1-465f-bf5e-b79821f6d323" />


J'ai aussi trouver des traces de fwrite qui correspondent à l'écriture dans un fichier.


| Type | IOC | Interprétation |
|---|---|---|
| Fonctions clavier | Fonctions de type `KeyPress` trouvées dans les imports | Indice comportemental de capture des frappes clavier |
| Fichier | `C:\WindSyst\log.txt` | Fichier potentiellement utilisé pour stocker les frappes clavier |
| Dossier | `C:\WindSyst\` | Répertoire utilisé par le malware |
| Adresse e-mail | `aaaaaaaaaaaa@gmail.com` | Adresse potentiellement utilisée comme destinataire des données |
| Serveur SMTP | `smtp.gmail.com` | Infrastructure potentiellement utilisée pour l’envoi de mails |
| Fonction | `fwrite` | Indice comportemental d’écriture dans un fichier |
| Fonction | `SendMail` | Indice comportemental d’un mécanisme d’envoi de données |

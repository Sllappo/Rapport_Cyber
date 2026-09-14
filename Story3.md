Decryptage avec Ghidra : 

Sur le mémory map j'ai toruver le .text qui relie le env.exe et qui nous sort cette fonction : UndefinedFunction_0040100


On as vue dans les imports qu'il y as des fonctions de KeyPress qui correspondent potentiellement à un catch des touches presser

Après recherche de string : j'ai trouver la création d'un fichier log.txt à cet adress : "c:\\WindSyst\\log.txt"	"c:\\WindSyst\\log.txt"

suite à cette recherche j'ai aussi trouver qu'il y avait une adresse email lier au .exe :	"smtp.gmail.com" "aaaaaaaaaaaa@gmail.com"	

<img width="911" height="661" alt="image" src="https://github.com/user-attachments/assets/cf745b04-4f88-40fa-85d9-48e6404e83d1" />

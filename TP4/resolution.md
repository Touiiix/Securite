Ici on change l'id (bid) du panier pour acceder a un panier de quelqu'un d'autre.  
C'est du a un manque de verification du navigateur de l'utilisateur, le site lui fait confiance dans les données qu'il envoie.  
Pour régler ce probleme il faut vérifier si l'id de l'utilisateur et celui du panier correspondent.  
<img width="1089" height="479" alt="image" src="https://github.com/user-attachments/assets/4b37caba-156d-4374-b219-fcd4929d9126" />
voici le flag : aac58cc7ac1d092f7d1a08dcd826b64554e6ad5b

Ici on trouve l'email de l'admin : admin@juice-sh.op  
<img width="338" height="237" alt="image" src="https://github.com/user-attachments/assets/22c30ca9-ef83-47b7-b553-a5e75fb54c40" />

voici les flags pour la connection au compte admin  
<img width="771" height="211" alt="image" src="https://github.com/user-attachments/assets/9fdf7ba4-05ad-42a6-ab29-0d31eaaef5cd" />

Pour y arriver on utlise fuff avec cette commande qui va chercher dans une liste de mot de passes : 
```
ffuf -w ./ma_liste.txt -X POST \
  -u http://127.0.0.1:3001/rest/user/login \
  -H 'Content-Type: application/json' \
  -d '{"email":"admin@juice-sh.op","password":"FUZZ"}' \
  -mc 200 -fr 'Invalid email or password' \
  -t 5 -s | head -n 1

```
Et il nous renvoie admin123

Ici quand on crée un compte dans le champ JSON on ajoute le role admin (il manque la virgule a la fin de la ligne)
<img width="789" height="586" alt="image" src="https://github.com/user-attachments/assets/b7da10f6-37a5-49cf-a36f-a67b1519562c" />
<img width="509" height="107" alt="image" src="https://github.com/user-attachments/assets/0006fbfb-954c-4d59-a08a-a6cf5b28c551" />



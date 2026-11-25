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
<img width="650" height="451" alt="image" src="https://github.com/user-attachments/assets/b7efacf1-304d-4793-8cc9-1eab6e97ee0e" />

Quand on modifie la quantité dans le api/basketItems et qu'on la met en négatif on peut faire ce qui suit
<img width="782" height="464" alt="image" src="https://github.com/user-attachments/assets/75b41432-6353-4b1f-910c-ea616b974c4e" />
(pas faire attention au nombres qui sont pas les memes j'ai du refaire le screen d'au dessus)
<img width="755" height="316" alt="image" src="https://github.com/user-attachments/assets/a6593f42-1613-4bcd-bef2-7bd8be1f0caa" />
<img width="397" height="89" alt="image" src="https://github.com/user-attachments/assets/4e68562a-2cfa-4492-94e9-397d97b73292" />
<img width="679" height="209" alt="image" src="https://github.com/user-attachments/assets/fdc275c6-f0d3-4004-9b76-6407063cfff9" />

Ici on trouve l'id du panier qui était en base64 dans le token JWT
<img width="944" height="45" alt="Capture d&#39;écran 2026-11-25 155246" src="https://github.com/user-attachments/assets/0095f917-c92c-4bc6-943f-29dbf31aa4fc" />
<img width="523" height="90" alt="Capture d&#39;écran 2026-11-25 161217" src="https://github.com/user-attachments/assets/e6f02345-d7c7-4840-985b-f82261845bbb" />
voici le panier de l'utilisateur a qui j'ai rajouté des items
<img width="701" height="449" alt="image" src="https://github.com/user-attachments/assets/39263e95-47b2-44b7-8625-0b1b777cca37" />

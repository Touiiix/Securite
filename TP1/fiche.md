# TP1 — Fiche de renseignement ACME-BE (nom, prénom)
## Trouvailles
| # | Information | Source (page / fichier) | Méthode (outil, commande) | Fuite volontaire ? |
|---|---|---|---|---|
| 1 | wifi invités SSID : ACME-Guest mdp : ACME{zoom_sur_le_post_it} | http://localhost:8080/files/equipe-2024.jpg  | recherche dans la mediatheque  | non  |
| 2 | oubli de retirer l'autoindex | http://localhost:8080/files/notes.txt | recherche dans la médiatheque | non |
| 3 | siege se trouve a louvain la neuve | metadonnées de l'image siege.jpg | grace a exiftool on peut avoir les métadonnées qui nous donne la longitude et latitude il suffit de l'entrer dans google maps | non |
| 4 | le rapport 2025 a été fait par j.Lefevre avec Microsoft Word 2019 le 14 octobre 2026 | grace a exiftool on peut connaitre la personne qui a créé et modifié le fichier, on peut connaitre l'outil utilisé et la date de création/modification | non |

## Flags
| # | Flag | Où | Comment |
|---|---|---|---|
| 1 | ACME{zoom_sur_le_post_it}  | http://localhost:8080/files/equipe-2024.jpg | dans la médiatheque en cliquant sur une image | 
| 2 | ACME{docx_chemin_interne} | procedure-vpn.docx | dans la médiatheque et je le converti en .txt pour le lire |
| 3 | ACME{html_source_oublie} | code de la page | F12 pour accéder a l'outil d'inspection |
| 4 | ACME{pdf_metadata_auteur} | metadonées du pdf | exiftool |
| 5 | ACME{exif_garde_tout} | métadonnées de l'image siege.jpg | exiftool |
## Le kit du fraudeur
(qui viser, au nom de qui, quelle adresse, quand, quels détails, quel portail — chaque
ligne sourcée)
## Le phishing kit (mission 6)
(ce qui trahissait le faux portail ; pourquoi le MFA et le gestionnaire de mots de
passe protègent)
## Recommandations pour ACME (3, dont une anti-phishing)
## Une action pour moi

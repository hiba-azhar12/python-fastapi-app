# SECURITY-NOTES – Sécurité des actions tierces

**Q3.** Épingler une version (@v4) fixe le code exécuté : le résultat est reproductible. @main est une branche qui change à chaque commit : une modification cassée, ou malveillante en cas de compromission du dépôt de l'action, serait exécutée au prochain run sans que nous ayons rien changé (attaque de la chaîne d'approvisionnement). Pour une sécurité maximale, on peut même épingler le SHA complet d'un commit.

**Q4.** Non. Le badge « créateur vérifié » atteste de l'identité de l'éditeur, pas de la qualité ni de l'innocuité du code. Un compte ou un dépôt vérifié peut être compromis, ou contenir une faille ou une dépendance vulnérable. Il faut donc toujours relire l'action et épingler sa version.

**Q5.** (1) Lire le code source de l'action (action.yml et les scripts) pour vérifier ce qu'elle fait réellement, notamment l'accès aux secrets et les appels réseau. (2) Évaluer le fournisseur : maintenance active, étoiles, issues ouvertes, historique des versions. On épingle aussi un SHA de commit et on limite les permissions du GITHUB_TOKEN à ce qui est nécessaire.

# TP6 – Variables d'environnement, Inputs et Outputs

**Q1.** GITHUB_ENV est un fichier. Écrire dedans ne modifie pas l'environnement du step en cours, dont le processus a déjà démarré. Le runner lit ce fichier à la fin du step et injecte les variables dans les steps suivants.

**Q2.** Dans le job verify-env, $APP_NAME est vide. La portée de GITHUB_ENV est donc limitée aux steps suivants du même job : un autre job s'exécute sur un autre runner, avec un environnement vierge.

**Q3.** Avec >, chaque écriture remplace tout le fichier GITHUB_OUTPUT : seule la dernière ligne subsiste, le premier output est perdu (vide). Il faut >> pour ajouter à la suite.

**Q4.** GITHUB_ENV a une portée limitée à un job, car chaque job tourne sur un runner distinct. GITHUB_OUTPUT, déclaré dans outputs: du job, est stocké par GitHub et accessible aux jobs dépendants via needs.

**Q5.** Sans needs: build, deploy démarre en parallèle de build, et needs.build.outputs.full_version est vide : la version déployée est vide.

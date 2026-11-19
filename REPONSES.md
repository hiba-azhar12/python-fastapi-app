# TP7 – Actions tierces et actions personnalisées

**Q1.** actions/checkout a une valeur par défaut pour tous ses paramètres : dépôt courant, commit qui a déclenché le run, token automatique. setup-node doit savoir quelle version de Node installer : sans with, on ne maîtrise pas la version utilisée.

**Q2.** Chaque job s'exécute sur un runner distinct et vierge. report.txt est généré pendant l'exécution de build et n'est pas committé dans le dépôt : verify ne peut donc pas le trouver même si les deux jobs partagent le même dépôt. Les artefacts permettent de transférer des fichiers d'un job à l'autre.

**Q6.** Une action locale est lue depuis les fichiers du dépôt présents sur le runner. Tant que actions/checkout n'a pas copié le dépôt, le dossier .github/actions/... n'existe pas et l'appel échoue.

**Q7.** Dans une action composite, les steps run n'héritent d'aucun shell par défaut : shell: est obligatoire. L'action doit fonctionner dans n'importe quel workflow et sur n'importe quel runner, elle précise donc elle-même l'interpréteur.

## Comparaison composite et Docker

Le step de l'action composite s'est exécuté en  s. Le step de l'action Docker a pris  s, car il faut construire l'image à partir du Dockerfile avant de démarrer le conteneur.

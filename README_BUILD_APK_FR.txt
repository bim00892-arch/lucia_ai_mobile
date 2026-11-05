LUCIA AI — Génération de l'APK Android non signé

Ce projet contient un workflow GitHub Actions pour compiler l'application dans un environnement Android configuré.

ÉTAPES
1. Décompressez le ZIP.
2. Créez un dépôt GitHub privé et envoyez-y le contenu du dossier lucia_ai_mobile.
3. Dans GitHub > Actions, sélectionnez « Build LUCIA Android APK ».
4. Cliquez sur « Run workflow ».
5. Lorsque l'exécution est terminée, ouvrez-la et téléchargez l'artefact « LUCIA-Android-unsigned-APK ».
6. Ouvrez Android Studio, choisissez Build > Generate Signed Bundle / APK > APK, sélectionnez l'APK non signé et créez/utilisez votre clé de signature.

IMPORTANT
- L'APK issu du workflow est non signé.
- Gardez votre fichier de clé (.jks) et ses mots de passe en lieu sûr.
- Ne mettez jamais la clé privée dans GitHub ni dans le ZIP partagé.
- Le workflow cloud n'a pas encore été exécuté ici : la compilation reste à effectuer dans GitHub Actions.

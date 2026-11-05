# LUCIA AI — projet Android

Ouvrir ce dossier dans Android Studio (JDK 17, SDK 35). La page locale est embarquée dans `app/src/main/assets/public/`. Le pont `LuciaNativeVault` chiffre clé API, mémoire et historique avec AES-GCM et une clé conservée dans Android Keystore.

## Générer l'APK non signé dans le cloud

1. Décompresser ce projet et importer le dossier `lucia_ai_mobile` dans un dépôt GitHub privé.
2. Dans GitHub, ouvrir l'onglet **Actions**, choisir **Build LUCIA Android APK**, puis **Run workflow**.
3. À la fin du travail, télécharger l'artefact `LUCIA-Android-unsigned-APK`.
4. Signer l'APK avec votre propre clé de signature (Android Studio : **Build > Generate Signed Bundle / APK > APK**). Conserver cette clé et son mot de passe en lieu sûr : ils seront nécessaires pour les mises à jour.

Le workflow compile une variante `release` non signée. Il ne publie pas l'application et ne crée ni ne stocke de clé privée. Ne jamais envoyer votre clé de signature ou votre mot de passe dans le dépôt GitHub.

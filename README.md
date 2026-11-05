# LUCIA AI 0.8 — application Android native

Cette version contient un véritable projet Android (WebView locale + code Java), et non uniquement une PWA. Identifiant : `fr.lucia.ai`.

## Sécurité et mémoire
- Clé API, mémoire personnelle et historique enregistrés dans un coffre natif chiffré AES-GCM.
- Clé AES créée et conservée dans Android Keystore ; seuls les textes chiffrés sont stockés dans les préférences privées de l'application.
- Sauvegardes Android désactivées afin d'éviter la copie automatique des secrets vers une sauvegarde non maîtrisée.
- Migration depuis les paramètres et historiques CORINNE/LUCIA des versions précédentes.
- Historique conservé jusqu'à 500 messages ; export JSON manuel toujours possible depuis l'interface.
- En mode navigateur/PWA, le coffre natif n'existe pas : le stockage local web reste moins protecteur. La clé API y est stockée dans un espace distinct, mais sans chiffrement natif.

## Compiler et installer sur Android
Prérequis : Android Studio, JDK 17, Android SDK Platform 35 et Android Gradle Plugin 8.7.3.

1. Ouvrir le dossier `android/` dans Android Studio.
2. Laisser Gradle synchroniser et télécharger les dépendances officielles.
3. Brancher le téléphone Android et activer le débogage USB, ou choisir un émulateur.
4. Cliquer sur **Run** pour installer l'application, ou utiliser **Build > Build APK(s)** pour produire un APK debug.
5. Pour une diffusion, créer une clé de signature privée et générer un APK/AAB signé. Ne jamais partager la clé de signature.

L'APK n'est pas précompilé dans cette archive : l'environnement de création ne dispose pas d'Android SDK/Gradle installés. Le projet source Android est fourni pour compilation dans Android Studio.

## Important
- La clé API est protégée au repos sur l'appareil, mais elle est utilisée en mémoire lors des appels au fournisseur IA. Utiliser un verrouillage d'écran et ne pas déverrouiller/rooter le téléphone.
- Une clé Groq/OpenAI est un secret personnel : ne pas l'intégrer dans une APK destinée à d'autres personnes. Pour une distribution multi-utilisateur, utiliser un serveur intermédiaire sécurisé.
- Les appels à Groq et autres fournisseurs nécessitent Internet et peuvent être facturés selon le fournisseur et le modèle.

# LUCIA AI 0.7 — préparation Android native

Ce dossier est prêt à être enveloppé avec Capacitor 7. Le dossier Android natif et l’APK doivent être générés sur une machine équipée de Node.js, Android Studio et du SDK Android. Ils ne sont pas inclus comme APK compilé.

## Générer le projet Android

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

Dans Android Studio : choisir Build > Build Bundle(s) / APK(s) > Build APK(s). Pour distribuer l’application, créer une version signée via Build > Generate Signed Bundle / APK.

Application ID : `fr.lucia.ai` — Nom : `LUCIA AI`.

La clé API reste stockée dans le stockage web local de l’application ; cette version n’ajoute pas de coffre-fort chiffré natif. Ne pas intégrer une clé personnelle dans une APK distribuée. Préférer un serveur intermédiaire sécurisé pour un déploiement multi-utilisateur.

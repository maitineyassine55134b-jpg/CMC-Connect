# CMC Connect – génération de l'APK

## Méthode A : dans le cloud (aucune installation)
1. Crée un compte gratuit sur github.com, puis un nouveau dépôt (New repository).
2. Envoie TOUT le contenu de ce dossier dans le dépôt, y compris le dossier caché `.github`
   (glisser-déposer sur la page du dépôt → "uploading an existing file").
3. Onglet **Actions** → workflow **Build APK** (il démarre tout seul, ~5 min).
4. Quand il est vert : clique sur l'exécution → section **Artifacts** → télécharge **CMC-Connect-apk**.
5. Décompresse : tu obtiens `app-debug.apk`. Envoie-le sur ton téléphone, ouvre-le et autorise
   "Installer des applications inconnues".

## Méthode B : sur ton ordinateur (Node 18+, Java 17, Android Studio/SDK)
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
→ APK : android/app/build/outputs/apk/debug/app-debug.apk

Remarques : l'APK est signé en mode debug (installable, pas publiable sur le Play Store).
Le partage d'écran n'est pas disponible dans une application Android WebView.

# Depense

Suivi personnel des dépenses — application web autonome (`index.html`), hébergée
sur GitHub Pages : https://sudoserere.github.io/Depense/

## Fonctionnalités

- Ajout de dépenses par catégorie (Charges / Famille / Divers), montant et description modifiables après coup.
- Case à cocher « payé » par dépense + métrique « Reste à payer ».
- Tag couleur libre (vert / rouge) par dépense — clic sur le point pour faire défiler vert → rouge → aucun.
- Export / import CSV.
- Synchronisation entre appareils via un fichier `data.json` stocké dans ce dépôt GitHub.

## Synchronisation entre appareils

Les données vivent normalement dans le navigateur (localStorage). Pour les
retrouver sur un autre appareil sans tout ressaisir, l'application peut lire et
écrire un fichier `data.json` directement dans ce dépôt, via l'API GitHub.

1. Sur GitHub, va dans **Settings → Developer settings → Personal access
   tokens → Fine-grained tokens → Generate new token**.
2. Limite l'accès au dépôt **Depense** uniquement (« Only select repositories »).
3. Sous **Repository permissions**, mets **Contents : Read and write**.
4. Copie le token généré, colle-le dans la carte « Synchronisation GitHub » de
   l'application (dans la barre latérale), clique sur **Connecter**.

Le token reste uniquement dans le navigateur de cet appareil (localStorage) — à
refaire sur chaque nouvel appareil/navigateur. Une fois connecté :

- **☁ Sauvegarder en ligne** envoie l'état courant vers `data.json` sur GitHub.
- **↻ Recharger** récupère la dernière version sauvegardée sur GitHub (écrase
  les données locales non synchronisées, une confirmation est demandée).
- La case **Synchroniser automatiquement** envoie les modifications toutes
  seules quelques secondes après chaque changement.

⚠️ Comme le dépôt est utilisé pour stocker de vraies données financières, il
est recommandé de le garder **privé** (Settings → General → Danger Zone →
Change repository visibility). GitHub Pages continue de fonctionner sur un
dépôt privé.
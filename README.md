# ManhwaVerse — Lecteur Autonome

## Structure du projet

```
/
├── index.html          ← Le site (fichier unique)
├── data.json           ← Configuration des manhwas
├── manhwa/
│   └── NomDuManhwa/
│       ├── 1/
│       │   ├── 001.webp
│       │   ├── 002.webp
│       │   └── ...
│       ├── 2/
│       └── ...
└── backgrounds/
    └── NomDuManhwa.jpg  ← Couverture (optionnel)
```

## data.json — Structure

```json
{
  "manhwas": [
    {
      "name": "NomDossier",       ← Nom exact du dossier dans /manhwa/
      "title": "Titre affiché",
      "synopsis": "Description...",
      "status": "en cours",       ← "en cours" | "terminé" | "pause"
      "seasons": 2,               ← Nombre de saisons (optionnel)
      "cover": null,              ← URL custom ou null (auto-détecté)
      "chapters": {
        "1": { "title": "Prologue" },
        "10": { "title": "La révélation", "synopsis": "..." }
      }
    }
  ]
}
```

## Fonctionnalités

- **Mot de passe** : `1234` par défaut (modifiable dans ⚙️ Paramètres)
- La session est mémorisée jusqu'à la fermeture du navigateur (pas de re-saisie au rechargement)
- **Drag & drop** pour réorganiser les manhwas
- **Mode sombre/clair** (bouton 🌙)
- **Zoom** activable dans le lecteur
- **Navigation clavier** : ← → pour changer de chapitre, Échap pour fermer

## Images supportées

- `.webp`, `.jpg`, `.jpeg`, `.png`
- Numérotation non continue (ex: 001, 003, 005...)
- Tri automatique croissant
- Détection automatique sans backend

## Serveur local (requis pour fetch)

```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# VS Code
# Extension "Live Server"
```

Puis ouvrir : http://localhost:8080

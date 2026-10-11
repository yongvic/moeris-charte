# Résidence Moeris — Charte graphique 2026

Brand book interactif (une seule page HTML) de la Résidence Moeris, hôtel au bord du Lac Togo.

## Structure

```
index.html          La charte (page autonome)
images/             Images générées (54 emplacements)
assets/brand/       Logos à joindre à Gemini : logo_blanc, logo_noir, icon (SVG + PNG)
prompts.json        Les 54 prompts complets (brief commun + prompt), format, logo à joindre
```

## Images

Chaque emplacement charge automatiquement `images/<fichier>.jpg` (ou `.png`, `.webp`, `.jpeg`).
Si l'image est absente, le placeholder d'origine s'affiche. La liste exacte des noms de fichiers est dans `prompts.json` (champ `filename`).

Génération : dans Gemini, coller le `fullPrompt`, joindre le logo indiqué (`logoFile`) quand `needsLogo` vaut `true`, puis enregistrer le résultat sous le nom attendu dans `images/`.

## Mode Atelier

Le bouton « Atelier d'images » affiche les prompts, l'annexe et permet de tester une image par glisser-déposer.
Pour la version de présentation, mettre `const ATELIER_UI = false;` dans `index.html`.

## Aperçu local

```
python3 -m http.server 8000
```
puis ouvrir http://localhost:8000 (le chargement des images nécessite un serveur ou GitHub Pages).

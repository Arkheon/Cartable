# Mon Cartable

Site éducatif statique pour apprendre à la maison — mathématiques, français, anglais et découverte du monde, du CP au CM2. Zéro build, zéro framework : du HTML/CSS/JS vanilla, hébergé sur GitHub Pages.

---

## Ajouter un exercice

1. Créer un dossier dans la matière concernée, ex. `cp/maths/mon-exercice/`
2. Y déposer un `index.html` (partir de `cp/maths/cartes-seguin/index.html` comme modèle)
3. Ajouter un lien retour en haut : `<a href="../" class="back-link">← Retour</a>`
4. Dans la page parente (`cp/maths/index.html`), copier la carte existante et ajuster le `href`, le titre et la description

```html
<!-- Modèle de carte à copier dans cp/maths/index.html -->
<a href="mon-exercice/" class="nav-card"
   style="--card-color: var(--maths-color); --card-dark: var(--maths-dark)">
  Mon exercice
  <span class="nav-card-desc">Courte description</span>
</a>
```

## Ajouter une matière

1. Créer le dossier `cp/ma-matiere/` avec un `index.html` (partir de `cp/maths/index.html`)
2. Dans `cp/index.html`, remplacer la `<div class="nav-card disabled">` correspondante par un `<a>` cliquable avec la couleur de la matière

Couleurs disponibles dans `assets/css/shared.css` :
- Maths : `--maths-color` / `--maths-dark`
- Français : `--francais-color` / `--francais-dark`
- Anglais : `--anglais-color` / `--anglais-dark`
- Découverte du monde : `--monde-color` / `--monde-dark`

## Ajouter un niveau

1. Créer le dossier `ce1/` avec un `index.html` (partir de `cp/index.html`)
2. Dans `index.html` (racine), remplacer la `<div class="nav-card disabled">` du niveau par un `<a>` cliquable

## Déploiement GitHub Pages

1. Pousser le dépôt sur GitHub
2. Settings → Pages → Source : **Deploy from a branch**, branche `main`, dossier `/` (root)
3. Le site est disponible à `https://<utilisateur>.github.io/<nom-du-repo>/`

Chaque dossier contenant un `index.html` est automatiquement servi — aucune configuration supplémentaire.

## Structure

```
/
├── index.html                    # Sélecteur de niveaux
├── assets/
│   └── css/
│       └── shared.css            # Tokens de design + composants de navigation
├── cp/
│   ├── index.html                # Sélecteur de matières CP
│   └── maths/
│       ├── index.html            # Liste des exercices de maths CP
│       └── cartes-seguin/
│           └── index.html        # Exercice : Cartes Séguin
└── README.md
```

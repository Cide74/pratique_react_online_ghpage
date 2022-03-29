# Mettre en ligne une app React sur GH Pages

## Installation de la dépendance `gh-pages`

lien npm : <https://www.npmjs.com/package/gh-pages>

```bash
npm i -D gh-pages

yarn add -D gh-pages
```

## Modification du fichier `package.json`

Le fichier package.json avant modification

```json
{
  "name": "pratique_react_online_ghpage",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.3",
    "@testing-library/react": "^12.1.4",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0",
    "react-scripts": "5.0.0",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "gh-pages": "^3.2.3"
  }
}
```

### Intégration d'une `homepage`

Sur la 1er ligne, elle sera la page d'acceuil de notre site de base

```json
{
"homepage": "https://notre_pseudo_GitHub.github.io/nom_du_ripo",
}
```

Pour cette exemple cela donne :

```json
{
"homepage": "https://cide74.github.io/pratique_react_online_ghpage",
}
```

### inégration d'un script `deploy`

Cela va permettre de déployer, notre ripo sur une nouvelle branche.

```json
{
  "scripts": {
    "deploy": "gh-pages -d build"
  },
}
```

Rendu du fichier final

```json
{
  "homepage": "https://cide74.github.io/pratique_react_online_ghpage",
  "name": "pratique_react_online_ghpage",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.3",
    "@testing-library/react": "^12.1.4",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0",
    "react-scripts": "5.0.0",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "deploy": "gh-pages -d build"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "gh-pages": "^3.2.3"
  }
}
```

## Mise en ligne de l'application

### Création du build

Cela va permettre de produire notre application

Dans la console :

```bash
npm run build

yarn run build
```

Création du fichier build pour la production.

### Création de la branche de production

Dans la console :

```bash
npm run deploy

yarn run deploy
```

Après exécution de cette commande l'application est publier sur une nouvelle branche nommée `gh-pages`.

## Sur le Ripo de l'application

Dans gitHub aller dans `Settings` => `Pages`

- Si bleu => site en cous de déploiement.
- Si vert => site plublier.

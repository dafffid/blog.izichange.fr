# Guide de Déploiement - Blog Symbotis sur GitHub Pages

## Table des Matières
1. [Prérequis](#prérequis)
2. [Création du Repository GitHub](#création-du-repository-github)
3. [Upload des Fichiers](#upload-des-fichiers)
4. [Configuration GitHub Pages](#configuration-github-pages)
5. [Vérifications et Tests](#vérifications-et-tests)
6. [Troubleshooting](#troubleshooting)
7. [Maintenance et Mises à Jour](#maintenance-et-mises-à-jour)

---

## Prérequis

Avant de commencer, assurez-vous d'avoir :
- Un compte GitHub actif
- Accès aux fichiers du blog Symbotis
- Une connexion internet stable
- Un navigateur web moderne

---

## Création du Repository GitHub

### Étape 1 : Créer un nouveau repository

1. **Connectez-vous à GitHub**
   - Allez sur [github.com](https://github.com)
   - Connectez-vous avec vos identifiants

2. **Créer le repository**
   - Cliquez sur le bouton vert "New" ou l'icône "+" en haut à droite
   - Sélectionnez "New repository"

3. **Configuration du repository**
   ```
   Repository name: Symbotis-blog
   Description: Blog Symbotis - Plateforme de changement et d'innovation
   Visibility: Public (obligatoire pour GitHub Pages gratuit)
   Initialize with:
   ☑️ Add a README file
   ☐ Add .gitignore (nous l'ajouterons manuellement)
   ☐ Choose a license (optionnel)
   ```

4. **Créer le repository**
   - Cliquez sur "Create repository"

### Étape 2 : Cloner ou préparer l'upload

**Option A : Via interface web (recommandé pour débutants)**
- Restez sur la page du repository créé
- Nous utiliserons l'interface web pour l'upload

**Option B : Via Git (pour utilisateurs avancés)**
```bash
git clone https://github.com/VOTRE_USERNAME/Symbotis-blog.git
cd Symbotis-blog
```

---

## Upload des Fichiers

### Méthode 1 : Upload via Interface Web GitHub

1. **Accéder au repository**
   - Ouvrez votre repository `Symbotis-blog` sur GitHub

2. **Upload des fichiers**
   - Cliquez sur "Add file" → "Upload files"
   - Glissez-déposez tous les fichiers du blog dans la zone de drop
   - Ou cliquez "choose your files" pour sélectionner manuellement

3. **Structure des fichiers à uploader**
   ```
   Symbotis-blog/
   ├── index.html (page d'accueil)
   ├── about.html
   ├── contact.html
   ├── blog/
   │   ├── index.html
   │   └── articles/
   ├── css/
   │   ├── style.css
   │   └── responsive.css
   ├── js/
   │   └── main.js
   ├── images/
   │   ├── logo.png
   │   ├── hero-bg.jpg
   │   └── articles/
   ├── assets/
   └── README.md
   ```

4. **Commit des fichiers**
   - Scrollez vers le bas
   - Ajoutez un message de commit : "Initial upload - Symbotis blog files"
   - Sélectionnez "Commit directly to the main branch"
   - Cliquez "Commit changes"

### Méthode 2 : Upload via Git (ligne de commande)

```bash
# Copier tous les fichiers du blog dans le dossier cloné
cp -r /chemin/vers/blog/* ./

# Ajouter tous les fichiers
git add .

# Commit
git commit -m "Initial upload - Symbotis blog files"

# Push vers GitHub
git push origin main
```

---

## Configuration GitHub Pages

### Étape 1 : Activer GitHub Pages

1. **Accéder aux paramètres**
   - Dans votre repository, cliquez sur l'onglet "Settings"
   - Scrollez vers le bas jusqu'à la section "Pages"

2. **Configuration de la source**
   ```
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   ```

3. **Sauvegarder**
   - Cliquez "Save"
   - GitHub affichera l'URL de votre site : `https://VOTRE_USERNAME.github.io/Symbotis-blog`

### Étape 2 : Configuration personnalisée (optionnel)

1. **Domaine personnalisé** (si vous en avez un)
   - Dans la section Pages, ajoutez votre domaine dans "Custom domain"
   - Créez un fichier `CNAME` à la racine avec votre domaine

2. **Enforce HTTPS**
   - Cochez "Enforce HTTPS" pour la sécurité

---

## Vérifications et Tests

### Vérification 1 : Déploiement en cours

1. **Vérifier le status de déploiement**
   - Allez dans l'onglet "Actions" de votre repository
   - Vous devriez voir un workflow "pages-build-deployment" en cours ou terminé

2. **Temps d'attente**
   - Le premier déploiement peut prendre 5-10 minutes
   - Les mises à jour suivantes sont plus rapides (1-3 minutes)

### Vérification 2 : Accès au site

1. **Tester l'URL principale**
   - Ouvrez `https://VOTRE_USERNAME.github.io/Symbotis-blog`
   - Vérifiez que la page d'accueil se charge correctement

2. **Tester la navigation**
   - Cliquez sur tous les liens de navigation
   - Vérifiez que les pages About, Contact, Blog fonctionnent

3. **Tester les ressources**
   - Ouvrez les outils de développement (F12)
   - Vérifiez qu'il n'y a pas d'erreurs 404 dans la console
   - Vérifiez que les images, CSS et JS se chargent

### Vérification 3 : Responsive et compatibilité

1. **Test mobile**
   - Utilisez les outils de développement pour simuler différents appareils
   - Testez sur votre téléphone

2. **Test navigateurs**
   - Testez sur Chrome, Firefox, Safari, Edge
   - Vérifiez la compatibilité

---

## Troubleshooting

### Problème 1 : Site inaccessible (404)

**Symptômes :** L'URL retourne une erreur 404

**Solutions :**
1. Vérifiez que GitHub Pages est activé dans Settings → Pages
2. Attendez 10-15 minutes après l'activation
3. Vérifiez que le fichier `index.html` est à la racine du repository
4. Vérifiez que la branche source est correcte (main)

### Problème 2 : CSS/JS ne se chargent pas

**Symptômes :** Le site apparaît sans style ou fonctionnalités JavaScript

**Solutions :**
1. Vérifiez les chemins dans les fichiers HTML :
   ```html
   <!-- Correct -->
   <link rel="stylesheet" href="css/style.css">
   <script src="js/main.js"></script>

   <!-- Incorrect -->
   <link rel="stylesheet" href="/css/style.css">
   <script src="/js/main.js"></script>
   ```

2. Utilisez des chemins relatifs, pas absolus
3. Vérifiez que les fichiers CSS/JS sont bien uploadés dans les bons dossiers

### Problème 3 : Images manquantes

**Symptômes :** Images ne s'affichent pas (icônes cassées)

**Solutions :**
1. Vérifiez les chemins des images :
   ```html
   <!-- Correct -->
   <img src="images/logo.png" alt="Logo">

   <!-- Incorrect -->
   <img src="/images/logo.png" alt="Logo">
   ```

2. Vérifiez que les images sont dans le bon dossier
3. Vérifiez les noms de fichiers (sensibles à la casse)

### Problème 4 : Déploiement échoue

**Symptômes :** Le workflow GitHub Actions échoue

**Solutions :**
1. Allez dans Actions → cliquez sur le workflow échoué
2. Lisez les logs d'erreur
3. Vérifiez qu'il n'y a pas de fichiers corrompus
4. Vérifiez que tous les fichiers sont valides (HTML, CSS, JS)

### Problème 5 : Changements non visibles

**Symptômes :** Les modifications ne s'affichent pas sur le site

**Solutions :**
1. Attendez 1-3 minutes après le commit
2. Forcez le rechargement (Ctrl+F5 ou Cmd+Shift+R)
3. Videz le cache du navigateur
4. Vérifiez dans Actions que le déploiement s'est bien terminé

### Problème 6 : Domaine personnalisé ne fonctionne pas

**Symptômes :** Le domaine personnalisé retourne une erreur

**Solutions :**
1. Vérifiez le fichier CNAME à la racine du repository
2. Configurez les DNS chez votre registraire :
   ```
   Type: CNAME
   Name: www
   Value: VOTRE_USERNAME.github.io

   Type: A
   Name: @
   Value: 185.199.108.153
          185.199.109.153
          185.199.110.153
          185.199.111.153
   ```
3. Attendez la propagation DNS (jusqu'à 24h)

---

## Maintenance et Mises à Jour

### Mise à jour du contenu

1. **Via interface web :**
   - Naviguez vers le fichier à modifier
   - Cliquez sur l'icône crayon (Edit)
   - Faites vos modifications
   - Commit avec un message descriptif

2. **Via Git :**
   ```bash
   git pull origin main
   # Modifiez vos fichiers
   git add .
   git commit -m "Description des modifications"
   git push origin main
   ```

### Ajout de nouvelles pages

1. Créez le fichier HTML dans le bon dossier
2. Mettez à jour la navigation dans les autres pages
3. Testez localement si possible
4. Commit et push

### Suivi des performances

1. **Google Analytics** (optionnel)
   - Ajoutez le code de tracking dans toutes les pages

2. **Google Search Console**
   - Soumettez votre sitemap
   - Surveillez l'indexation

### Sauvegardes

1. **Sauvegarde automatique :** GitHub conserve tout l'historique
2. **Sauvegarde locale :** Clonez régulièrement le repository
3. **Export :** Utilisez les outils GitHub pour exporter si nécessaire

---

## Ressources Utiles

- [Documentation GitHub Pages](https://docs.github.com/en/pages)
- [Guide Markdown GitHub](https://guides.github.com/features/mastering-markdown/)
- [Générateur de .gitignore](https://gitignore.io/)
- [Validateur HTML](https://validator.w3.org/)
- [Validateur CSS](https://jigsaw.w3.org/css-validator/)

---

## Support

En cas de problème non résolu :

1. Consultez les [GitHub Community Discussions](https://github.com/community)
2. Vérifiez le [GitHub Status](https://status.github.com/)
3. Contactez le support GitHub si nécessaire

---

*Guide créé pour le déploiement du blog Symbotis*
*Dernière mise à jour : 2025-01-18*

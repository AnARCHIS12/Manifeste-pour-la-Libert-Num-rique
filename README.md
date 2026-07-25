# 1984 - Manifeste pour la Liberté Numérique

Site statique militant contre la surveillance de masse et pour la protection des libertés individuelles.

## Déploiement sur Netlify

### Option 1: Drag & Drop (le plus simple)

1. Allez sur [app.netlify.com](https://app.netlify.com)
2. Connectez-vous ou créez un compte
3. Glissez-déposez le dossier du projet dans la zone "Drag and drop your site output folder here"

### Option 2: Via Git

1. Poussez votre code sur GitHub/GitLab/Bitbucket
2. Allez sur [app.netlify.com](https://app.netlify.com)
3. Cliquez sur "Add new site" → "Import an existing project"
4. Sélectionnez votre dépôt Git
5. Netlify détectera automatiquement la configuration via `netlify.toml`

### Option 3: Netlify CLI

```bash
# Installer Netlify CLI
npm install -g netlify-cli

# Se connecter
netlify login

# Déployer
netlify deploy --prod
```

## Gestion des articles avec Decap CMS (Netlify Identity)

Le site utilise Decap CMS avec Netlify Identity pour gérer les articles simplement.

### Configuration requise

1. **Créez un dépôt GitHub** pour votre projet
2. **Connectez le dépôt à Netlify** lors du déploiement (Option 2: Via Git)
3. **Activez Netlify Identity** :
   - Allez sur votre dashboard Netlify
   - Cliquez sur "Site settings" → "Identity"
   - Cliquez sur "Enable Identity"
4. **Activez Git Gateway** :
   - Dans "Identity", cliquez sur "Git Gateway"
   - Cliquez sur "Enable Git Gateway"

### Utilisation

1. Déployez votre site sur Netlify
2. Allez sur `https://votre-site.netlify.app/admin/`
3. Cliquez sur "Login with Netlify Identity"
4. Créez un compte ou connectez-vous
5. Créez et modifiez des articles via l'interface
6. Les articles sont sauvegardés automatiquement dans le dossier `_articles` de votre repo GitHub
7. Netlify rebuild automatiquement le site avec les nouveaux articles

**Avantage** : Pas besoin de configurer OAuth GitHub manuellement, Netlify gère tout automatiquement.

## Fichiers

- `preview.html` - Page principale du site
- `admin/config.yml` - Configuration Decap CMS
- `admin/index.html` - Interface d'administration Decap CMS
- `_articles/` - Dossier contenant les fichiers markdown des articles
- `netlify.toml` - Configuration Netlify

## Sécurité

Le `netlify.toml` inclut des headers de sécurité basiques. Ajustez selon vos besoins.

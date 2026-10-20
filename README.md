# Protocole

Tracker d'habitudes personnel et gamifié : XP, niveaux, points de vie, coups critiques, succès, boutique de thèmes et tableau de bord d'analyse. L'app fonctionne entièrement dans le navigateur, hors ligne, sans compte ni serveur. Les données restent sur ton téléphone.

## Contenu du dépôt

| Fichier | Rôle |
| --- | --- |
| `index.html` | L'application complète (interface, logique, styles) |
| `manifest.webmanifest` | Permet l'installation sur l'écran d'accueil (nom, icônes, couleurs) |
| `sw.js` | Service worker : l'app s'ouvre même sans connexion |
| `icons/` | Icônes de l'app pour iPhone, Android et navigateur |
| `.nojekyll` | Indique à GitHub Pages de servir les fichiers tels quels |

## Mise en ligne avec GitHub Pages

1. Sur GitHub, crée un nouveau dépôt, par exemple `protocole`. Il doit être **public** si tu as un compte gratuit (c'est une condition de GitHub Pages). Le code sera visible, mais tes données ne quittent jamais ton téléphone.
2. Dans le dépôt, clique sur **Add file > Upload files**, glisse tout le contenu du dossier (y compris le dossier `icons` et le fichier `.nojekyll`), puis **Commit changes**.
   Si `.nojekyll` n'apparaît pas dans ton explorateur de fichiers (fichier caché), ce n'est pas bloquant : l'app fonctionne sans.
3. Va dans **Settings > Pages**. Dans **Build and deployment**, choisis **Source : Deploy from a branch**, puis la branche **main** et le dossier **/ (root)**. Clique sur **Save**.
4. Attends une à deux minutes. L'adresse de ton app s'affiche en haut de la page, sous la forme :
   `https://ton-pseudo.github.io/protocole/`

## Installation sur le téléphone

**iPhone** : ouvre l'adresse dans **Safari**, touche le bouton de partage, puis **Sur l'écran d'accueil**.

**Android** : ouvre l'adresse dans **Chrome**, touche le menu ⋮, puis **Installer l'application** (ou **Ajouter à l'écran d'accueil**).

Utilise ensuite toujours l'icône de l'écran d'accueil. Sur iPhone, l'app installée et Safari ont chacun leur propre stockage : des habitudes saisies dans Safari n'apparaîtront pas dans l'app installée, et inversement.

## Récupérer tes données depuis la version Claude

1. Dans la version publiée sur Claude, va dans **Réglages > Sauvegarde > Exporter**.
2. Dans l'app installée, va dans **Réglages > Sauvegarde > Importer**, puis colle le texte ou choisis le fichier exporté.

## Sauvegardes

Les données sont stockées dans le navigateur du téléphone. Elles sont effacées si tu supprimes les données du site, désinstalles l'app ou changes de téléphone. Sur iPhone, Safari peut aussi effacer les données d'un site après plusieurs semaines sans visite. Si tu ouvres l'app tous les jours, ce n'est pas un problème.

Prends l'habitude d'exporter une sauvegarde chaque semaine (**Réglages > Sauvegarde > Exporter**) et de la ranger dans tes fichiers, iCloud ou Google Drive.

## Historique

- **v2** : dispenses encadrées, versions minimales, ancrages, moments de la journée, bonus de retour, paliers de série, objectif hebdomadaire, nouveau départ, bilan d'automatisme, récompense des écarts évités, page « La science derrière l'app ».
- **v1** : première version.

## Mettre à jour l'app

1. Remplace `index.html` dans le dépôt par la nouvelle version.
2. Ouvre `sw.js` et augmente la version : `protocole-v1` devient `protocole-v2`, et ainsi de suite.
3. Sur le téléphone, ouvre l'app, ferme-la complètement, puis rouvre-la. La nouvelle version se charge et tes données sont conservées.

## Règles du jeu

- Une validation rapporte 10 XP par niveau de difficulté, multipliés par ta série (jusqu'à ×1,9 à 30 jours), et 3 crédits par niveau de difficulté.
- 8 % de chances de coup critique (×3) et 1 % de jackpot (×10) à chaque validation.
- Jour parfait : +50 XP, +10 crédits et 4 PV réparés à la clôture.
- La journée se clôture à 4 h du matin. Chaque protocole oublié coûte 6 PV et 18 XP par niveau de difficulté, avec un plafond de 50 PV par journée.
- Craquer sur un protocole à éviter coûte immédiatement 8 PV et 24 XP par niveau de difficulté.
- Objectif hebdomadaire : bonus de 30 XP par niveau de difficulté s'il est atteint, 5 PV perdus par séance manquante le dimanche soir.
- À 0 PV, la coque est détruite : tu perds un niveau et la moitié de tes crédits.
- Un bouclier en stock absorbe automatiquement une journée de dégâts.
- Écart évité : chaque jour tenu sur un protocole à éviter rapporte 5 XP par niveau de difficulté à la clôture.
- Retour : après un oubli ou une dispense, la validation suivante rapporte le double.
- Paliers de série (3, 7, 14, 21, 30, 50, 66, 100 jours et plus) : bonus d'XP.

## Dispenses

Pour passer exceptionnellement un protocole, touche son nom puis **Dispenser aujourd'hui**. L'option est volontairement un peu cachée : un léger frein limite l'usage par réflexe.

- 2 dispenses par semaine au maximum, renouvelées le lundi.
- Une seule par protocole et par semaine, et jamais deux fois de suite sur le même protocole.
- Impossible pendant les 7 premiers jours d'un protocole, juste après l'avoir oublié, ou pour un protocole à éviter.
- Coût croissant : ◈ 25 pour la première de la semaine, ◈ 50 pour la seconde.
- Raison et plan de rattrapage (« quand et où ») obligatoires. Le plan s'affiche le jour suivant avec le bonus de retour ×2.
- Avant de dispenser, l'app propose la **version minimale** du protocole (si tu en as défini une) : la série continue, à 50 % de l'XP.

## Autres outils

- **Ancrage** : « Après mon café, je médite ». Le protocole s'affiche avec son déclencheur.
- **Moments de la journée** : la liste du jour se range en Matin, Après-midi, Soir.
- **Objectif de la semaine** : ta réussite de la semaine précédente plus 5 points, affiché sous le cockpit.
- **Nouveau départ** : un message le lundi et le premier du mois.
- **Bilan d'automatisme** : une fois par semaine, tu notes de 1 à 7 à quel point chaque protocole se fait sans y penser. Au-delà de 6/7 avec une bonne régularité, le protocole est marqué « Ancré ».

La liste complète des études utilisées est dans l'app : **Réglages > La science derrière l'app**.

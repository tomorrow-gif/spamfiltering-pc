# Spam filtering (filtrage des informations indésirables)

> 🌍 [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [Português](README.pt.md) · [Русский](README.ru.md)

Gardez votre navigation propre. **Spam filtering** supprime automatiquement les spams, pop-ups, bannières, traceurs et autres contenus indésirables des pages que vous visitez — tout s'exécute localement et en toute confidentialité sur votre appareil.

## Points forts

- Bloque les spams et contenus indésirables : pop-ups, bannières, traceurs, scripts d'analyse
- Vos propres règles en texte brut — importez, modifiez et exportez à tout moment
- Liste blanche des sites de confiance en un clic
- Statistiques de blocage (aujourd'hui / total)
- 10 langues prises en charge
- 100 % local et privé — aucun compte, aucun cloud, aucune collecte de données
- Fonctionne au niveau système — aucune extension de navigateur requise

## Configuration requise

- Windows 10 / 11

## Pour commencer

1. Téléchargez le dernier installeur depuis la page Releases.
2. Installez et lancez l'application.
3. Activez **Prendre en charge le proxy système** dans les paramètres.
4. Naviguez normalement — les contenus indésirables sont filtrés automatiquement.

## Modifier les règles

Les règles sont stockées en texte brut, une règle par ligne. Ajoutez des règles dans la page **Règles** de l'application ou importez un fichier de règles.

### Formats de règles

| Exemple | Signification |
| --- | --- |
| `\|\|example.com^` | Bloquer un domaine et tous ses sous-domaines |
| `\|\|example.com/path/page^` | Bloquer une adresse spécifique (domaine + chemin) |
| `example.com` | Bloquer toute adresse contenant ce texte |
| `@@\|\|good.example.com^` | Exception — toujours autoriser ce domaine |
| `0.0.0.0 ad.example.com` | Entrée au format hosts |
| `! commentaire` / `# commentaire` | Lignes de commentaire — les lignes commençant par ces caractères sont ignorées |

### Conseils

- `||` ancre la règle au début du domaine ; `^` signifie « fin de domaine ou de chemin » (un séparateur).
- Commencez simple : `||domaine^` couvre la plupart des cas. Ajoutez des règles de chemin uniquement si nécessaire, ex. `||www.example.com/ads/banner^`.
- Après l'enregistrement d'une règle, vérifiez les statistiques de blocage pour confirmer qu'elle fonctionne.

### À propos de HTTPS

Par défaut, les requêtes HTTPS sont comparées par **nom de domaine uniquement** (l'adresse complète est chiffrée et invisible). Pour comparer par **adresse complète incluant le chemin**, activez **Déchiffrement HTTPS (MITM)** dans les paramètres, installez le certificat racine lorsque demandé (une seule fois), puis redémarrez votre navigateur. Ensuite, les règles de chemin comme `||www.example.com/ads/banner^` s'appliquent aussi aux sites HTTPS.

## Comment ça marche (en bref)

- L'application exécute un proxy local et peut prendre en charge le proxy système, de sorte que le trafic du navigateur y transite.
- Chaque requête est vérifiée contre vos règles : les correspondances sont bloquées, tout le reste est transmis tel quel.
- Tout le filtrage se fait sur votre appareil — aucune donnée n'est téléchargée.

## Dépannage

**Impossible d'accéder à Internet ?** La cause la plus probable : l'application a été fermée de manière inattendue et a laissé le proxy système pointant vers un port invalide.

- **Solution 1 — redémarrez l'application.** Elle détecte et nettoie automatiquement les réglages de proxy résiduels au démarrage.
- **Solution 2 — désactivez le proxy manuellement.** Paramètres Windows → Réseau et Internet → Proxy → désactivez « Utiliser un serveur proxy ».
- Normalement, la fermeture de l'application (icône de la barre d'état → Quitter) restaure automatiquement votre proxy. Des résidus n'apparaissent qu'après des fermetures anormales (plantage, arrêt forcé, coupure de courant).

## Confidentialité

Spam filtering est un outil local. Tout le filtrage s'effectue sur votre appareil — vos données de navigation ne quittent jamais votre ordinateur.

## Soutenir ce projet

Si Spam filtering vous aide, pensez à soutenir le développement futur :

![Donate](donate.jpg)

## Licence

Tous droits réservés. Ce logiciel n'est **pas open source**. La redistribution et la modification ne sont pas autorisées sans autorisation écrite explicite.

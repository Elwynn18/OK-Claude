# OK Claude

Des aides toutes prêtes pour Claude, pensées pour les gens que l'IA n'intéresse pas.
Démarches, papiers, quotidien : on s'en occupe ensemble, un pas à la fois.

Pas besoin de savoir « parler à une IA ». Une fois l'aide installée, il suffit d'écrire normalement à Claude, par exemple :

> « J'ai reçu un courrier des impôts, je sais pas quoi faire »

Claude s'occupe du reste.

---

## Les aides disponibles

### 📄 Démarche pas à pas

Pour toutes les démarches administratives en France qui font peur ou qu'on repousse :
- courrier des impôts, de la CAF ou de la CPAM ;
- carte d'identité, préfecture ;
- relance, formulaire.

**Ce que fait Claude :**
- Il fait lui-même tout ce qu'il peut : il lit le courrier, rédige les réponses, prépare les papiers.
- Il cherche la marche à suivre sur les sites officiels.
- Il vous guide **une seule étape à la fois**, en quelques mots.
- Il ne porte aucun jugement et n'emploie aucun jargon.
- S'il y a un imprévu (mot de passe oublié, site en panne…), il le règle avec vous, puis reprend où vous en étiez.

**Exemple :**

> **Étape 2/4** · Connectez-vous sur caf.fr
> 👉 Cliquez « Mon Compte ».
> Répondez « ok » ou « bloqué ».

---

## Installer une aide (5 minutes, une seule fois)

### Sur claude.ai (site ou application)

1. **Activez une option.** Allez dans **Paramètres → Capacités** et activez « Exécution de code et création de fichiers » (son nom peut être « Créer et modifier des fichiers »).
2. **Téléchargez le fichier de l'aide** : [demarche-pas-a-pas.zip](https://github.com/Elwynn18/OK-Claude/raw/main/telecharger/demarche-pas-a-pas.zip). Ne le décompressez pas.
3. **Ouvrez l'écran des skills.** Allez dans **Personnaliser → Skills**, cliquez sur **+**, puis **Créer un skill** et **Importer un skill**.
4. **Importez le fichier.** Choisissez le fichier téléchargé.

C'est fini. Vous pouvez parler à Claude normalement.

Le nom des menus peut varier légèrement selon votre version de l'application. Les étapes officielles sont sur [l'aide de Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

**Sur un compte d'entreprise ou d'organisation (Team, Enterprise)**, c'est l'administrateur qui doit autoriser cette option.

### Avec Claude Code

```
claude plugin marketplace add Elwynn18/OK-Claude
claude plugin install demarche-pas-a-pas@ok-claude
```

---

## Vous installez pour un proche ?

C'est souvent comme ça que ça se passe, et c'est très bien.
1. Installez l'aide sur son compte.
2. Montrez-lui qu'il suffit d'écrire ou de dicter sa question, ou d'envoyer la photo du courrier.

---

## Bon à savoir

- **Claude ne connaît jamais vos mots de passe.** Vous vous connectez toujours vous-même.
- **Rien n'est envoyé ni payé sans votre accord.**
- **Claude peut se tromper.** Il vérifie sur les sites officiels, mais en cas de doute important, une aide humaine existe, par exemple les espaces France Services, gratuits.

---

## Contribuer

Une idée d'aide, un bug, une formulation à améliorer ? Ouvrez une *issue* sur GitHub.

Chaque aide se trouve dans `plugins/<nom>/skills/<nom>/` :
- son `SKILL.md` ;
- ses tests dans `evals/`.

---

*Projet indépendant, non affilié à Anthropic. Claude est une marque d'Anthropic.*

Licence [MIT](LICENSE).

# Banque de questions

Questions prêtes à passer dans l'outil de questions à choix. Chaque bloc donne :
- l'**en-tête** : l'étiquette courte affichée par l'outil (12 caractères au plus) ;
- la **question** ;
- les **réponses** : le libellé, puis une courte précision après le tiret ;
- **plusieurs choix** quand la personne peut cocher plusieurs réponses ;
- **sert à** : ce que la réponse permet de vérifier. Ne pas l'afficher à la personne.

## Sommaire

- [Règles de l'outil](#règles-de-loutil)
- [Série 1 : le socle](#série-1--le-socle)
- [Série 2 : selon les réponses](#série-2--selon-les-réponses)
- [Série 3 : seulement si utile](#série-3--seulement-si-utile)
- [Choisir et continuer](#choisir-et-continuer)
- [Sans outil de questions](#sans-outil-de-questions)

## Règles de l'outil

- 1 à 4 questions par appel, 2 à 4 réponses par question (limites d'AskUserQuestion dans Claude Code).
- Si l'outil ajoute de lui-même un choix libre (« Autre »), ne pas l'ajouter une seconde fois.
- Si l'outil exige une précision pour chaque réponse, en écrire une très courte (3 à 6 mots) quand la banque n'en donne pas.
- Ne poser que les questions dont la réponse change le résultat. Sauter toute question dont la réponse est déjà connue.
- Les seuils indiqués dans « sert à » sont des repères : les vérifier au moment de la recherche.

## Série 1 : le socle

### Âge

- **En-tête** : `Âge`
- **Question** : Quel âge avez-vous ?
- **Réponses** :
  - Moins de 25 ans
  - 25 à 29 ans
  - 30 à 64 ans
  - 65 ans ou plus
- **Sert à** : aides pour les jeunes (souvent jusqu'à 25 ou 30 ans), RSA (en principe à partir de 25 ans), minimum vieillesse (en principe à partir de 65 ans).

### Foyer

- **En-tête** : `Foyer`
- **Question** : Avec qui vivez-vous ?
- **Réponses** :
  - Seul(e)
  - En couple — marié, pacsé ou non
  - Seul(e) avec enfant(s)
  - En couple avec enfant(s)
- **Sert à** : composition du foyer, qui entre dans le calcul de presque toutes les aides ; parent seul, qui ouvre des aides spécifiques.

### Logement

- **En-tête** : `Logement`
- **Question** : Pour votre logement, vous êtes… ?
- **Réponses** :
  - Locataire — HLM ou privé
  - Propriétaire — avec ou sans crédit
  - Hébergé(e) — chez de la famille ou des amis
  - Sans logement stable — foyer, hôtel, rue, voiture
- **Sert à** : aides au logement, aides aux travaux, hébergement. « Sans logement stable » : voir la section Urgence du SKILL.md.

### Travail

- **En-tête** : `Travail`
- **Question** : Que faites-vous en ce moment ?
- **Plusieurs choix** : oui (par exemple, étudiant qui travaille).
- **Réponses** :
  - En emploi — salarié, fonctionnaire ou indépendant
  - Sans emploi — avec ou sans chômage
  - En études ou en formation — apprentissage compris
  - À la retraite
- **Sert à** : choisir les questions de la série 2.

## Série 2 : selon les réponses

Ordre de priorité :
1. **Revenus**, presque toujours.
2. **Aides déjà reçues**.
3. **Le détail qui pèse le plus** : enfants, emploi, chômage, études, autonomie ou santé.

### Revenus

- **En-tête** : `Revenus`
- **Question** : Combien entre chaque mois dans votre foyer, à peu près ? Salaires, allocations, pensions : tout compris.
- **Réponses** :
  - Moins de 1 000 €
  - 1 000 à 2 000 €
  - 2 000 à 3 000 €
  - Plus de 3 000 €
- **Sert à** : presque toutes les aides sous conditions de ressources. Si le résultat dépend d'un seuil proche, affiner en série 3 avec des tranches plus fines autour de ce seuil. Si la personne ne répond pas, présenter les aides sous conditions de ressources comme « à vérifier ».

### Aides déjà reçues

- **En-tête** : `Déjà reçu`
- **Question** : Vous recevez déjà une de ces aides ?
- **Plusieurs choix** : oui.
- **Réponses** :
  - Aucune
  - Aide au logement — APL, ALS ou ALF
  - Prime d'activité ou RSA
  - Allocations familiales — ou autre aide de la CAF
- **Sert à** : ne pas proposer une aide déjà reçue ; repérer les droits qui en ouvrent d'autres.

### Enfants

À poser si le foyer compte des enfants et que leur nombre n'est pas connu.

- **En-tête** : `Enfants`
- **Question** : Combien d'enfants à charge ?
- **Réponses** :
  - 1 enfant
  - 2 enfants
  - 3 enfants ou plus
- **Sert à** : allocations familiales (en principe dès 2 enfants), aides pour familles nombreuses.

### Âges des enfants

- **En-tête** : `Âges enfants`
- **Question** : Quel âge ont vos enfants ?
- **Plusieurs choix** : oui.
- **Réponses** :
  - Moins de 3 ans
  - 3 à 5 ans
  - 6 à 17 ans
  - 18 ans ou plus
- **Sert à** : aides à la petite enfance et à la garde, allocation de rentrée scolaire, aides qui s'arrêtent selon l'âge.

### Emploi

À poser si la personne est en emploi.

- **En-tête** : `Emploi`
- **Question** : Quel type d'emploi ?
- **Réponses** :
  - Salarié(e) du privé — CDI, CDD ou intérim
  - Agent public — fonctionnaire ou contractuel
  - Indépendant(e) — micro-entrepreneur, artisan, commerçant
  - Monde agricole — exploitant ou salarié
- **Sert à** : aides de l'employeur et d'Action Logement (salariés du privé), action sociale de la fonction publique, MSA plutôt que CAF pour le monde agricole, aides aux indépendants.

### Chômage

À poser si la personne est sans emploi.

- **En-tête** : `Chômage`
- **Question** : Côté France Travail, vous êtes… ?
- **Réponses** :
  - Inscrit(e), avec allocation
  - Inscrit(e), sans allocation
  - Pas inscrit(e)
  - Je crée mon entreprise
- **Sert à** : allocation chômage, RSA, aides à la reprise d'emploi (permis, mobilité, garde d'enfant), aides à la création d'entreprise.

### Études

À poser si la personne est en études ou en formation.

- **En-tête** : `Études`
- **Question** : Vous êtes… ?
- **Réponses** :
  - Lycéen(ne)
  - Étudiant(e) boursier(e)
  - Étudiant(e) non boursier(e)
  - Apprenti(e) ou alternant(e)
- **Sert à** : bourses et aides du CROUS, aides aux apprentis, aides au logement pour les jeunes.

### Autonomie

À poser si la personne a 65 ans ou plus, est à la retraite, ou s'occupe d'un proche.

- **En-tête** : `Autonomie`
- **Question** : Au quotidien, avez-vous besoin d'aide ?
- **Réponses** :
  - Non, je me débrouille
  - Un peu — courses, ménage
  - Beaucoup — toilette, repas, déplacements
  - Pour un proche — pas pour moi
- **Sert à** : aide à domicile, allocation personnalisée d'autonomie (en principe à partir de 60 ans), aides aux proches aidants.

### Santé

- **En-tête** : `Santé`
- **Question** : Une maladie longue ou un handicap dans le foyer ?
- **Réponses** :
  - Non
  - Oui, déjà reconnu — MDPH, invalidité, longue maladie
  - Oui, sans démarche faite
  - Je préfère ne pas dire
- **Sert à** : aides de la MDPH, allocation aux adultes handicapés, aide pour enfant handicapé, pension d'invalidité, aides aux aidants.

## Série 3 : seulement si utile

### Changement récent

À poser si la situation familiale reste floue.

- **En-tête** : `Changement`
- **Question** : Un changement récent ou à venir ?
- **Plusieurs choix** : oui.
- **Réponses** :
  - Naissance — ou bébé attendu
  - Séparation ou deuil
  - Déménagement
  - Aucun de ces cas
- **Sert à** : aides liées aux événements de vie (naissance, parent seul, déménagement).

### Loyer

À poser si la personne est locataire et que l'aide au logement est en jeu.

- **En-tête** : `Loyer`
- **Question** : Votre loyer par mois, charges comprises ?
- **Réponses** :
  - Moins de 400 €
  - 400 à 700 €
  - 700 à 1 000 €
  - Plus de 1 000 €
- **Sert à** : estimer l'aide au logement.

### Travaux

À poser si la personne est propriétaire.

- **En-tête** : `Travaux`
- **Question** : Des travaux prévus dans le logement ?
- **Réponses** :
  - Oui, pour l'énergie — isolation, chauffage, fenêtres
  - Oui, pour l'adapter — âge ou handicap
  - Non
- **Sert à** : aides à la rénovation énergétique, aides à l'adaptation du logement.

### Aides locales

À poser quand les aides de la commune ou du département peuvent compter : logement, énergie, transport, personnes âgées, urgence. Seulement si l'outil offre un champ libre, et si la ville n'est pas déjà connue.

- **En-tête** : `Code postal`
- **Question** : Pour chercher aussi les aides de votre ville, écrivez votre code postal dans « Autre ».
- **Réponses** :
  - Passer — on garde les aides nationales
  - J'habite en outre-mer — les règles diffèrent parfois
- **Sert à** : aides de la mairie (CCAS), du département et de la région ; règles propres à l'outre-mer.

## Choisir et continuer

### Choisir l'aide

- **En-tête** : `Choix`
- **Question** : Par laquelle on commence ?
- **Réponses** :
  - [Aide la plus utile] (recommandé) — ce qu'elle apporte, en 5 mots
  - [Deuxième aide] — ce qu'elle apporte
  - [Troisième aide] — ce qu'elle apporte
  - Plus tard — je garde la liste

### Continuer après une demande

- **En-tête** : `Suite`
- **Question** : Il reste [aide] et [aide]. On continue ?
- **Réponses** :
  - Oui, [aide suivante]
  - Plus tard

### Aucune aide trouvée

- **En-tête** : `Rendez-vous`
- **Question** : Voulez-vous que je trouve un lieu près de chez vous pour faire un bilan complet avec quelqu'un ?
- **Réponses** :
  - Oui — je cherche le plus proche
  - Non merci

## Sans outil de questions

Dernier recours, seulement si la session n'a aucun outil de questions. Mêmes questions, mêmes réponses, une question par message :

> Quel âge avez-vous ?
> 1. Moins de 25 ans
> 2. 25 à 29 ans
> 3. 30 à 64 ans
> 4. 65 ans ou plus
>
> Répondez par le numéro.

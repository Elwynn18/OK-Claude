# Banque de questions

Questions prêtes à passer dans l'outil de questions à choix. Chaque bloc donne :
- l'**en-tête** : l'étiquette courte affichée par l'outil (12 caractères au plus) ;
- la **question** ;
- les **réponses** : le libellé, puis, après le tiret, la précision affichée sous la réponse ;
- **plusieurs choix** quand la personne peut cocher plusieurs réponses ;
- **sert à** : ce que la réponse permet de vérifier. Ne pas l'afficher à la personne.

## Sommaire

- [Règles](#règles)
- [Série 1 : le socle](#série-1--le-socle)
- [Détails selon la situation](#détails-selon-la-situation)
- [Série 2 : revenus et aides déjà reçues](#série-2--revenus-et-aides-déjà-reçues)
- [Seulement si utile](#seulement-si-utile)
- [Choisir et continuer](#choisir-et-continuer)
- [Sans outil de questions](#sans-outil-de-questions)

## Règles

**Limites de l'outil**
- 1 à 4 questions par appel, 2 à 4 réponses par question (limites d'AskUserQuestion dans Claude Code).
- Si l'outil ajoute de lui-même un choix libre (« Autre »), ne pas l'ajouter une seconde fois.
- Quand la banque ne donne pas de précision, la réponse se suffit : laisser la précision vide si l'outil l'accepte, sinon la reprendre en deux ou trois mots, sans rien inventer.

**Choisir les questions**
- Ne poser que les questions dont la réponse change le résultat. Sauter toute question dont la réponse est déjà connue, même en partie : si la personne a dit « je suis étudiant », ne pas reposer « Vous êtes… ? » mais passer à la question suivante utile (« Bourse »).
- Quand une variante existe pour le profil (jeunes, parents, étudiants, retraite), prendre la variante.
- Les seuils indiqués dans « sert à » sont des repères : les vérifier au moment de la recherche.

**Écrire pour la personne**
- **Accords** : si le genre est connu, accorder (« Seule avec enfants », « Inscrite »). Sinon, garder la forme de la banque.
- **Tu ou vous** : tutoyer seulement si la personne tutoie. Dans ce cas, mettre aussi les questions au tu.
- **Réponses à plusieurs choix** : si « Aucune » est cochée avec autre chose, ignorer « Aucune ».

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
- **Variante jeunes** (moins de 30 ans, sans enfant connu) :
  - Seul(e)
  - En colocation — avec d'autres personnes, chacun son bail ou un bail commun
  - En couple
  - Chez mes parents
- **Sert à** : composition du foyer, qui entre dans le calcul de presque toutes les aides ; parent seul, qui ouvre des aides spécifiques ; colocation, qui change le calcul de l'aide au logement.

### Logement

- **En-tête** : `Logement`
- **Question** : Pour votre logement, vous êtes… ?
- **Réponses** :
  - Locataire — HLM, privé ou résidence étudiante
  - Propriétaire — avec ou sans crédit
  - Hébergé(e) — chez la famille ou des amis, sans payer de loyer
  - Sans logement stable — foyer, hôtel, rue, voiture
- **Sert à** : aides au logement, aides aux travaux, hébergement. « Sans logement stable » : voir la section Urgence du SKILL.md.

### Travail

- **En-tête** : `Travail`
- **Question** : Que faites-vous en ce moment ?
- **Plusieurs choix** : oui (par exemple, étudiant qui travaille).
- **Réponses** :
  - En emploi — salarié, fonctionnaire ou à votre compte
  - Sans emploi — avec ou sans chômage
  - En études ou en formation — apprentissage compris
  - À la retraite
- **Sert à** : choisir les détails à demander ensuite.

## Détails selon la situation

Ces questions complètent le premier appel quand une partie du socle est déjà connue, ou forment la série 2 avec les revenus. Prendre d'abord celles qui touchent ce que la personne a évoqué.

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
  - Salarié(e) du privé — CDI, CDD, intérim, temps partiel
  - Agent public — fonctionnaire ou contractuel
  - À votre compte — micro-entreprise, artisan, commerçant, libéral
  - Monde agricole — exploitant ou salarié
- **Sert à** : aides de l'employeur et d'Action Logement (salariés du privé), action sociale de la fonction publique, MSA plutôt que CAF pour le monde agricole, aides aux indépendants.

### Chômage

À poser si la personne est sans emploi.

- **En-tête** : `Chômage`
- **Question** : Côté France Travail (ex-Pôle emploi), où en êtes-vous ?
- **Réponses** :
  - Inscrit(e), avec allocation — vous recevez déjà de l'argent
  - Inscrit(e), en attente — pas encore de réponse
  - Inscrit(e), sans droit — allocation refusée ou terminée
  - Pas encore inscrit(e)
- **Sert à** : allocation chômage, RSA, aides à la reprise d'emploi (permis, mobilité, garde d'enfant).

### Bourse

À poser si la personne est étudiante.

- **En-tête** : `Bourse`
- **Question** : Avez-vous une bourse d'études ?
- **Réponses** :
  - Oui, je suis boursier(e)
  - Non, jamais demandée
  - Non, elle a été refusée
  - Je suis en alternance — apprentissage ou contrat pro
- **Sert à** : bourses et aides du CROUS (une demande est parfois encore possible), aides aux apprentis, conditions de certaines aides au logement.

### Autonomie

À poser si la personne a 60 ans ou plus, est à la retraite, ou s'occupe d'un proche.

- **En-tête** : `Autonomie`
- **Question** : Au quotidien, avez-vous besoin d'aide ?
- **Réponses** :
  - Non, je me débrouille
  - Un peu — courses, ménage
  - Beaucoup — toilette, repas, déplacements
  - Pour un proche — pas pour moi
- **Sert à** : aide à domicile, allocation personnalisée d'autonomie (en principe à partir de 60 ans), aides aux proches aidants.

### Santé

À poser si la santé ou le handicap ont été évoqués, ou si rien d'autre ne fait ressortir d'aide.

- **En-tête** : `Santé`
- **Question** : Une maladie longue ou un handicap dans le foyer ?
- **Réponses** :
  - Non
  - Oui, déjà reconnu — MDPH, invalidité, longue maladie
  - Oui, sans démarche faite
  - Je préfère ne pas dire
- **Sert à** : aides de la MDPH, allocation aux adultes handicapés, aide pour enfant handicapé, pension d'invalidité, aides aux aidants.

### Retards de paiement

À poser si la personne évoque du mal à payer son loyer, ses factures ou ses dettes.

- **En-tête** : `Retards`
- **Question** : Avez-vous du retard pour payer le loyer ou les factures ?
- **Réponses** :
  - Non, pas encore — mais c'est juste
  - Oui, un peu — un ou deux mois
  - Oui, beaucoup — plusieurs mois ou des relances
  - Expulsion ou coupure annoncée — un courrier l'a dit
- **Sert à** : fonds de solidarité logement, aides d'urgence (CCAS, CROUS pour les étudiants), point conseil budget. « Expulsion ou coupure annoncée » : voir la section Urgence du SKILL.md.

### Loyer

À poser si la personne est locataire et que l'aide au logement est en jeu.

- **En-tête** : `Loyer`
- **Question** : Votre loyer par mois, charges comprises ?
- **Réponses** :
  - Moins de 400 €
  - 400 à 700 €
  - 700 à 1 000 €
  - Plus de 1 000 €
- **Variante colocation** : la part de la personne, pas le loyer total.
- **Sert à** : estimer l'aide au logement.

## Série 2 : revenus et aides déjà reçues

### Revenus

- **En-tête** : `Revenus`
- **Question** : Aujourd'hui, combien entre chaque mois dans votre foyer, à peu près ?
- **Réponses (foyer de plusieurs personnes)** :
  - Moins de 1 000 € — salaires, allocations, pensions : tout compris
  - 1 000 à 2 000 €
  - 2 000 à 3 000 €
  - Plus de 3 000 €
- **Variante personne seule ou étudiant** :
  - Moins de 500 € — job, aide des parents, allocations : tout compris
  - 500 à 1 000 €
  - 1 000 à 1 500 €
  - Plus de 1 500 €
- **Sert à** : presque toutes les aides sous conditions de ressources. « Aujourd'hui » compte : après un licenciement ou une séparation, ce sont les revenus actuels qui comptent pour beaucoup d'aides. Si la personne ne répond pas, présenter les aides sous conditions de ressources comme « à vérifier ».

### Aides déjà reçues

- **En-tête** : `Déjà reçu`
- **Question** : Vous recevez déjà une de ces aides ?
- **Plusieurs choix** : oui.
- **Réponses (par défaut)** :
  - Aucune
  - Aide au logement — versée par la CAF ou la MSA
  - Prime d'activité ou RSA
  - Une autre aide de la CAF
- **Variante parents** :
  - Aucune
  - Allocations familiales
  - Aide au logement — versée par la CAF ou la MSA
  - Prime d'activité ou RSA
- **Variante étudiant** :
  - Aucune
  - Bourse
  - Aide au logement — versée par la CAF
  - Une autre aide
- **Variante retraite** :
  - Aucune
  - Minimum vieillesse
  - Aide au logement — versée par la CAF ou la MSA
  - Aide à domicile — de la mairie, du département ou de la caisse de retraite
- **Sert à** : ne pas proposer une aide déjà reçue ; repérer les droits qui en ouvrent d'autres.

## Seulement si utile

À poser en dernière série courte (2 questions au plus), y compris après la recherche si une condition décisive reste inconnue.

### Changement récent

- **En-tête** : `Changement`
- **Question** : Un changement récent ou à venir ?
- **Plusieurs choix** : oui.
- **Réponses** :
  - Naissance — ou bébé attendu
  - Séparation ou deuil
  - Déménagement
  - Aucun de ces cas
- **Sert à** : aides liées aux événements de vie (naissance, parent seul, déménagement).

### Projet

- **En-tête** : `Projet`
- **Question** : Un projet en cours ?
- **Plusieurs choix** : oui.
- **Réponses** :
  - Créer mon entreprise
  - Passer le permis
  - Me former ou reprendre des études
  - Aucun de ces projets
- **Sert à** : aides à la création d'entreprise, aides au permis, aides à la formation.

### Travaux

À poser si la personne est propriétaire.

- **En-tête** : `Travaux`
- **Question** : Des travaux prévus dans le logement ?
- **Réponses** :
  - Oui, pour l'énergie — isolation, chauffage, fenêtres
  - Oui, pour l'adapter — âge ou handicap
  - Non
- **Sert à** : aides à la rénovation énergétique, aides à l'adaptation du logement.

### Nationalité

À poser seulement si une aide probable en dépend : certaines aides exigent une nationalité ou une durée de séjour régulier, et ces règles changent.

- **En-tête** : `Nationalité`
- **Question** : Votre nationalité ? Certaines aides en dépendent.
- **Réponses** :
  - Française
  - Europe — Union européenne, Islande, Norvège, Liechtenstein ou Suisse
  - Autre — avec un titre de séjour
  - Je préfère ne pas dire
- **Sert à** : conditions de nationalité ou de séjour. Si la personne ne répond pas, présenter l'aide concernée comme « à vérifier ».

### Aides locales

À poser quand les aides de la commune ou du département peuvent compter (logement, énergie, transport, personnes âgées, urgence), si la ville n'est pas déjà connue et si l'outil offre un champ libre.

- **En-tête** : `Code postal`
- **Question** : Pour chercher aussi les aides de votre ville : tapez votre code postal dans la case « Autre », en bas.
- **Réponses** :
  - Passer — on garde les aides nationales
  - J'habite en outre-mer — les règles diffèrent parfois
- **Sert à** : aides de la mairie (CCAS), du département et de la région ; règles propres à l'outre-mer.

## Choisir et continuer

### Choisir l'aide

- **En-tête** : `Choix`
- **Question** : Par laquelle on commence ?
- **Réponses** :
  - [Aide la plus utile] (recommandé) — ce qu'elle apporte, en quelques mots
  - [Deuxième aide] — ce qu'elle apporte
  - [Troisième aide] — ce qu'elle apporte
  - Plus tard — je garde la liste

### Continuer après une demande

- **En-tête** : `Suite`
- **Question** : Il reste [aide] et [aide]. On continue ?
- **Réponses** :
  - Oui, [aide suivante]
  - Plus tard — je garde la liste

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

# Exemples de conversation

Ces exemples illustrent le rythme et la longueur attendus. Les aides, les montants et les noms de boutons sont des illustrations : dans une vraie conversation, ils viennent de la recherche faite au cas par cas.

Les appels à l'outil de questions sont décrits entre crochets : ce que la personne voit, ce sont des questions avec des réponses à cliquer.

## Exemple 1 : perte d'emploi, parent seul

**Personne** : je viens de me faire licencier, je suis seule avec mes 2 enfants, je sais même pas à quoi j'ai droit

*(En silence : Claude relève ce qui est déjà dit. Foyer : seule avec 2 enfants. Travail : sans emploi. Il ne le redemandera pas.)*

**Claude** :

> Je cherche vos aides. Quelques réponses à cliquer, 2 minutes.

> [Outil de questions, 4 questions]
> **Âge** · Quel âge avez-vous ? → Moins de 25 ans · 25 à 29 ans · 30 à 64 ans · 65 ans ou plus
> **Logement** · Pour votre logement, vous êtes… ? → Locataire · Propriétaire · Hébergé(e) · Sans logement stable
> **Chômage** · Côté France Travail, vous êtes… ? → Inscrit(e), avec allocation · Inscrit(e), sans allocation · Pas inscrit(e) · Je crée mon entreprise
> **Âges enfants** · Quel âge ont vos enfants ? (plusieurs choix) → Moins de 3 ans · 3 à 5 ans · 6 à 17 ans · 18 ans ou plus

*(Le socle étant en partie connu, Claude complète le premier appel avec deux questions de série 2.)*

**Personne** : [30 à 64 ans · Locataire · Pas inscrit(e) · 3 à 5 ans, 6 à 17 ans]

**Claude** :

> [Outil de questions, 3 questions, sans texte autour]
> **Revenus** · Combien entre chaque mois dans votre foyer, à peu près ? → Moins de 1 000 € · 1 000 à 2 000 € · 2 000 à 3 000 € · Plus de 3 000 €
> **Déjà reçu** · Vous recevez déjà une de ces aides ? (plusieurs choix) → Aucune · Aide au logement · Prime d'activité ou RSA · Allocations familiales
> **Loyer** · Votre loyer par mois, charges comprises ? → Moins de 400 € · 400 à 700 € · 700 à 1 000 € · Plus de 1 000 €

**Personne** : [1 000 à 2 000 € · Allocations familiales · 700 à 1 000 €]

*(En silence : Claude passe en revue les familles d'aides « Sans emploi » et « Parents ». Il vérifie chaque aide sur les sites officiels et croise avec une seconde source. Il écarte les allocations familiales, déjà reçues, et estime les montants avec les simulateurs officiels.)*

**Claude** :

> J'ai trouvé 3 aides pour vous.
>
> 💼 **Allocation chômage** · environ 1 100 €/mois · France Travail
> 🏠 **Aide au logement** · environ 250 €/mois · CAF
> 🩺 **Complémentaire santé solidaire** (mutuelle gratuite ou à petit prix) · Assurance maladie
> À vérifier : allocation de soutien familial, si l'autre parent ne verse pas de pension.
> Montants estimés : ce sont France Travail et la CAF qui calculent le montant exact.

> [Outil de questions]
> **Choix** · Par laquelle on commence ? → Allocation chômage (recommandé) · Aide au logement · Complémentaire santé solidaire · Plus tard

**Personne** : [Allocation chômage (recommandé)]

*(En silence : Claude charge le skill demarche-pas-a-pas et lui transmet l'aide, l'organisme, les conditions vérifiées et les réponses déjà données. La phase « Comprendre » est faite : rien n'est redemandé.)*

**Claude** :

> On vous inscrit à France Travail : c'est ce qui ouvre l'allocation. 4 étapes, 20 minutes.
> Dites « explique » si vous voulez le pourquoi.
>
> **Étape 1/4** · Ouvrez francetravail.fr
> 👉 Cliquez « Je m'inscris ».
> Répondez « ok » ou « bloqué ».

*(La suite se déroule selon demarche-pas-a-pas, une étape à la fois. À la fin de la démarche :)*

**Claude** :

> ✅ C'est fait. Gardez la capture de la confirmation d'inscription.

> [Outil de questions]
> **Suite** · Il reste l'aide au logement et la complémentaire santé solidaire. On continue ? → Oui, l'aide au logement · Plus tard

**Personne** : [Plus tard]

**Claude** :

> 📌 Vos aides à demander : aide au logement, complémentaire santé solidaire. Dites « mes aides » pour reprendre.

## Exemple 2 : aucune aide ne ressort

*(Après deux séries de questions, la recherche ne fait ressortir aucune aide probable.)*

**Claude** :

> Je n'ai pas trouvé d'aide pour votre situation actuelle. Si vos revenus baissent ou si votre foyer change, on refait le point.

> [Outil de questions]
> **Rendez-vous** · Voulez-vous que je trouve un lieu près de chez vous pour faire un bilan complet avec quelqu'un ? → Oui · Non merci

*(Pas d'aide inventée pour « faire plaisir ». Une réponse franche, et une porte ouverte.)*

## Contre-exemple : ce qu'il ne faut pas faire

*(Réponse au même premier message que l'exemple 1.)*

> Bonjour ! Pour savoir à quelles aides vous avez droit, j'ai besoin de quelques informations :
> 1. Quel est votre âge exact ?
> 2. Quel est le montant exact de vos revenus des 12 derniers mois ?
> 3. Quel est votre numéro allocataire CAF ?
> 4. Êtes-vous locataire ? Si oui, quel est le montant de votre loyer ?
> 5. Avez-vous des enfants ? Quel âge ont-ils ?
> 6. …

Pourquoi c'est un échec :
- questions écrites dans le texte au lieu de réponses à cliquer ;
- montants exacts et identifiant demandés, alors qu'une tranche suffit et qu'un identifiant est inutile ;
- question sur les enfants alors que la personne en a déjà parlé ;
- tout d'un coup : exactement ce qui fait abandonner un simulateur.

Autre échec fréquent : présenter douze aides avec leurs conditions détaillées. Trois à cinq lignes claires, puis une question à cliquer, valent mieux qu'un catalogue.

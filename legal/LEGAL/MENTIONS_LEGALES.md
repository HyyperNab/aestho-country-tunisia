# AESTHÉA — Mentions légales

**Date : 2026-11-20 · Version : v1.0.0**

---

Modèle à compléter par l'éditeur du logiciel AESTHÉA. Les mentions marquées
[PLACEHOLDER …] doivent être remplacées par les informations exactes de
l'éditeur et de son canal de distribution avant toute publication.

## 1. Éditeur du logiciel

| Champ | Valeur |
|---|---|
| Dénomination sociale | [PLACEHOLDER — dénomination sociale de l'éditeur] |
| Forme juridique | [PLACEHOLDER — ex. : SUARL, SARL…] |
| Siège social | [PLACEHOLDER — adresse complète du siège, Tunisie] |
| Registre du commerce | [PLACEHOLDER — registre et numéro d'immatriculation] |
| Matricule fiscal | [PLACEHOLDER — matricule fiscal] |
| Capital social | [PLACEHOLDER — capital en dinars tunisiens] |
| Téléphone | [PLACEHOLDER — téléphone] |
| Email / contact | [PLACEHOLDER — adresse email de contact] |
| Directeur de la publication | [PLACEHOLDER — nom du représentant légal] |

L'éditeur est le **vendeur** du logiciel AESTHÉA : il concède au praticien
une licence d'utilisation par cabinet (voir `LICENSE.md` et `CGU.md`).

## 2. Logiciel

- **Nom** : AESTHÉA
- **Nature** : logiciel de gestion de cabinet médico-esthétique, chirurgie
  esthétique et dermatologie, livré sous forme d'application web progressive
  (PWA) hors-ligne, monofichier, sans serveur central, sans dépendance
  externe, sans télémétrie.
- **Version du présent document** : v1.0.0
- **Propriété intellectuelle** : le logiciel, sa conception, son code, son
  interface, sa marque et sa documentation sont la propriété exclusive de
  l'éditeur. Toute reproduction, redistribution, rétro-ingénierie ou
  modification non autorisée est interdite (voir `LICENSE.md`).

## 3. Hébergement

Le logiciel AESTHÉA est distribué par **hébergement statique** : les fichiers
de distribution (PWA) sont servis par un hébergeur de fichiers statiques
(CDN / edge, HTTPS).

- **Hébergeur du canal de distribution** : [PLACEHOLDER — identité de
  l'hébergeur statique, adresse, coordonnées].
- **Traitement côté serveur : néant.** Le logiciel ne traite **aucune donnée
  côté serveur** : il ne transmet, ne collecte et n'héberge aucune donnée de
  santé, aucune donnée de cabinet, aucune donnée de patient. L'ensemble des
  données saisies par le praticien est chiffré (AES-256-GCM) et stocké
  exclusivement sur l'appareil du praticien et sur les supports qu'il choisit
  lui-même (voir `CONFIDENTIALITE.md`).

L'éditeur ne reçoit jamais de données de santé. Aucune donnée ne quitte
l'appareil du praticien, sauf si le praticien choisit lui-même un transport
cloud pour son paquet chiffré `.aesthea` — transport qui relève alors de sa
responsabilité et des garde-fous de l'art. 52 de la loi organique
n° 2004-63 (voir `docs/REGULATORY.md` §1 et `INPDP.md`).

## 4. Protection des données personnelles

- Le logiciel est un **outil local** : le praticien est le responsable du
  traitement des données de ses patients au sens de la loi organique
  n° 2004-63 du 27 juillet 2004. Les formalités INPDP (déclaration,
  autorisation, transferts) incombent au praticien ; l'éditeur fournit un
  dossier d'accompagnement (`INPDP.md`) sans se substituer au praticien.
- L'éditeur n'est ni responsable de traitement, ni sous-traitant, ni
  hébergeur de données de santé : il n'en a aucun accès (voir `CGU.md` et
  `CONFIDENTIALITE.md`).
- Le logiciel n'utilise **aucun cookie**, aucun traceur, aucune télémétrie
  et n'effectue **aucun appel réseau** pendant son utilisation.

## 5. Responsabilité

### Avertissement médical et responsabilité

AESTHÉA est un outil de gestion et d'aide à la décision pour professionnels
de santé. Il ne remplace pas le jugement clinique du praticien : la
prescription, l'acte et la décision finale restent sous sa responsabilité
exclusive.

Les modèles, posologies, seuils et délais de suivi proposés sont des points
de départ à adapter au patient et à vérifier contre la RCP du produit
utilisé. L'application ne prescrit rien automatiquement : chaque ligne est
modifiable et chaque validation relève du praticien. Aucun message n'est
envoyé sans son geste explicite.

Cet avertissement est présenté une seule fois lors du premier lancement
(acceptation enregistrée localement sur l'appareil, sans donnée de santé) et
reste accessible à tout moment dans la présente page. Il ne dispense pas le
praticien des avertissements affichés au point d'action — verdicts
STOP/CONDITIONNEL, contre-indications, signes d'alerte patient, consentements
et traçabilité des lots — qui demeurent intégraux.

- L'éditeur ne fournit aucun conseil médical, fiscal ou juridique. Le
  logiciel est une aide organisationnelle ; le médecin demeure la seule
  autorité décisionnaire pour ses patients.
- Les délais de suivi post-acte pré-configurés sont des conventions de départ
  à valider par le praticien (voir `LICENSE.md` art. 7).
- La phrase secrète est sous la responsabilité exclusive du praticien ; sans
  elle, les données sont irrécupérables (propriété de souveraineté, par
  conception).

## 6. Contact

Pour toute question relative au logiciel, à la licence ou aux présentes
mentions : [PLACEHOLDER — email / formulaire / adresse postale de l'éditeur].

---

*Modèle à compléter et à faire relire par un juriste avant publication. Les
mentions d'hébergement dépendent du canal de distribution effectivement
retenu par l'éditeur (voir `docs/COMMERCIALISATION.md` §B) ; en l'état, aucun
serveur applicatif n'existe et aucune donnée n'est traitée côté serveur.*

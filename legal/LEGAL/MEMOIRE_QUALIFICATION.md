# MÉMOIRE DE QUALIFICATION — questions juridiques ouvertes

À remettre au juriste avec les documents du pack (`LICENSE.md`, `CGU.md`,
`CONFIDENTIALITE.md`, `INPDP.md`) et `REGULATORY.md` (référentiel des
articles, RETRIEVED). Chaque question : position documentée + ce qu'il reste à
trancher. **Ce mémoire ne remplace pas un avis juridique.**

## Q1 — Qualification de l'éditeur (loi 2004-63)

**Question** : l'éditeur, qui fournit un outil 100 % hors-ligne sans aucun flux
de données, est-il « sous-traitant » ou « responsable de traitement » au sens
de la loi organique n° 2004-63 ?

**Position documentée (JUDGED)** : ni l'un ni l'autre pour les données des
patients — l'éditeur n'a « aucun accès », ne reçoit « aucune copie » et
n'effectue « aucun traitement » (LICENSE.md art. 6). Le praticien est le seul
responsable de traitement (CGU.md, INPDP.md). La seule donnée traitée par
l'éditeur est la **licence** (identité du cabinet, nombre de postes,
expiration) — hors périmètre santé.

**À trancher** : confirmation écrite de cette lecture ; le cas échéant,
enregistrement de la licence comme traitement distinct (finalité : gestion
commerciale).

## Q2 — Transfert art. 52 et paquet chiffré

**Question** : un paquet `.aesthea` chiffré AES-256-GCM côté client, transporté
par le praticien lui-même via son propre cloud, constitue-t-il un « transfert
de données à caractère personnel vers l'étranger » soumis à autorisation INPDP
(art. 52) ?

**Position documentée (JUDGED, REGULATORY.md §1)** : oui par prudence — le
praticien peut déchiffrer le paquet ; l'administration peut considérer qu'il
s'agit de données personnelles. Le logiciel documente le garde-fou (consentement
art. 47, adéquation art. 51, autorisation art. 52) et l'option « zéro transfert »
(local + clé USB).

**À trancher** : confirmation par l'INPDP (une consultation préalable est
recommandée) ; rédaction d'une notice praticien d'une page.

## Q3 — Formalités exactes (déclaration vs autorisation)

**Question** : pour un cabinet médical traitant des données de santé, quelles
formalités exactes (déclaration art. 7, autorisation art. 8, conditions du
décret n° 2007-3004) ?

**Position documentée** : art. 8 = autorisation pour données sensibles
[RETRIEVED] ; la checklist INPDP.md prépare les deux cas.

**À trancher** : vérification in extenso du décret n° 2007-3004 (non lu à ce
jour) et de la délibération INPDP n° 4/2018.

## Q4 — Juridiction et parties (LICENSE art. 11.2, CGU art. 12)

**Question** : la clause de juridiction est-elle adaptée à des parties
professionnelles/commerçantes en droit tunisien ?

**À trancher** : choix du tribunal [PLACEHOLDER], vérification des règles de
compétence matérielle.

## Q5 — Modification unilatérale des CGU (CGU art. 13.2)

**Question** : encadrement requis pour un contrat professionnel (préavis,
opposabilité, versioning) ?

**À trancher** : mécanisme de préavis + preuve d'information (l'app affiche la
version des CGU acceptées — à implémenter si exigé).

## Q6 — Durées de conservation et honoraires

**Question** : durée légale de conservation des documents comptables et
obligation de note d'honoraires (art. 37 du code de déontologie médicale).

**Position documentée** : 10 ans d'usage (non confirmé), note d'honoraires
requise (REGULATORY.md §5, marqué à vérifier).

**À trancher** : confirmation des deux points ; le logiciel conserve déjà
factures et journal d'audit sans purge automatique (aucune donnée détruite —
conforme à la conservation).

## Statut global

Toutes les citations d'articles du pack sont ancrées dans REGULATORY.md
(`python3 scripts/check_citations.py` → OK). Les [PLACEHOLDER] (identité de
l'éditeur, juridiction, montants) doivent être remplis avant signature.

# AESTHÉA — Conditions Générales d'Utilisation (CGU)

**Date : 2026-11-20 · Version : v1.0.0 · Droit applicable : droit tunisien**

---

## Article 1 — Objet

Les présentes Conditions Générales d'Utilisation (ci-après les « CGU »)
régissent les relations entre :

- **l'Éditeur** : [PLACEHOLDER — dénomination sociale], [PLACEHOLDER — forme
  juridique], siège social [PLACEHOLDER — adresse], matricule fiscal
  [PLACEHOLDER — matricule fiscal] (ci-après « l'Éditeur ») ;
- **le Praticien** : le médecin esthétique, chirurgien esthétique ou
  dermatologue exerçant en cabinet en Tunisie, ayant acquis une licence
  d'utilisation du logiciel AESTHÉA (ci-après « le Praticien »).

Les CGU s'appliquent à l'installation et à l'utilisation du logiciel AESTHÉA
(ci-après le « Logiciel ») : application web progressive (PWA) hors-ligne de
gestion de cabinet médico-esthétique, fonctionnant sans serveur central, sur
l'appareil du Praticien.

Le contrat de licence (`LICENSE.md`) fait partie intégrante des présentes. En
cas de contradiction, les stipulations de la licence prévalent pour les
éléments qu'elle couvre (étendue, restrictions, garanties, responsabilité,
maintenance).

## Article 2 — Acceptation

L'installation, le déploiement ou l'utilisation du Logiciel, ainsi que
l'acceptation du bon de commande, valent acceptation pleine et entière des
présentes CGU par le Praticien. À défaut d'acceptation, le Praticien ne doit
pas utiliser le Logiciel.

## Article 3 — Description du Logiciel

3.1. Le Logiciel couvre notamment : dossier patient (antécédents, allergies,
traitements, notes), rendez-vous, actes avec traçabilité des lots, consentement
éclairé par acte, facturation TVA tunisienne avec encaissement et devis, stock
de produits injectables, rappels post-acte, dépistage des contre-indications
(aide à la décision, jamais un diagnostic), journal d'audit local hash-chaîné,
gestion de trois rôles (médecin-chef, secrétaire, comptable) et synchronisation
par paquets `.aesthea` (manifeste SHA-256, fusion LWW) ou « dossier
synchronisé » (File System Access).

3.2. Le Logiciel fonctionne **intégralement hors-ligne sur l'appareil du
Praticien** : le coffre de données est chiffré en local (AES-256-GCM, clé
dérivée de la phrase secrète par PBKDF2-SHA256, 600 000 itérations), la phrase
secrète ne quitte jamais l'appareil, et aucun serveur, aucun compte, aucune
télémétrie n'existe.

3.3. Le Logiciel est une aide organisationnelle. Il ne délivre aucun
diagnostic, aucune conclusion médicale, aucun conseil fiscal ou juridique. Le
Praticien demeure seul responsable de ses décisions médicales, de ses
obligations fiscales et de ses formalités réglementaires.

## Article 4 — Licence

L'utilisation du Logiciel est soumise à la licence concédée par l'Éditeur
(`LICENSE.md`) : licence **par cabinet**, limitée à un nombre de **postes**
[PLACEHOLDER — nombre de postes inclus], non exclusive, non cessible, non
sous-licenciable, sans transfert de propriété. Toute redistribution ou
rétro-ingénierie est interdite.

Le Praticien s'engage à n'utiliser le Logiciel que dans les limites de la
licence acquise et à régler le prix convenu
[PLACEHOLDER — prix et modalités de paiement].

## Article 5 — Obligations de l'Éditeur

L'Éditeur s'engage à :

1. fournir le Logiciel dans une version fonctionnelle conforme à sa
   documentation, sans garantie particulière au-delà des stipulations de la
   licence (art. 7 et 8 de `LICENSE.md`) ;
2. publier les mises à jour qu'il décide, via le canal de distribution désigné,
   sans installation automatique ni accès à distance aux postes du Praticien ;
3. **ne jamais recevoir, collecter, traiter, héberger ou consulter de données
   de santé** : l'architecture du Logiciel est dépourvue de serveur et d'appel
   réseau ; l'Éditeur n'a par construction aucun accès au coffre du Praticien ;
4. maintenir la documentation du Logiciel et le dossier d'accompagnement
   réglementaire (notamment `INPDP.md`), sans se substituer au Praticien ni à
   ses conseils.

## Article 6 — Obligations du Praticien

### 6.1. Phrase secrète — responsabilité exclusive

La phrase secrète choisie par le Praticien est le seul moyen de déchiffrer le
coffre de données. Elle est sous la **responsabilité exclusive du
Praticien** :

- elle ne quitte jamais l'appareil et n'est connue d'aucun tiers, y compris de
  l'Éditeur ;
- en cas de perte ou d'oubli, les données sont **irrécupérables** ; l'Éditeur
  ne dispose d'aucun moyen de récupération, de réinitialisation ou de
  restauration — c'est une propriété de souveraineté, pas un défaut ;
- le Praticien veille à la confidentialité des phrases de rôle qu'il remet à
  ses collaborateurs (secrétaire, comptable) et à la sécurité des appareils
  (verrouillage automatique du Logiciel, accès physique).

### 6.2. Sauvegardes du paquet `.aesthea`

Le Praticien est **seul responsable de ses sauvegardes**. Le Logiciel produit
un paquet `.aesthea` chiffré (manifeste SHA-256) que le Praticien doit
exporter et conserver sur un support de son choix (disque local, clé USB,
dossier synchronisé par son propre client cloud). En l'absence de sauvegarde,
toute perte de données (panne, effacement du stockage local du navigateur,
incident) est irréparable. L'Éditeur ne fournit aucune garantie de
récupération.

Le Praticien conserve également ses documents comptables (factures, devis
convertis, notes d'honoraires) selon les durées légales en vigueur (voir
`docs/REGULATORY.md` §5 — durée de conservation à confirmer par le comptable).

### 6.3. Conventions médicales et paramètres

Les délais de suivi post-acte, seuils d'alerte et règles pré-configurés sont
des **conventions de départ** que le Praticien doit **valider** au regard de la
RCP/notice de chaque produit et de sa pratique (voir `docs/REGULATORY.md` §2 et
`README.md` — limites honnêtes). Les taux de TVA sont des paramètres que le
comptable du cabinet tranche acte par acte. Le Praticien demeure seul
responsable de ces validations.

### 6.4. Habilitation des collaborateurs et secret professionnel

Le Logiciel permet trois rôles (médecin-chef, secrétaire, comptable) avec une
matrice de permissions restrictive : le secrétaire n'accède jamais aux champs
médicaux, le comptable jamais aux éléments cliniques. Le Praticien est
**seul responsable de l'habilitation de ses collaborateurs**, du choix des
postes de rôle et du respect du secret professionnel. Conformément à
l'art. 63 de la loi organique n° 2004-63, le traitement des données de santé
ne peut être mis en œuvre que par des médecins ou des personnes soumises au
secret professionnel — le Praticien s'en assure pour chaque poste qu'il
provisionne (voir `docs/REGULATORY.md` §1 et §2).

### 6.5. Environnement d'exécution

Le Praticien utilise un navigateur compatible (notamment pour la File System
Access API utilisée par le « dossier synchronisé ») et maintient ses appareils
à jour. Les limites de compatibilité sont documentées (voir `docs/ARCHITECTURE.md`
— support navigateur).

## Article 7 — Protection des données personnelles (loi organique n° 2004-63)

### 7.1. Rôles respectifs

Le Praticien, qui collecte et traite les données de santé de ses patients dans
le cadre de son cabinet, est le **responsable du traitement** au sens de la
loi organique n° 2004-63 du 27 juillet 2004 relative à la protection des
données à caractère personnel.

L'Éditeur **n'effectue aucun traitement** de données à caractère personnel :
le Logiciel fonctionne exclusivement sur l'appareil du Praticien, sans
transmission, collecte, hébergement ni consultation par l'Éditeur (voir
l'article 8 ci-après).

### 7.2. Formalités INPDP à la charge du Praticien

Il incombe au Praticien, en qualité de responsable du traitement :

1. d'effectuer auprès de l'INPDP la **déclaration** et, pour les traitements
   de données de santé, d'obtenir l'**autorisation préalable** exigée par les
   art. 7 et 14 de la loi n° 2004-63, dans les conditions du décret
   n° 2007-3004 du 27 novembre 2007 et de la délibération INPDP n° 4 du
   5 septembre 2018 (voir `docs/REGULATORY.md` §1) ;
2. de tenir son registre des traitements ;
3. de respecter les droits des personnes concernées (information, consentement,
   accès, opposition le cas échéant) conformément à la loi n° 2004-63 ;
4. de veiller au secret professionnel (art. 63 de la loi n° 2004-63) et aux
   règles du Code de déontologie médicale tunisien (dossier médical portant le
   nom du médecin signataire, non-communication du dossier).

L'Éditeur fournit un dossier d'accompagnement (`INPDP.md`) comprenant la
checklist de déclaration et le modèle de registre. Ce dossier est un support ;
il ne constitue pas un conseil juridique et ne dispense pas le Praticien de ses
déclarations, dont il reste seul responsable.

### 7.3. Consentement des patients — géré par le Logiciel

Le Logiciel gère le **consentement éclairé par acte** : consentement daté, avec
signature, lié à l'acte pratiqué, ainsi que les consentements photos/données
personnelles datés. Le Praticien :

1. utilise ce mécanisme pour recueillir, avant chaque acte concerné, le
   consentement libre et éclairé du patient, conformément à la loi n° 2004-63 ;
2. conserve la preuve de ces consentements dans le coffre (exportée dans le
   paquet `.aesthea`) ;
3. reste **seul responsable de la licéité** des consentements recueillis : le
   Logiciel fournit le mécanisme, pas la décision, et ne se substitue pas à
   l'information délivrée au patient par le médecin.

### 7.4. Transferts vers l'étranger — garde-fou art. 52

Aucune donnée ne quitte l'appareil du Praticien par le fait de l'Éditeur. Si
le Praticien choisit lui-même de transporter son paquet `.aesthea` chiffré via
un cloud étranger (iCloud Drive, Google Drive, kDrive, Proton Drive…), ce
transport constitue un transfert de données au sens de la loi n° 2004-63 et il
lui incombe :

1. de recueillir le **consentement** des personnes concernées (art. 47) ;
2. de vérifier le niveau de **protection adéquat** du pays de destination
   (art. 51) ;
3. d'obtenir l'**autorisation préalable de l'INPDP**, obligatoire dans tous les
   cas (art. 52, instruction sous un mois).

L'option « zéro transfert » (stockage local sur l'appareil + clé USB, sans
cloud) dispense de ces formalités de transfert ; elle est recommandée par
défaut. Voir `docs/REGULATORY.md` §1 et `INPDP.md` §7. [À VÉRIFIER PAR UN
JURISTE — la qualification d'un paquet chiffré côté client comme transfert de
données personnelles relève de l'appréciation de l'INPDP.]

## Article 8 — Absence de traitement par l'Éditeur — clause « zéro donnée »

8.1. Le Logiciel est conçu pour que **l'Éditeur ne reçoive jamais de données
de santé** : aucune donnée ne quitte l'appareil du Praticien du fait du
Logiciel ; le Logiciel n'émet aucun appel réseau, n'utilise aucun cookie,
aucune télémétrie, aucun compte, aucune authentification serveur.

8.2. En conséquence, l'Éditeur :

- n'est **pas sous-traitant** du Praticien au sens de la loi n° 2004-63 :
  aucune opération de traitement n'est réalisée pour le compte du Praticien ;
- n'est **pas hébergeur** de données de santé : il ne stocke, ne conserve ni ne
  transporte aucune donnée du cabinet ;
- ne peut répondre d'aucune obligation de confidentialité portant sur des
  données qu'il ne détient pas.

8.3. Le Praticien déclare avoir compris que la souveraineté de ses données
repose sur : la confidentialité de sa phrase secrète, ses sauvegardes
`.aesthea`, la sécurité de ses appareils et l'habilitation de ses
collaborateurs. [À VÉRIFIER PAR UN JURISTE — la qualification de l'Éditeur
(fournisseur d'outil hors-ligne sans aucun flux de données) au regard de la
loi n° 2004-63 mérite confirmation écrite.]

## Article 9 — Responsabilités

9.1. La responsabilité de l'Éditeur est régie par les art. 7 et 8 de
`LICENSE.md` (absence de garantie, plafonnement, exclusions), intégralement
applicables aux présentes.

9.2. Le Praticien est seul responsable : de ses décisions médicales, de ses
obligations fiscales et comptables (TVA, télé-déclaration TTN — hors périmètre
du Logiciel, voir `docs/REGULATORY.md` §7), de ses formalités INPDP, de ses
sauvegardes, de la garde de sa phrase secrète et des phrases de rôle, et de
l'usage conforme du Logiciel par ses collaborateurs.

9.3. Chaque Partie répond des dommages directs causés à l'autre par sa faute
prouvée, dans les limites fixées par la licence.

## Article 10 — Maintenance, mises à jour et support

La maintenance, les mises à jour et le support sont régis par l'art. 9 de
`LICENSE.md` : mises à jour publiées par l'Éditeur via son canal de
distribution, aucune installation à distance, support selon les modalités
[PLACEHOLDER — niveau de support inclus].

## Article 11 — Résiliation

La résiliation de la licence emporte résiliation des présentes, selon les
modalités de l'art. 10 de `LICENSE.md` (durée, manquement substantiel,
résiliation de plein droit, cessation d'utilisation et destruction des copies,
maintien des données sur les appareils du Praticien, survie des clauses).

## Article 12 — Droit applicable et juridiction

Les présentes CGU sont soumises au **droit tunisien**. Tout litige relève de
la compétence exclusive des tribunaux de
[PLACEHOLDER — juridiction compétente]. [À VÉRIFIER PAR UN JURISTE — la clause
d'attribution de compétence doit être adaptée à la qualité des parties et au
droit tunisien applicable.]

## Article 13 — Divers

13.1. Nullité partielle : si une stipulation des présentes est déclarée nulle,
les autres demeurent en vigueur.

13.2. Les présentes peuvent être modifiées par l'Éditeur ; la version
applicable est celle en vigueur à la date d'acceptation de la licence ou
notifiée au Praticien. [À VÉRIFIER PAR UN JURISTE — encadrer la modification
unilatérale pour un contrat professionnel.]

13.3. Contacts : [PLACEHOLDER — adresse de contact de l'éditeur].

---

*Modèle à compléter (placeholders) et à faire relire par un juriste avant
signature. Les références réglementaires citées renvoient à
`docs/REGULATORY.md` ; tout élément excédant ce qui y est documenté est marqué
[À VÉRIFIER PAR UN JURISTE].*

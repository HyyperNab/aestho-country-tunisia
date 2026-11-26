# AESTHÉA — Contrat de Licence Utilisateur Final (EULA)

**Date : 2026-11-20 · Version : v1.0.0 · Droit applicable : droit tunisien**

---

## Article 1 — Parties

Le présent contrat de licence utilisateur final (ci-après le « Contrat ») est
conclu entre :

- **L'Éditeur** : [PLACEHOLDER — dénomination sociale], [PLACEHOLDER — forme
  juridique], dont le siège social est situé [PLACEHOLDER — adresse du siège],
  immatriculé(e) au registre du commerce sous le numéro
  [PLACEHOLDER — numéro de registre], titulaire du matricule fiscal
  [PLACEHOLDER — matricule fiscal], ci-après « l'Éditeur », éditeur du logiciel
  AESTHÉA ;
- **Le Licencié** : le cabinet de médecine esthétique, chirurgie esthétique ou
  dermatologie ayant acquis une licence d'utilisation du Logiciel, représenté
  par le praticien responsable (médecin-chef), ci-après « le Licencié » ou « le
  Cabinet ».

L'Éditeur et le Licencié sont ci-après désignés individuellement « la Partie »
et collectivement « les Parties ».

## Article 2 — Définitions

- **Logiciel** : le logiciel de gestion de cabinet médico-esthétique AESTHÉA,
  livré sous forme d'application web progressive (PWA) fonctionnant
  exclusivement sur l'appareil du Licencié, hors-ligne, sans serveur central,
  dans la version objet du présent Contrat.
- **Poste** : un appareil (ordinateur, tablette ou autre dispositif compatible)
  sur lequel le Logiciel est installé ou utilisé au sein du Cabinet, provisionné
  selon l'un des rôles définis par le Logiciel (médecin-chef, secrétariat,
  comptabilité).
- **Coffre** : l'espace de stockage chiffré du Logiciel (AES-256-GCM, clé
  dérivée de la phrase secrète), hébergé localement dans le navigateur de
  l'appareil du Licencié.
- **Phrase secrète** : la phrase de passe choisie par le Licencié, à partir de
  laquelle est dérivée la clé de chiffrement du Coffre. Elle ne quitte jamais
  l'appareil du Licencié.
- **Paquet .aesthea** : le fichier de sauvegarde ou de synchronisation produit
  par le Logiciel, chiffré, doté d'un manifeste d'intégrité SHA-256, stocké sur
  un support choisi par le Licencié (disque local, clé USB, dossier synchronisé
  par le propre client cloud du Licencié, etc.).
- **Données de santé** : toute donnée à caractère personnel relative à la santé
  des patients du Cabinet, telle que définie par la loi organique n° 2004-63 du
  27 juillet 2004 relative à la protection des données à caractère personnel.

## Article 3 — Objet

Le présent Contrat a pour objet de définir les conditions dans lesquelles
l'Éditeur concède au Licencié un droit personnel, non exclusif, non cessible et
non sous-licenciable d'utilisation du Logiciel, à l'exclusion de toute autre
prérogative.

Le Logiciel est fourni « en l'état ». Il constitue un outil de gestion de
cabinet (dossier patient, rendez-vous, actes, facturation, stock, consentements,
suivi post-acte, journal d'audit local) et une aide organisationnelle. Il ne
délivre aucun diagnostic, aucune conclusion médicale ni aucun conseil fiscal ou
juridique.

## Article 4 — Étendue de la licence : licence par cabinet et nombre de postes

4.1. La licence est concédée **par cabinet** : elle couvre l'usage du Logiciel
pour l'activité du seul Cabinet désigné au bon de commande, sur l'ensemble de
ses sites d'exercice, à l'exclusion de toute autre structure, société, ou
praticien exerçant en dehors du Cabinet.

4.2. La licence autorise l'installation et l'utilisation du Logiciel sur un
nombre de **postes** défini au bon de commande :
[PLACEHOLDER — nombre de postes inclus dans la licence de base], dont au
maximum un poste maître (rôle « médecin-chef ») et des postes de rôle
(secrétariat, comptabilité) dans la limite convenue. Toute installation ou
utilisation sur un poste supplémentaire requiert l'acquisition préalable d'une
extension de licence auprès de l'Éditeur.

4.3. La licence est strictement personnelle au Cabinet. Elle ne peut être ni
cédée, ni transférée, ni concédée en sous-licence, ni mise à disposition d'un
tiers (notamment : autre cabinet, société de services, prestataire informatique
exploitant le Logiciel pour le compte d'autrui), sans accord écrit préalable de
l'Éditeur.

4.4. La licence ne confère au Licencié aucun droit de propriété sur le Logiciel,
son code, sa documentation ou ses marques.

## Article 5 — Restrictions d'usage

Sauf autorisation écrite préalable et expresse de l'Éditeur, il est interdit au
Licencié :

1. de redistribuer, céder, louer, prêter, vendre ou mettre à disposition du
   public le Logiciel ou toute copie de celui-ci, à titre gratuit ou onéreux ;
2. de procéder ou de faire procéder à la rétro-ingénierie, la décompilation, le
   désassemblage du Logiciel, ou à toute tentative d'accès au code source ou aux
   mécanismes internes de chiffrement, de licence ou de contrôle d'intégrité du
   Logiciel, sous réserve des droits impérativement reconnus par la loi ;
3. de modifier, adapter, traduire, corriger ou créer des œuvres dérivées du
   Logiciel ;
4. de contourner, neutraliser ou altérer les mécanismes techniques du Logiciel
   (chiffrement, journal d'audit, matrice de rôles, verrous de licence) ;
5. d'utiliser le Logiciel au-delà du nombre de postes licenciés ou hors du
   périmètre du Cabinet ;
6. de retirer, masquer ou altérer les mentions de propriété intellectuelle,
   marques, avis de version ou mentions légales figurant dans le Logiciel.

Toute violation du présent article constitue une violation substantielle du
Contrat, autorisant l'Éditeur à le résilier de plein droit, sans préjudice de
tous dommages et intérêts.

## Article 6 — Propriété intellectuelle

Le Logiciel, sa conception, son code, sa documentation, son interface, sa
marque, ses bases de données de configuration (catalogue d'actes, règles de
suivi, matrice de rôles) ainsi que l'ensemble des droits de propriété
intellectuelle y afférents demeurent la propriété exclusive et entière de
l'Éditeur ou de ses ayants droit.

Les données saisies dans le Logiciel par le Licencié (dossiers patients,
actes, factures, devis, lots, consentements, journal d'audit) demeurent la
propriété exclusive du Licencié. Elles sont stockées uniquement sur les
appareils et supports du Licencié ; l'Éditeur n'y a aucun accès, n'en reçoit
aucune copie et n'en effectue aucun traitement.

## Article 7 — Garanties — absence de garantie

7.1. Le Logiciel est fourni « en l'état » et « selon disponibilité ». L'Éditeur
ne garantit pas que le Logiciel fonctionnera sans interruption ni erreur, ni
qu'il répondra à l'intégralité des besoins spécifiques du Cabinet.

7.2. L'Éditeur ne donne **aucune garantie d'ordre médical, fiscal, juridique ou
réglementaire**. En particulier :

- les délais de suivi post-acte, seuils d'alerte et règles pré-configurés dans
  le Logiciel sont des **conventions de départ destinées à être validées par le
  praticien**, au regard de la notice/RCP de chaque produit utilisé et de son
  propre jugement clinique ; l'Éditeur ne garantit pas leur pertinence médicale ;
- les taux de TVA paramétrés sont des valeurs par défaut que le comptable du
  Cabinet doit valider ; l'Éditeur ne fournit aucun conseil fiscal ;
- le module de dépistage des contre-indications est une aide à la décision qui
  n'émet aucune conclusion ; le médecin demeure la seule autorité décisionnaire.

7.3. Le Licencié reconnaît que la sécurité de ses données repose sur la
confidentialité de sa phrase secrète. L'Éditeur ne peut, par construction,
restaurer un Coffre dont la phrase secrète est perdue : aucune garantie de
récupération n'est due à ce titre.

7.4. Les garanties légales impérativement applicables demeurent en tout état de
cause.

## Article 8 — Limitation de responsabilité

8.1. L'Éditeur n'est responsable que des dommages directs et prévisibles
résultant d'un manquement avéré du Logiciel à sa documentation, à l'exclusion
de tout dommage indirect (perte de données non sauvegardées, perte
d'exploitation, préjudice commercial, préjudice moral, atteinte à l'image,
manque à gagner).

8.2. La responsabilité totale de l'Éditeur au titre du présent Contrat est
plafonnée, quel que soit le fondement de la réclamation, au montant des sommes
effectivement versées par le Licencié au cours des douze (12) mois précédant le
fait générateur, ou à [PLACEHOLDER — montant plancher en dinars tunisiens] si ce
montant est inférieur.

8.3. L'Éditeur n'encourt aucune responsabilité :

- en cas de perte de la phrase secrète ou d'impossibilité de déchiffrer un
  Coffre ;
- en cas de perte ou de corruption de données résultant d'une absence de
  sauvegarde du Paquet .aesthea par le Licencié, d'un support de stockage
  défaillant, ou d'un service tiers choisi par le Licencié (client cloud,
  support physique) ;
- en cas d'usage non conforme du Logiciel ou de violation des présentes par le
  Licencié ou ses préposés ;
- au titre des décisions médicales, fiscales ou réglementaires prises par le
  Licencié à partir des informations affichées par le Logiciel ;
- en cas de perte de données liée au stockage local du navigateur (IndexedDB)
  lorsque le Licencié n'a pas mis en œuvre de sauvegarde externe.

8.4. Les stipulations du présent article constituent une répartition convenue
des risques entre les Parties et restent applicables après la résiliation du
Contrat.

## Article 9 — Maintenance et mises à jour

9.1. Pendant la durée de la licence, l'Éditeur met à disposition du Licencié
les **mises à jour** du Logiciel qu'il publie (correctifs, évolutions
mineures), via le canal de distribution désigné par l'Éditeur
[PLACEHOLDER — canal de distribution].

9.2. Le Logiciel étant hors-ligne par conception, aucune mise à jour n'est
installée automatiquement ou à distance. Il appartient au Licencié de
télécharger et de déployer les nouvelles versions sur ses postes. L'Éditeur ne
peut en aucun cas accéder aux postes du Licencié.

9.3. L'Éditeur ne s'engage sur aucun contenu, calendrier ou périmètre
fonctionnel des versions futures. Les évolutions majeures peuvent faire l'objet
d'une offre distincte.

9.4. La maintenance corrective est assurée selon les modalités définies au bon
de commande ou dans les présentes : [PLACEHOLDER — niveau de support inclus,
canal de contact, délais indicatifs]. L'Éditeur s'engage à traiter les
signalements de dysfonctionnement qui lui sont transmis selon ces modalités,
sans garantie de délai de résolution.

9.5. Le support ne couvre pas : la récupération de Coffres dont la phrase
secrète est perdue (impossible par conception), les environnements hors
compatibilité déclarée, ni les questions d'ordre médical, fiscal ou juridique,
qui relèvent des conseils du praticien et de son comptable.

## Article 10 — Durée et résiliation

10.1. Le présent Contrat prend effet à la date d'acceptation par le Licencié et
reste en vigueur pour la durée de la licence acquise
[PLACEHOLDER — durée, par défaut un an renouvelable].

10.2. Chaque Partie peut résilier le Contrat en cas de manquement substantiel de
l'autre Partie à ses obligations, non réparé dans un délai de trente (30) jours
après mise en demeure notifiée par écrit.

10.3. L'Éditeur peut résilier le Contrat de plein droit, sans préavis, en cas
de violation de l'article 5 (restrictions d'usage), de non-paiement des sommes
dues, ou d'atteinte à ses droits de propriété intellectuelle.

10.4. En cas de résiliation, quelle qu'en soit la cause :

- le Licencié cesse toute utilisation du Logiciel et détruit les copies du
  Logiciel en sa possession, sur l'ensemble de ses postes, dans un délai de
  quinze (15) jours ;
- les données du Licencié restent stockées sur ses propres appareils et supports
  ; l'Éditeur n'en détient aucune et ne peut procéder à aucune suppression à
  distance ;
- il appartient au Licencié d'exporter le Paquet .aesthea avant l'expiration de
  la licence s'il souhaite conserver ses données dans un format exploitable ;
  l'Éditeur ne fournit aucune garantie de reprise des données par un logiciel
  tiers.

10.5. Les articles 5, 6, 7, 8, 10 et 11 survivent à la résiliation du Contrat.

## Article 11 — Droit applicable et divers

11.1. Le présent Contrat est régi par le **droit tunisien**.

11.2. Tout litige relatif à la formation, l'interprétation, l'exécution ou la
résiliation du présent Contrat relève de la compétence exclusive des tribunaux
de [PLACEHOLDER — juridiction compétente]. [À VÉRIFIER PAR UN JURISTE — la
clause d'attribution de compétence doit être adaptée à la qualité des parties
(commerçant / professionnel) et au droit tunisien applicable.]

11.3. Si une stipulation du présent Contrat est déclarée nulle ou
inapplicable, les autres stipulations demeurent en vigueur et les Parties
substitueront à la stipulation atteinte une stipulation économiquement
équivalente.

11.4. Le fait pour une Partie de ne pas se prévaloir d'une stipulation du
Contrat ne vaut pas renonciation à s'en prévaloir ultérieurement.

11.5. Les documents contractuels (bon de commande, annexes techniques, présentes
conditions) forment un ensemble indivisible. En cas de contradiction, le bon de
commande prévaut pour les éléments commerciaux (prix, nombre de postes, durée)
et les présentes pour les éléments juridiques.

---

*Le présent modèle est fourni à titre de support. Il doit être complété
(placeholders), adapté à l'identité de l'éditeur et revu par un avocat avant
signature. Les références réglementaires citées renvoient à
`docs/REGULATORY.md` ; tout élément excédant ce qui y est documenté est marqué
[À VÉRIFIER PAR UN JURISTE].*

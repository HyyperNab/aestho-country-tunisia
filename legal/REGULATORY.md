# REGULATORY — AESTHÉA v0.4.0 (Tunisie, périmètre vérifié)

Chaque affirmation porte son étiquette (RETRIEVED / JUDGED). Rien ici n'est un
conseil juridique ; le praticien et son comptable restent responsables de leurs
déclarations.

## 1. Protection des données personnelles (Tunisie) — RETRIEVED

- **Loi organique n° 2004-63 du 27 juillet 2004** (protection des données à
  caractère personnel), **art. 7 et 14** : tout traitement de données de santé
  est soumis à **déclaration et autorisation préalable** auprès de l'INPDP,
  conditions fixées par le **décret n° 2007-3004 du 27 novembre 2007**.
- **Art. 8 de la loi 2004-63** : demande d'**autorisation** auprès de l'INPDP
  pour le traitement des données **sensibles** (santé comprise) et pour le
  transfert à l'étranger. [RETRIEVED 2026-11-20 — universitecentrale.net,
  docic.net]
- **Art. 9 de la loi 2004-63** : le traitement doit respecter la **dignité
  humaine, la vie privée et les libertés publiques**. [RETRIEVED 2026-11-20 —
  annexe OFII, tn.diplomatie.gouv.fr]
- **Art. 10 de la loi 2004-63** : la collecte ne peut s'effectuer que pour des
  **finalités licites, déterminées et explicites**. [RETRIEVED 2026-11-20 —
  texte officiel INS, ins.tn]
- **Délibération INPDP n° 4 du 5 septembre 2018** : traitement des données de
  santé.
- **Art. 63 de la loi 2004-63** : le traitement des données de santé ne peut
  être mis en œuvre que par des médecins ou des personnes soumises au secret
  professionnel ; consentement requis (personne concernée, héritiers ou
  tuteur). [texte officiel INS, ins.tn — RETRIEVED 2026-11-20]
- Source : `INPDP_guide_medecins.pdf`, ordremedecins-centre.org.tn (RETRIEVED
  2026-11-17) ; texte officiel ins.tn (RETRIEVED 2026-11-20).

**Conséquence pour AESTHÉA:** nous n'hébergeons rien ; le praticien traite ses
propres données sur son propre appareil, ce qui le place dans le cas prévu par
la loi (dossier médical du cabinet). La checklist de déclaration INPDP est un
livrable à fournir au praticien, pas une fonction du logiciel (voir §8).

### Transfert à l'étranger (art. 47, 51, 52) — RETRIEVED

- **Art. 47** : consentement de la personne concernée pour le transfert.
- **Art. 51** : protection adéquate exigée ; l'INPDP publie une liste des États
  jugés adéquats.
- **Art. 52** : l'**autorisation préalable de l'INPDP est obligatoire dans tous
  les cas** (instruction de la demande sous un mois).
- Source : loi organique n° 2004-63 du 27 juillet 2004 (art. 47, 51, 52),
  legislation-securite.tn / INS (RETRIEVED 2026-11-17).

**Conséquence pour AESTHÉA:** le transport du paquet `.aesthea` vers un cloud
étranger (iCloud Drive, Drive, kDrive, Proton…) constitue un transfert au sens
de l'art. 52. [JUDGED — le paquet est chiffré côté client, mais le praticien
peut le déchiffrer ; l'administration peut considérer que ce reste des données
personnelles.] Le praticien doit vérifier l'adéquation du pays et obtenir
l'autorisation INPDP ; l'option « zéro transfert » reste le stockage local
(appareil + clé USB).

## 2. Dossier médical et secret professionnel (Tunisie) — RETRIEVED

- **Code de déontologie médicale tunisien** (RETRIEVED) :
  - tout document médical doit porter le nom du médecin signataire ;
  - secret professionnel étendu au dossier ;
  - le dossier ne se communique pas en dehors des cas prévus.
- **Concrètement dans AESTHÉA** : chaque acte porte le champ `medecin`, et le
  consentement par acte porte une `signature`. Le vault est celui du praticien
  signataire.
- **Secret médical et facturation** : une facture ne doit pas révéler la
  pathologie. AESTHÉA liste les actes par leur libellé de catalogue (ex.
  « injection de toxine botulique »), jamais par un diagnostic ; le libellé est
  paramétrable par le cabinet.
- **Rôles et secret (v0.4.0)** : l'art. 63 limite le traitement aux médecins et
  aux personnes soumises au secret professionnel. AESTHÉA va au-delà par
  construction : la matrice RBAC (`kernel/rbac.py`) ne donne ni les champs
  médicaux (antécédents, allergies, traitements, notes) ni les
  contre-indications ni les photos au rôle `secretaire`, et ni l'agenda, ni les
  consentements, ni les champs cliniques au rôle `comptable` — et le coffre de
  rôle est filtré **avant** chiffrement, donc ces données ne quittent pas le
  coffre du médecin. [JUDGED — interprétation ; le praticien reste responsable
  de l'habilitation de ses collaborateurs.]

## 3. MDR 2017/745 — HORS PÉRIMÈTRE (JUDGED, ancré)

- Un « dispositif médical » au sens de l'art. 2(1) du règlement (UE) 2017/745
  suppose une finalité médicale : diagnostic, prévention, traitement...
- Un logiciel de gestion de cabinet (agenda, facturation, rappels, aide-mémoire
  de dépistage sans conclusion automatique) n'établit aucune information
  destinée à une décision diagnostique ou thérapeutique : ce n'est pas un
  dispositif (orientation MDCG 2019-11).
- La frontière est tenue par ADR-5 : le module contre-indications n'émet
  jamais de conclusion. Si le produit calculait un diagnostic ou une décision
  thérapeutique, il basculerait dans le périmètre — interdit par construction.
- Clause non vérifiée : le texte exact de l'art. 2(1) MDR n'a pas été extrait
  (l'appel lexarium a renvoyé les considérants). L'ancrage MDCG 2019-11 est
  cité de mémoire de travail : à re-vérifier avant tout argumentaire commercial.

## 4. TVA tunisienne — RETRIEVED (source commerciale, à confirmer)

- Taux standard **19 %**, taux réduit **7 %**, exonérations pour services
  essentiels (source : lucapacioli.com.tn, 2026 — tier RETRIEVED faible).
- Les actes médicaux relèvent selon leur nature de l'exonération ou du taux
  standard ; la qualification acte par acte appartient au comptable.
- AESTHÉA applique le taux **paramétré par acte** (défauts 19/7/0), arrondi aux
  millimes, et produit le rapport mensuel par taux : l'outil calcule, le
  comptable tranche.
- **Devis et factures** : le devis est un acte commercial ; sa conversion en
  facture n'altère pas les totaux (mêmes lignes, mêmes taux).

## 5. Honoraires et conservation — RETRIEVED (à confirmer par le praticien)

- **Code de déontologie, art. 37** : une note d'honoraires détaillée doit
  pouvoir être remise sur demande (JUDGED, texte à relire in extenso).
- **Conservation comptable** : les documents comptables (factures, devis
  convertis, notes d'honoraires) se conservent en pratique **10 ans**
  (RETRIEVED, usage ; à confirmer par le comptable).
- AESTHÉA ne supprime rien automatiquement : les factures et devis sont
  conservés dans le vault ; la suppression est un acte manuel, tracé au journal
  d'audit.

## 6. HIPAA — non applicable juridiquement, principes adoptés

- HIPAA est une loi américaine sans effet en Tunisie (JUDGED).
- Les garanties techniques équivalentes sont néanmoins appliquées : chiffrement
  au repos (AES-256-GCM), clé locale non exportable, journal d'audit
  hash-chaîné, aucun plaintext de santé hors de l'appareil, accès par phrase
  secrète, verrouillage automatique. C'est la lecture « HIPAA-grade » sans la
  juridiction.

## 7. Télé-déclaration des factures (TTN) — tension documentée

- Le dispositif tunisien de télé-déclaration des factures par identifiant
  **TTN** existe (RETRIEVED, usage). Un cabinet assujetti doit en principe
  déclarer ses factures le jour même via l'administration fiscale.
- **Tension avec l'architecture** : AESTHÉA est sans serveur ; la
  télé-déclaration est un acte d'envoi vers l'administration. Le logiciel ne
  peut ni la réaliser (pas de serveur, pas de canal vers l'administration), ni
  la feindre.
- **Ce que fait le logiciel** : il porte l'identifiant TTN du cabinet
  (`cabinet_legal.ttn`) sur les factures imprimées, et ne bloque pas la
  saisie. **Ce qu'il ne fait pas** : l'envoi effectif à l'administration — il
  reste un acte du cabinet (export/impression puis télédéclaration). À documenter
  clairement au moment de la vente.

## 8. Ce qui manque encore (honnête)

- La checklist de déclaration INPDP pour le praticien (livrable commercial).
- La vérification des textes exacts : MDR art. 2(1), MDCG 2019-11, art. 37 du
  code de déontologie, durée légale de conservation.
- La qualification TVA acte par acte avec un comptable tunisien.
- L'intégration effective de la télé-déclaration TTN (hors architecture
  sans serveur ; §7).
- Rétention/rotation des photos patient (prises en charge, pas de politique
  automatique).

# INPDP — Dossier d'accompagnement du praticien (loi organique n° 2004-63)

**Date : 2026-11-20 · Version : v1.0.0 · Destinataire : le praticien, responsable du traitement**

---

## Avertissement liminaire

Ce document est un **squelette de dossier** mis à la disposition du praticien
par l'éditeur du logiciel AESTHÉA. Il ne constitue pas un conseil juridique et
ne dispense en rien le praticien de ses déclarations et demandes
d'autorisation auprès de l'INPDP, dont il est **seul responsable**. Les
références citées ci-après sont celles documentées dans
`REGULATORY.md` (§1 et §2) ; aucun article de loi n'est cité au-delà.
Tout élément incertain est marqué [À VÉRIFIER PAR UN JURISTE].

**Rappel de contexte** : AESTHÉA est un logiciel hors-ligne ; le praticien
traite ses propres données sur son propre appareil (dossier médical de son
cabinet) et reste seul responsable de traitement. L'éditeur ne reçoit, ne
traite et n'héberge aucune donnée de santé (clause « zéro donnée », `CGU.md`
art. 8).

## 1. Ce que le praticien doit déclarer

Le traitement de **données de santé à caractère personnel** mis en œuvre par le
cabinet est soumis à :

1. **Déclaration** auprès de l'INPDP ;
2. **Autorisation préalable** pour le traitement de données de santé, exigée
   par les **art. 7 et 14 de la loi organique n° 2004-63 du 27 juillet 2004**,
   dans les conditions fixées par le **décret n° 2007-3004 du
   27 novembre 2007** et précisées par la **délibération INPDP n° 4 du
   5 septembre 2018** (traitement des données de santé).
   (Références : `REGULATORY.md` §1.)

3. Respect de l'**art. 63 de la loi n° 2004-63** : le traitement des données
   de santé ne peut être mis en œuvre que par des médecins ou des personnes
   soumises au secret professionnel. Concrètement, dans AESTHÉA, la matrice
   de rôles limite l'accès : le secrétaire n'accède jamais aux champs
   médicaux, le comptable jamais aux éléments cliniques — le praticien reste
   responsable de l'habilitation de ses collaborateurs
   (`REGULATORY.md` §2).

## 2. Quand l'autorisation est requise

- **Tout traitement de données de santé** est soumis à déclaration et
  **autorisation préalable** (art. 7 et 14, loi n° 2004-63), selon les
  conditions du décret n° 2007-3004 et de la délibération INPDP n° 4 du
  5 septembre 2018.
- Le cabinet qui informatise son dossier patient avec AESTHÉA entre dans ce
  cadre dès qu'il traite des données de santé de patients (antécédents,
  allergies, traitements, notes, actes, photos).
- En cas de doute sur l'exigibilité (nature du traitement, conditions du
  décret), le praticien consulte l'INPDP ou un juriste.
  [À VÉRIFIER PAR UN JURISTE — les conditions exactes d'exigibilité fixées par
  le décret n° 2007-3004 n'ont pas été vérifiées in extenso ; se référer au
  texte et à la pratique de l'INPDP.]

## 3. Fiche de registre des traitements — modèle à remplir

Le praticien complète une fiche par traitement. Modèle :

| Rubrique | À remplir par le praticien |
|---|---|
| **Responsable du traitement** | Dr [NOM], cabinet [RAISON SOCIALE], [ADRESSE], matricule fiscal [N°], téléphone [TÉL] |
| **Désignation du traitement** | Gestion du dossier patient d'un cabinet médico-esthétique : rendez-vous, actes avec traçabilité des lots, consentements, facturation, rappels post-acte, stock |
| **Finalité** | Suivi médical et organisation du cabinet ; facturation des actes ; traçabilité des produits injectables ; respect du consentement éclairé |
| **Catégories de données** | Données de santé (antécédents, allergies, traitements, notes cliniques, protocoles, photos) ; identité et coordonnées ; données financières (factures, devis) |
| **Personnes concernées** | Patients du cabinet |
| **Destinataires** | Aucun, sauf collaborateurs habilités soumis au secret professionnel (art. 63, loi n° 2004-63) |
| **Durée de conservation** | [À DÉFINIR — voir `REGULATORY.md` §5 : conservation comptable en pratique 10 ans, à confirmer par le comptable] |
| **Mesures de sécurité** | Chiffrement local AES-256-GCM (clé dérivée de la phrase secrète, jamais transmise) ; accès par phrase secrète ; verrouillage automatique ; RBAC trois rôles ; journal d'audit local hash-chaîné ; sauvegardes par paquet `.aesthea` chiffré (manifeste SHA-256) sur support choisi par le praticien |
| **Transferts hors de Tunisie** | **Aucun** (option « zéro transfert » : appareil + clé USB). Si transport cloud choisi : voir §7 ci-après |
| **Déclaration / autorisation INPDP** | [N° / date de la déclaration], [N° / date de l'autorisation] |

## 4. Consentement des patients — mécanisme géré par le Logiciel

Le Logiciel gère le **consentement éclairé par acte** : consentement daté,
portant signature, lié à l'acte pratiqué, ainsi que les consentements
photos/données personnelles datés. Le praticien :

1. recueille le consentement **libre et éclairé** du patient avant chaque acte
   concerné (information délivrée par le médecin) ;
2. enregistre le consentement dans le Logiciel (traçable dans le coffre et le
   paquet `.aesthea`) ;
3. reste seul responsable de la licéité des consentements ; le Logiciel
   fournit le mécanisme, pas la décision (`CGU.md` art. 7.3).

## 5. Dossier médical et secret professionnel (rappel)

Conformément au Code de déontologie médicale tunisien (voir
`REGULATORY.md` §2) : tout document médical porte le nom du médecin
signataire ; le secret professionnel s'étend au dossier ; le dossier ne se
communique pas en dehors des cas prévus. Dans AESTHÉA : chaque acte porte le
champ `medecin`, le consentement par acte porte une `signature`, et la
facturation n'expose jamais un diagnostic (libellés de catalogue
paramétrables).

## 6. Checklist du dossier INPDP à constituer

- [ ] Fiche(s) de registre des traitements (modèle §3) complétée(s)
- [ ] Déclaration du traitement déposée à l'INPDP
- [ ] Demande d'**autorisation préalable** (traitement de données de santé)
      déposée — art. 7 et 14, loi n° 2004-63 ; décret n° 2007-3004 ;
      délibération INPDP n° 4 du 5 septembre 2018
- [ ] Le cas échéant : demande d'autorisation de **transfert** (art. 52) si un
      transport cloud étranger est utilisé (§7)
- [ ] Engagement de confidentialité signé par chaque collaborateur habilité
      (secret professionnel, art. 63)
- [ ] Modèle de consentement patient (par acte, photos/données personnelles)
- [ ] Copies des accusés de réception / autorisations INPDP, archivées

## 7. Cas du transport cloud (art. 47, 51, 52 de la loi n° 2004-63)

**Situation.** AESTHÉA n'émet aucun appel réseau. Si le praticien choisit
lui-même de transporter son paquet `.aesthea` chiffré vers un cloud étranger
(iCloud Drive, Google Drive, kDrive, Proton Drive…) via son propre client
cloud, ce transport constitue un transfert au sens de la loi n° 2004-63
(`REGULATORY.md` §1 : le paquet est chiffré côté client, mais le
praticien peut le déchiffrer ; l'administration peut considérer qu'il s'agit
de données personnelles [JUDGED — à confirmer]).

**Obligations du praticien dans ce cas :**

| Condition | Base légale | Action |
|---|---|---|
| Consentement de la personne concernée | art. 47 | consentement des patients au transfert |
| Protection adéquate du pays de destination | art. 51 | vérifier la liste des États jugés adéquats publiée par l'INPDP |
| Autorisation préalable de l'INPDP | art. 52 | **obligatoire dans tous les cas** (instruction de la demande sous un mois) |

**Option « zéro transfert » (recommandée par défaut)** : stockage local
(appareil + clé USB), sans cloud — dispense des formalités de transfert.

[À VÉRIFIER PAR UN JURISTE — la qualification d'un paquet chiffré transporté
par le praticien lui-même comme « transfert » au sens de l'art. 52 relève de
l'appréciation de l'INPDP ; l'interprétation ci-dessus est issue de
`REGULATORY.md` §1, étiquetée JUDGED.]

## 8. Références

Toutes les références citées dans le présent document proviennent de
`REGULATORY.md` (§1 et §2) : loi organique n° 2004-63 du 27 juillet 2004
(art. 7, 14, 47, 51, 52, 63) ; décret n° 2007-3004 du 27 novembre 2007 ;
délibération INPDP n° 4 du 5 septembre 2018 ; Code de déontologie médicale
tunisien. Aucune autre disposition n'est invoquée. Les textes intégraux et la
pratique de l'INPDP font foi ; à faire vérifier par un juriste avant dépôt.

---

*Squelette destiné au praticien, fourni par l'éditeur à titre d'accompagnement
commercial et documentaire — sans valeur de conseil juridique.*

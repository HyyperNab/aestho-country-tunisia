# AESTHÉA — Politique de confidentialité du logiciel

**Date : 2026-11-20 · Version : v1.0.0**

---

## 1. Objet

La présente politique décrit la manière dont le logiciel AESTHÉA (ci-après le
« Logiciel ») traite — ou, plus exactement, **ne transmet pas** — les données
de ses utilisateurs.

Elle s'adresse au praticien (médecin esthétique, chirurgien esthétique,
dermatologue) et, par transparence, à ses patients. Elle complète les
Conditions Générales d'Utilisation (`CGU.md`), la licence (`LICENSE.md`) et le
dossier réglementaire (`INPDP.md`, `REGULATORY.md`).

Le principe fondateur du Logiciel est la **souveraineté locale** : les données
restent sur l'appareil du praticien. L'éditeur
[PLACEHOLDER — dénomination sociale de l'éditeur] n'exploite aucun serveur
applicatif, ne reçoit aucune donnée et n'en voit aucune.

## 2. Qui traite les données ?

**Le praticien, et lui seul.** Le praticien est le responsable du traitement
des données de ses patients au sens de la loi organique n° 2004-63 du
27 juillet 2004 (protection des données à caractère personnel). Les formalités
INPDP lui incombent (déclaration et autorisation préalable pour les données de
santé — art. 7 et 14 ; décret n° 2007-3004 du 27 novembre 2007 ; délibération
INPDP n° 4 du 5 septembre 2018 ; voir `REGULATORY.md` §1).

**L'éditeur ne traite rien.** Il n'est ni responsable de traitement, ni
sous-traitant, ni hébergeur de données de santé. [À VÉRIFIER PAR UN JURISTE —
qualification à confirmer.]

## 3. Quelles données existent dans le Logiciel ?

Le Logiciel gère, **sur l'appareil du praticien**, les catégories de données
suivantes :

| Catégorie | Contenu indicatif |
|---|---|
| Dossier patient | identité, contact, antécédents, allergies, traitements en cours, notes |
| Actes | patient, type d'acte, date, médecin, protocole, notes cliniques, lots consommés, suivi |
| Rendez-vous | patient, date, heure, durée, motif, statut |
| Factures / devis | numéro, patient, lignes d'actes, totaux HT/TVA/TTC, paiements, statuts |
| Lots (stock injectables) | produit, n° de lot, fournisseur, expiration, quantité, seuil |
| Consentements | type (acte / photos / données personnelles / newsletter), accord, date, version, signature |
| Rappels | échéances calculées post-acte |
| Photos (avant/après) | images chiffrées dans le coffre (JPEG/PNG, ≤ 5 Mo) |
| Journal d'audit local | horodatage + événement + empreinte SHA-256 (maillon hash-chaîné) |
| Identité du cabinet | nom, matricule fiscal, adresse, téléphone, email, identifiant TTN |

## 4. Où sont les données ?

**Exclusivement en local, chiffrées.** Toutes les données sont stockées sur
l'appareil du praticien, dans le stockage local du navigateur (IndexedDB),
chiffrées **AES-256-GCM** avec une clé dérivée de la phrase secrète du
praticien (PBKDF2-SHA256, 600 000 itérations, clé non exportable). Le
chiffrement s'applique au repos comme au paquet de synchronisation.

- La **phrase secrète ne quitte jamais l'appareil**. Sans elle, les données
  sont irrécupérables — y compris pour l'éditeur, qui ne dispose d'aucun
  moyen de déchiffrement ni de récupération.
- Les **sauvegardes / synchronisation** se font par paquet `.aesthea` chiffré
  (manifeste d'intégrité SHA-256), exporté vers un support choisi par le
  praticien : disque local, clé USB, ou « dossier synchronisé » mirroiré par
  le **propre client cloud du praticien** (kDrive, Nextcloud…) via la File
  System Access API — sans aucun compte, OAuth ou serveur de l'éditeur.
- Le journal d'audit est local (navigateur ; noyau CLI), hash-chaîné, et ne
  contient jamais de donnée de santé en clair.

## 5. Ce que l'éditeur ne voit pas

Par construction, l'éditeur n'a accès à **rien** :

- il ne voit, ne reçoit, ne collecte, ne stocke, ne traite et n'héberge
  **aucune donnée de patient**, aucune donnée du cabinet, aucune photo,
  aucune facture ;
- il ne connaît ni la phrase secrète, ni les phrases de rôle, ni le contenu
  des coffres ;
- il ne peut ni lire, ni restaurer, ni supprimer les données du praticien ;
- le Logiciel ne comporte **aucun compte utilisateur**, aucune
  authentification serveur, aucun canal de remontée.

## 6. Cookies et traceurs

**Aucun.** Le Logiciel n'utilise aucun cookie, aucun traceur, aucune
empreinte d'appareil, aucune publicité.

## 7. Métadonnées techniques de distribution

**Néant à ce jour.** Le Logiciel n'appelle **aucun serveur** pendant son
utilisation : pas de télémétrie, pas de vérification de licence en ligne, pas
de mise à jour automatique, pas d'API. Le fichier de l'application (PWA
monofichier) peut être distribué par hébergement statique ; à la date du
présent document, aucun canal de distribution n'exploite de journaux de
données personnelles. Si un canal de distribution est mis en service, la
présente politique sera mise à jour pour décrire les éventuelles métadonnées
techniques de téléchargement (ex. journaux d'accès de l'hébergeur statique),
sans jamais couvrir de données de santé — qui ne transitent en aucun cas.
Voir `MENTIONS_LEGALES.md` §3.

## 8. Transport cloud choisi par le praticien

Si le praticien choisit de transporter son paquet `.aesthea` chiffré via un
cloud étranger, ce choix lui appartient. Il constitue un transfert au sens de
la loi n° 2004-63 (art. 47 : consentement ; art. 51 : protection adéquate ;
art. 52 : autorisation préalable de l'INPDP obligatoire dans tous les cas) —
voir `REGULATORY.md` §1 et `INPDP.md` §7. L'option « zéro transfert »
(stockage local + clé USB) reste recommandée par défaut. L'éditeur n'est
jamais partie à ce transport.

## 9. Droits des personnes concernées (patients)

Les patients exercent leurs droits (information, consentement, accès,
rectification…) **directement auprès du praticien**, responsable du traitement.
L'éditeur, qui ne détient aucune donnée, ne peut donner suite à aucune demande
de ce type. Le Logiciel fournit au praticien les mécanismes utiles
(consentement daté et signé par acte, dossier patient, journal d'audit).

## 10. Sécurité et responsabilités

- Sécurité technique : chiffrement AES-256-GCM, clé non exportable,
  verrouillage automatique du Logiciel, matrice de rôles restrictive (RBAC :
  médecin-chef / secrétaire / comptable), journal d'audit hash-chaîné,
  contrôle d'intégrité des paquets (SHA-256).
- Responsabilités du praticien : confidentialité de la phrase secrète et des
  phrases de rôle, sauvegardes régulières du paquet `.aesthea`, sécurité des
  appareils, habilitation des collaborateurs (voir `CGU.md` art. 6 et 7).

## 11. Contact

Pour toute question relative à la présente politique :
[PLACEHOLDER — adresse de contact de l'éditeur].

---

*Modèle à compléter (placeholders) et à faire relire par un juriste. Les
références citées renvoient à `REGULATORY.md` ; aucun élément n'excède
ce qui y est documenté.*

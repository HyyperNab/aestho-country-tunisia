# TARIFS — recherche prix (Tunisie) et méthodologie de grille

## 1. Ce que la recherche a trouvé (RETRIEVED 2026-11-20)

**Le marché tunisien ne publie pas de grille complète.** La recherche du
25/11/2026 trouve des fourchettes en TND pour une partie des actes (Botox, HA,
skinbooster, Sculptra, PRP, laser, HIFU, microneedling, cryolipolyse) ; le reste
reste sur devis. Détail des sources : `docs/PRIX_MARCHE_TN.md`.

- [drbouricha.com/tarifs-medecine-esthetique-tunisie](https://www.drbouricha.com/tarifs-medecine-esthetique-tunisie/) :
  « aucun tarif n'est fixé à l'avance : chaque prix est déterminé après une
  évaluation personnalisée » — et la FAQ l'explique : « Afficher un tarif fixe
  donnerait une information imprécise, potentiellement trompeuse ».
- Tavily (brut) + Perplexity (ask + research, triple passe 2026-11-20) : aucune
  fourchette TND publiée par acte ; les cabinets pratiquent le **devis après
  consultation** (Medi'Go, Dr Bouricha, Medespoir, Dr Zarrouk…).
- **Seul datapoint publié** : HA 200 €/seringue 1 ml
  (dr-chiraz-bouzguenda.fr — en EUROS, cible tourisme médical ; pas un tarif
  TND de cabinet). Consultation d'évaluation = devis gratuit (drbouricha.com).
- Les prix en euros des sites de tourisme médical ne sont **pas** des tarifs de
  cabinet tunisien (ne pas les transposer).

**Conséquence d'ingénierie** : le catalogue préremplit une **médiane
indicative** pour les 20 actes sourcés (dont les protocoles à appareil de
rezervy.io), avec badge « indicatif », `min`/`max`, source et date. Les autres
actes restent à 0 — **aucun prix inventé**. Le praticien vérifie et modifie
chaque valeur ; un prix modifié perd le badge. Les coffres existants peuvent
appliquer les repères aux actes à 0 via un bouton explicite. La tarification
finale reste une décision du cabinet.

**Source unique (anti-SPOF)** : `data/prix_marche.json`. Avant cette
correction, les repères étaient dupliqués : 15 côtés noyau
(`kernel/catalogue.py`), 20 côté PWA (`src/js/00_prelude.js`) — dérive réelle
mesurée. Désormais le noyau **lit** ce JSON et `scripts/gen_prices.py` en génère
le miroir `PRIX_MARCHE` dans le préambule JS. `verify.sh` et la CI exécutent
`gen_prices.py --check` : toute édition manuelle d'un bloc généré échoue.

**Aucune transposition de devise** : aucun prix AED/SAR/EGP/MAD n'a été publié
de façon vérifiable (Perplexity, 26/11/2026 : `UNVERIFIED`). Les taux réels
(`docs/DEVISES.md`) servent uniquement à lire un prix TND dans une autre
devise ; convertir un prix tunisien n'en fait pas un prix de marché local.

## 2. Ce qui fait varier le prix (facteurs du marché, RETRIEVED)

1. **L'acte** (technique) et sa **zone** (lèvres ≠ sillons ≠ ovale).
2. **La quantité de produit** (UI de toxine, ml de HA, nombre de fils,
   séances de laser).
3. **Le nombre de séances** (protocoles énergie : 3-6 séances).
4. La **marque du produit** (RCP + prix d'achat du consommable).
5. L'**objectif** du patient (prévention vs correction).

## 3. Méthodologie de grille (à exécuter par le cabinet)

1. **Coût consommable** par unité : toxine (prix d'achat/UI), HA (prix/ml),
   fils (prix/fil), séances machine (amortissement + maintenance). Ces prix
   d'achat fournisseur ne sont pas publiés en TND : ils restent à saisir. Le
   repère indicatif porte sur le prix de l'acte, pas sur le coût matière.
2. **Marge cible par acte** (le cabinet décide ; la structure de coût d'AESTHÉA
   est zéro serveur/zéro abonnement — voir PRODUIT.md §4).
3. **Unité de facturation** par acte = champ `unite` du catalogue
   (`zone`, `ml`, `UI`, `fil`, `seance`) — le devis quantifie dans cette unité.
4. **TVA** : `tva_rate` par acte, modifiable. Par défaut 0 (soins médicaux) —
   le taux applicable aux actes purement esthétiques doit être confirmé par le
   comptable [À CONFIRMER] (REGULATORY.md §4).
5. **Enregistrement** : Réglages → catalogue — chaque acte reçoit prix HT + TVA ;
   le devis et la facture s'appuient sur ces valeurs.

## 4. Ce que le logiciel fournit déjà

- Catalogue 38 actes avec **zone / technique / consommable / unité / suivi
  post-acte / sources cliniques** (PMID ancrés, sinon CONVENTION/RCP).
- Devis détaillé par acte + conversion devis → facture + encaissements partiels.
- Suivi post-acte automatique par chaîne de checkpoints (ex. toxine J+10 puis
  J+120 ; HA J+30 puis J+180).

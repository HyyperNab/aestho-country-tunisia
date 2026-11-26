# Prix du marché tunisien — état documenté (26 novembre 2026)

## Verdict

**Il n'existe pas de grille tarifaire complète et officielle en dinars pour la
médecine esthétique en Tunisie.** Les recherches des 25 et 26 novembre 2026
(Tavily + Perplexity, pages publiques) trouvent des **fourchettes en TND** pour
20 des 50 actes du catalogue : Botox, acide hyaluronique, skinbooster, Sculptra,
PRP, laser épilation, HIFU, microneedling, cryolipolyse, soin du visage, peeling
superficiel et protocoles à appareil (hydradermabrasion, radiofréquence, LED).
**Les 30 autres actes restent explicitement « NON PUBLIÉ — devis »** : aucun
prix n'est inventé pour combler la case vide.

AESTHÉA distingue donc deux choses :

1. **Repères indicatifs** — médianes de fourchettes publiques, préremplies pour
   les actes concernés, marquées « indicatif » dans le catalogue.
2. **Prix réels du cabinet** — saisis ou importés par le praticien, seuls
   utilisables pour facturer. Les repères ne sont ni un devis, ni un tarif
   officiel, ni un prix de vente conseillé.

## Sources publiques utilisées (TND)

| Acte / produit | Fourchette publique | Source | Date |
|---|---|---|---|
| Toxine botulique (zone) | 50–550 DT selon produit | anismrabet.com — page Botox | 2026-11-25 |
| Acide hyaluronique (seringue 1 ml) | 450–750 DT (classique) ; 700–1200 DT (Restylane) | medtco.com — comparatif injectables | 2026-11-25 |
| Skinbooster (séance) | 400–700 DT | medtco.com — comparatif injectables | 2026-11-25 |
| Sculptra / biostimulant (séance) | 1000–1500 DT | medtco.com — comparatif injectables | 2026-11-25 |
| PRP (séance) | 300–1000 DT | drbouricha.com (500–1000) + offre locale 300 | 2026-11-25 |
| Épilation laser (zone) | 59–189 DT | vivencia.tn — grille par zone | 2026-11-25 |
| HIFU (zone / visage) | 465–1800 DT | vivencia.tn + organicaclinic.net | 2026-11-25 |
| Microneedling (séance) | 150–300 DT | tunestetic.com + offres locales | 2026-11-25 |
| Cryolipolyse (zone) | 150–400 DT | offres locales Tunisie | 2026-11-25 |
| Soin du visage / nettoyage de peau | 50–120 DT | [rezervy.io — guide prix beauté Tunisie](https://rezervy.io/blog/guide-prix-beaute-tunisie) | 2026-08-04 |
| Peeling superficiel | 100–250 DT | [rezervy.io — guide prix beauté Tunisie](https://rezervy.io/blog/guide-prix-beaute-tunisie) | 2026-08-04 |
| Hydradermabrasion / radiofréquence / LED (protocoles à appareil) | 120–350 DT la séance | [rezervy.io — guide prix beauté Tunisie](https://rezervy.io/blog/guide-prix-beaute-tunisie) | 2026-08-04 |

La source rezervy.io annonce explicitement ses montants en dinars tunisiens et
donne la fourchette groupée « hydradermabrasion, peeling, radiofréquence, LED :
120 à 350 DT la séance ». Elle est reprise telle quelle, avec sa date de
publication, pour chacun de ces quatre codes ; la borne médiane (235 DT) n'est
qu'un repère de départ, pas un prix constaté en cabinet.

### Sources écartées (absence maintenue)

- [centrelaer.com/tarifs](https://centrelaer.com/tarifs) (Tunis) : la page
  affiche des intitulés (« Radiofréquence », « Rajeunissement facial »,
  « Détatouage », « Épilation ») mais **aucun chiffre DT n'est extractible** du
  contenu publié. Aucun montant n'a donc été transposé.
- [servihealth-tunisie.com](https://servihealth-tunisie.com/intervention/medecine-esthetique/fils-tenseurs-tunisie)
  (fils tenseurs) et [tunisie-esthetic.com](https://eng.tunisie-esthetic.com/microneedling-tunisie.html)
  (microneedling) : prix en **euros uniquement**.
- clinique-ml.com, clinique-medespoir-tunisie.com, visagestunisie.com,
  docteur-mellouli.com : « devis », « prix communiqué sur demande », ou aucune
  valeur numérique.

Les sites de tourisme médical publient aussi des prix en **euros** (Botox
120–400 €, HA 200–400 €/seringue, PRP 100–350 €, fils 150 €/fil). Ils ne sont
**pas** transposés en TND : la clientèle, le forfait séjour et la marge ne sont
pas ceux d'un cabinet tunisien.

## Ce qui reste non publié

Les 30 codes sans repère vérifié restent à 0 avec le badge
« NON PUBLIÉ — devis » et une explication au survol : lipolyse injectable,
microtoxine, mésothérapie, polynucléotides, peelings moyen/profond/
dépigmentant/Jessner/PRX-T33, fils lisses/crantés/PCL, lasers vasculaire/
pigmentaire/fractionné/non ablatif/picoseconde/détatouage, IPL, RF micro-aiguilles,
carboxythérapie, dermabrasion, micropigmentation, exosomes, HIFEM-EMS, TECAR,
plasma fibroblaste, mésothérapie capillaire, traitements cellulite et vergetures.

- **Prix d'achat fournisseur / coût matière** (flacon de toxine, seringue de HA,
  kit PRP, fils, solutions de peeling, consommables laser) : aucune grille
  publique en TND trouvée. Le champ « coût matière » du catalogue reste donc à
  saisir par le praticien ; c'est lui qui alimente la marge, pas le repère de
  prix de l'acte.
- **Remises, forfaits, cures multi-séances** : non publiés ; à définir par le
  cabinet.

## Décision d'ingénierie

1. **Préremplir seulement ce qui est sourcé.** Les actes couverts reçoivent la
   médiane de la fourchette, avec `min`, `max`, source et date stockés.
2. **Marquer l'incertitude.** Badge « indicatif », note visible, titre au survol
   avec la fourchette et la source. Un prix modifié par le praticien perd le
   badge.
3. **Bouton explicite pour les coffres existants** : « Appliquer les repères aux
   actes à 0 » — jamais automatique, jamais sur un prix déjà saisi.
4. **Rendre l'absence visible, pas la masquer.** Un acte sans tarif publié porte
   « NON PUBLIÉ — devis » avec le motif au survol ; le champ reste éditable dans
   la fiche acte et via l'import du barème fournisseur.
5. **Le praticien reste l'autorité.** Les repères aident à démarrer ; ils ne
   remplacent ni son barème, ni le devis, ni la validation comptable de la TVA.

## Mise à jour

Toute nouvelle fourchette publique doit être ajoutée avec sa source, sa date et
son périmètre exact (zone, séance, seringue). Le moteur d'import fournisseur
reste la voie recommandée pour les prix réels : chaque ligne est proposée,
confirmée, puis historisée avec l'empreinte du document.

# MOTEUR DE RISQUE & AUDIT FISCAL — spécification (2026-11-25)

## Moteur de risque (logique velion)
Verdicts **PROCEED / CONDITIONAL / STOP** (analogue DECLINE/PROCEED/ESCALATE).
Cotes multiplicatives déterministes (LLM-free) : base par catégorie d'acte ×
facteurs déclarés (tabac ×1.6, auto-immun ×2.0, herpès récidivant ×1.8,
anticoagulants ×1.5, diabète ×1.4, chéloïdes ×1.7, immunosuppresseurs ×2.2,
photosensibilisants ×1.6). Absolus → STOP : grossesse, allergie anesthésiques
locaux, cardiopathie/stimulateur (énergie). ≥2 facteurs ou prob ≥ 10 % →
CONDITIONAL avec conseils. **Les cotes sont des PRIORS JUDGÉS** (ordres de
grandeur cliniques, pas des mesures) — le médecin reste l'autorité finale et
sa décision est enregistrée (audit `risque_decision_medecin`).

## Audit fiscal (praticien + comptable)
`kernel/finance_audit.py::pre_audit()` détecte avant contrôle : facture sans
acte, acte jamais facturé, HT/TVA incohérents avec les actes, paiement > TTC,
« payée » incomplète, numéros en doublon, taux TVA hors barème tunisien
(0/7/13/19), dates hors exercice. `export_fiscal()` produit le dossier
imprimable (synthèse, TVA par taux, anomalies, journal des factures) pour le
service des finances. Accès : medecin_ceo + comptable (nav Analyse).

## Signalement (Mentions)
Formulaire problème/bug/besoin : rapport enregistré chiffré localement
(settings.rapports) + email pré-rempli (mailto:) — **aucun envoi automatique,
aucun serveur central** (un serveur = SPOF + egress ; le sceau humain reste).

## Audit RBAC (2026-11-25)
Matrice vérifiée : dossier médical complet (impression/export) réservé au
médecin (canField patient.antecedents) ; analyse/audit fiscal réservés
medecin_ceo+comptable ; risque/dépistage réservés au médecin (read contra) ;
secrétaire : agenda/factures/patients sans champ médical ; comptable :
factures+analyse sans données cliniques. Vaults scindés par rôle AVANT
chiffrement (vérifié par sondes at-rest).

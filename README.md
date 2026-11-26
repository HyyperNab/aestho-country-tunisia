# AESTHÉA — country pack: Tunisia (TN)

This repository is one interchangeable country module for AESTHÉA. It carries
everything that changes when the market changes: currency, tax, market price
benchmarks, legal references and practice rules. The application core carries
none of these values.

## Contract

| File | Role |
|---|---|
| `pack.json` | identity, status, locale, timezone, currency code |
| `currency.json` | accounting currency, symbol, decimals, rounding |
| `tax.json` | tax system, rates, invoice fields, declaration channel |
| `prices.json` | indicative market benchmarks, with source and date per row |
| `legal.json` | machine-readable legal anchors (data protection, secrecy, retention) |
| `medical.json` | consent validity, signature rules, country-specific practice limits |
| `legal/` | human-readable legal and market source documents |

The core validates this pack against `aesthea-country/1`. A pack with
`"status": "draft"` is refused at build and at runtime unless the operator
explicitly allows drafts. Missing data stays missing: no value is inferred.

## Status

`verified` — 2026-11-26.

Verified scope is the Tunisian market only. The legal references and their
limits are in `legal/REGULATORY.md`; price provenance and limits are in
`legal/PRIX_MARCHE_TN.md`. Anything not anchored there is not claimed here.

## What this pack deliberately does not do

- It does not invent prices, tax rates or legal articles.
- It does not encode a medical diagnosis or a therapeutic decision.
- It does not claim that a draft market is launch-ready.

## Adding a market

Copy this repository, keep the same file names, set `status: "draft"`, and fill
only what is sourced. The core can then be built with
`AESTHEA_COUNTRY=<code>`. Draft packs fail closed until verification.

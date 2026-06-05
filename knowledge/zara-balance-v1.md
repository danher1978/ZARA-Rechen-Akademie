# ZARA Balance-Bibliothek V1
**XP-System, Boss-Schwellen, Drop-Rates für ZARA v2.0+**

Version: 1.0
Datum: März 2026

---

## 🔖 KNOWLEDGE FILE META

```yaml
KNOWLEDGE_FILE_META:
  knowledge_id: "ZARA_BALANCE_V1"
  type: "configuration"
  version: "1.0"
  datum: "März 2026"
  kompatibel_mit: "ZARA v2.0+"

  provides:
    - "xp_tabelle"
    - "rang_schwellen"
    - "boss_tier_tabelle"
    - "drop_rates"
    - "xp_verlust_regeln"

  fallback:
    wenn_nicht_geladen: "ZARA verwendet Basis-Werte aus Haupt-Prompt"
```

---

## XP-Vergabe (Basis — ohne Equipment-Boni)

```yaml
xp_basis:
  richtige_antwort:
    versuch_1: 10
    versuch_2: 7
    versuch_3: 5
    ausdauer_stufe_3: 5       # Zusatz-XP für Durchhalten bis Stufe 3

  falsche_antwort: -3         # Minimum XP = 0, nie negativ

  boss_sieg:
    tier_1: 60
    tier_2: 90
    tier_3: 130
    tier_4: 180
    tier_5: 250

  boss_niederlage:
    tier_1: 25
    tier_2: 35
    tier_3: 50
    tier_4: 70
    tier_5: 100

  boss_beschwoerung_multiplikator:
    standard:  1.5            # Boss-Tier +1
    legendaer: 2.0            # Boss-Tier +2

xp_boost_berechnung:
  formel: "basis_xp × (1 + xp_boost_prozent / 100)"
  runden: "auf ganze Zahl, kaufmännisch"
  gilt_fuer: ["richtige_antwort", "boss_sieg"]
  gilt_nicht_fuer: ["xp_verlust", "boss_niederlage"]

kampf_xp_boost:
  beschreibung: "Gilt nur für Boss-Kampf-Aufgaben (nicht Boss-Sieg-Bonus)"
  stack_mit_globalem_boost: true
```

---

## Rang-Tabelle

```yaml
raenge:
  1:
    name: "Rechenanfänger"
    symbol: "⭐"
    xp_fuer_diesen_rang: 0
    gesamt_xp: 0
    boss_tier: 1

  2:
    name: "Zahlen-Lehrling"
    symbol: "📖"
    xp_fuer_diesen_rang: 200
    gesamt_xp: 200
    boss_tier: 1

  3:
    name: "Rechen-Kämpfer"
    symbol: "⚔️"
    xp_fuer_diesen_rang: 400
    gesamt_xp: 600
    boss_tier: 2

  4:
    name: "Mathe-Ritter"
    symbol: "🛡️"
    xp_fuer_diesen_rang: 600
    gesamt_xp: 1200
    boss_tier: 2

  5:
    name: "Zahlen-Magier"
    symbol: "🔮"
    xp_fuer_diesen_rang: 900
    gesamt_xp: 2100
    boss_tier: 3

  6:
    name: "Mathewelt-Retter"
    symbol: "🌟"
    xp_fuer_diesen_rang: 1200
    gesamt_xp: 3300
    boss_tier: 3

  7:
    name: "Rechen-Champion"
    symbol: "🔱"
    xp_fuer_diesen_rang: 1600
    gesamt_xp: 4900
    boss_tier: 4

  8:
    name: "Zahlen-Meister"
    symbol: "💎"
    xp_fuer_diesen_rang: 2000
    gesamt_xp: 6900
    boss_tier: 4

  9:
    name: "Hüter der Mathewelt"
    symbol: "🌙"
    xp_fuer_diesen_rang: 2500
    gesamt_xp: 9400
    boss_tier: 5

  10:
    name: "Legendärer Rechenheld"
    symbol: "👑"
    xp_fuer_diesen_rang: 3000
    gesamt_xp: 12400
    boss_tier: 5
    prestige_verfuegbar: true
```

---

## Boss-Tier-Tabelle

```yaml
boss_tiers:
  tier_1:
    ab_rang: 1
    bis_rang: 2
    runden: 3
    aufgaben_niveau_bonus: 0      # +0 über aktuelles Kind-Niveau
    sieg_bedingung: "2 von 3 Runden"
    koerper_typ_pool: ["Bestie", "Kreatur", "Phantom"]
    titel_pool: ["der Lauernde", "des Chaos", "der Zerstörung"]

  tier_2:
    ab_rang: 3
    bis_rang: 4
    runden: 3
    aufgaben_niveau_bonus: 1
    sieg_bedingung: "2 von 3 Runden"
    koerper_typ_pool: ["Bestie", "Titan", "Phantom"]
    titel_pool: ["der Finsternis", "des Chaos", "der Zerstörung"]

  tier_3:
    ab_rang: 5
    bis_rang: 6
    runden: 4
    aufgaben_niveau_bonus: 1
    sieg_bedingung: "3 von 4 Runden"
    koerper_typ_pool: ["Titan", "Koloss", "Drache"]
    titel_pool: ["der Finsternis", "des Abgrunds", "der Leere"]

  tier_4:
    ab_rang: 7
    bis_rang: 8
    runden: 4
    aufgaben_niveau_bonus: 2
    sieg_bedingung: "3 von 4 Runden"
    koerper_typ_pool: ["Erzkoloss", "Urdrache", "Legendäre Bestie"]
    titel_pool: ["der Ewigkeit", "des Verderbens", "der Uralte"]

  tier_5:
    ab_rang: 9
    bis_rang: 10
    runden: 5
    aufgaben_niveau_bonus: 2
    sieg_bedingung: "3 von 5 Runden"
    koerper_typ_pool: ["Erzkoloss", "Urdrache", "Legendäre Bestie"]
    titel_pool: ["der Ewigkeit", "der Unbesiegliche", "des Uralten Verderbens"]
```

---

## Boss-Schwelle

```yaml
boss_schwelle:
  basis: 8                         # Aufgaben bis Boss ohne Equipment
  minimum: 3                       # Nie unter 3 durch Equipment-Boni
  berechnung: "8 - aktive_boni.boss_beschleuniger"
```

---

## Drop-Rates

```yaml
drop_rates:
  tier_1:
    gewoechnlich: 70
    selten: 25
    episch: 4
    legendaer: 1

  tier_2:
    gewoechnlich: 55
    selten: 35
    episch: 9
    legendaer: 1

  tier_3:
    gewoechnlich: 35
    selten: 40
    episch: 20
    legendaer: 5

  tier_4:
    gewoechnlich: 15
    selten: 40
    episch: 35
    legendaer: 10

  tier_5:
    gewoechnlich: 5
    selten: 30
    episch: 45
    legendaer: 20

  boss_beschwoerung_standard:      # Boss-Tier +1 temporär
    gewoechnlich: -15              # Delta auf Basis-Tier
    selten: +5
    episch: +8
    legendaer: +2

  boss_beschwoerung_legendaer:     # Boss-Tier +2 temporär
    gewoechnlich: -25
    selten: 0
    episch: +15
    legendaer: +10

hinweis: "Drop-Rates in Prozent. Bei Beschwörung: Delta auf aktuellen Tier addieren."
```

---

## Anzeige-Empfehlungen

```yaml
anzeige:
  rang_fortschritt_balken:
    zeichen_gesamt: 10
    gefuellt: "█"
    leer: "░"
    beispiel: "████░░░░░░ 40%"

  xp_anzeige:
    format: "[aktuelle XP] / [XP-Ziel] XP"
    beispiel: "340 / 600 XP"
```

---

*ZARA_BALANCE_V1 · Kompatibel mit ZARA v2.0+*
*Balancing-Anpassung: knowledge_id beibehalten, version erhöhen*
*Breaking Change (z.B. neue Rang-Stufen): ZARA_BALANCE_V2 erstellen*

# ZARA Equipment-Bibliothek V1
**Vollständige Item-Bibliothek für ZARA v2.0+**

Version: 1.0
Datum: März 2026
Items gesamt: 64 (8 Slots × 4 Seltenheiten × 2 Varianten)

---

## 🔖 KNOWLEDGE FILE META

```yaml
KNOWLEDGE_FILE_META:
  knowledge_id: "ZARA_ITEMS_V1"
  type: "domain_knowledge"
  version: "1.0"
  datum: "März 2026"
  kompatibel_mit: "ZARA v2.0+"

  provides:
    - "equipment_definitionen"
    - "item_namen"
    - "bonus_werte"
    - "drop_pool"

  fallback:
    wenn_nicht_geladen: "ZARA verwendet einfache Platzhalter-Items ohne Namen"
```

---

## Bonus-Kategorien

```yaml
bonus_typen:
  XP_BOOST:
    beschreibung: "Erhöht XP-Gewinn bei richtiger Antwort prozentual"
    formel: "basis_xp × (1 + boost/100)"

  BOSS_BESCHLEUNIGER:
    beschreibung: "Reduziert Aufgaben bis zum nächsten Boss"
    formel: "boss_schwelle = 8 - beschleuniger_wert"
    minimum_schwelle: 3

  BOSS_BESCHWOERUNG:
    beschreibung: "Kind kann vor Boss-Kampf stärkeren Boss wählen"
    stufen:
      standard: "Boss-Tier +1, Sieg-XP ×1.5"
      legendaer: "Boss-Tier +2, Sieg-XP ×2.0"

  XP_SCHUTZ:
    beschreibung: "Ladungen die XP-Verlust bei falscher Antwort verhindern"
    aktivierung: "Kind entscheidet aktiv beim Fehler"
```

---

## 🎩 KOPF-SLOT
*Thema: Wissen & Erkenntnis — Wahrscheinlicher Bonus: XP-Boost*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| K-G1 | Lernkappe des Numerus | +10% XP auf alle Aufgaben |
| K-G2 | Flickenhut des Addox | +10% XP auf alle Aufgaben |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| K-S1 | Denkhelm des Kalkulor | +20% XP auf alle Aufgaben |
| K-S2 | Stirnband des Sumgor | +20% XP + 1× XP-Schutz-Ladung |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| K-E1 | Krone des Magnath | +35% XP auf alle Aufgaben |
| K-E2 | Helm des Zahlenweisen Dividra | +30% XP + 2× XP-Schutz-Ladungen |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| K-L1 | Diadem des Ewigen Mathosaurus | +50% XP auf alle Aufgaben |
| K-L2 | Krone der Uralten Kalkulatrix | +40% XP + 3× XP-Schutz-Ladungen |

---

## 🧣 SCHULTERN-SLOT
*Thema: Last & Stärke — Wahrscheinlicher Bonus: Boss-Beschleuniger*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| S-G1 | Schulterplatten des Lernenden | Boss nach 7 statt 8 Aufgaben |
| S-G2 | Achselschutz des Pluskor | Boss nach 7 statt 8 Aufgaben |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| S-S1 | Schulterrüstung des Addrath | Boss nach 6 statt 8 Aufgaben |
| S-S2 | Kampfschultern des Mingor | Boss nach 6 statt 8 + +10% Kampf-XP |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| S-E1 | Schulterpanzer des Magnokron | Boss nach 5 statt 8 + +15% Kampf-XP |
| S-E2 | Kriegsschultern des Numerath | Boss nach 5 statt 8 + Boss-Beschwörung |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| S-L1 | Schultern des Unbesieglichen Sumgorth | Boss nach 4 statt 8 + +25% Kampf-XP |
| S-L2 | Titanenschultern des Fracnokron | Boss nach 4 statt 8 + Boss-Beschwörung (Legendär) |

---

## 🧥 KÖRPER-SLOT
*Thema: Schutz & Ausdauer — Wahrscheinlicher Bonus: XP-Schutz*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| KO-G1 | Ledergewand des Rechenanfängers | 1× XP-Schutz-Ladung pro Session |
| KO-G2 | Flickenrobe des Numerox | 1× XP-Schutz-Ladung pro Session |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| KO-S1 | Kettenhemd des Subtraktus | 2× XP-Schutz-Ladungen |
| KO-S2 | Schuppenrüstung des Konfrath | 2× XP-Schutz-Ladungen + +10% XP |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| KO-E1 | Plattenpanzer des Kalkulathar | 3× XP-Schutz-Ladungen + +15% XP |
| KO-E2 | Magiermantel des Shapnokron | 3× XP-Schutz-Ladungen + Boss nach 7 |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| KO-L1 | Rüstung des Ewigen Numeron | 5× XP-Schutz-Ladungen + +20% XP |
| KO-L2 | Drachenhaut des Uralten Multiphor | 5× XP-Schutz-Ladungen + Boss-Beschwörung |

---

## 🧤 HÄNDE-SLOT
*Thema: Geschick & Tempo — Wahrscheinlicher Bonus: XP-Boost (1. Versuch)*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| H-G1 | Lernhandschuhe des Pluskor | +15% XP bei 1.-Versuch-Treffer |
| H-G2 | Fingerling des Addox | +15% XP bei 1.-Versuch-Treffer |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| H-S1 | Kampfhandschuhe des Dividra | +25% XP bei 1.-Versuch-Treffer |
| H-S2 | Geschicksfäustlinge des Minukron | +20% XP bei 1.-Versuch-Treffer + 1× XP-Schutz |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| H-E1 | Kraftfäustlinge des Mulkrath | +40% XP bei 1.-Versuch-Treffer + +10% Kampf-XP |
| H-E2 | Zauberfinger des Geomrath | +35% XP bei 1.-Versuch-Treffer + 2× XP-Schutz |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| H-L1 | Fäuste des Legendären Fracnor | +60% XP bei 1.-Versuch-Treffer + +25% Kampf-XP |
| H-L2 | Titanenhände des Ewigen Magnath | +50% XP bei 1.-Versuch-Treffer + 3× XP-Schutz |

---

## 👖 BEINE-SLOT
*Thema: Ausdauer & Weg — Wahrscheinlicher Bonus: Globaler XP-Boost*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| B-G1 | Leinenhose des Wanderers | +8% XP global |
| B-G2 | Reisehose des Numerox | +8% XP global |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| B-S1 | Lederleggings des Numerath | +18% XP global |
| B-S2 | Kampfhose des Konfurath | +15% XP global + Boss nach 7 |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| B-E1 | Kriegshose des Shapor | +28% XP global + Boss nach 6 |
| B-E2 | Sturmleggings des Measrath | +25% XP global + 2× XP-Schutz |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| B-L1 | Beinschienen des Ewigen Rechenritters | +40% XP global + Boss nach 5 |
| B-L2 | Titanenhosen des Uralten Numerokron | +35% XP global + Boss-Beschwörung |

---

## 👟 FÜSSE-SLOT
*Thema: Bewegung & Tempo — Wahrscheinlicher Bonus: Boss-Beschleuniger + Beschwörung*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| F-G1 | Wanderstiefel des Lernenden | Boss nach 7 statt 8 Aufgaben |
| F-G2 | Rennschuhe des Addox | Boss nach 7 + +8% XP global |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| F-S1 | Sturmstiefel des Mingorrath | Boss nach 6 + +12% Kampf-XP |
| F-S2 | Eilschuhe des Numerath | Boss nach 6 + 1× XP-Schutz |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| F-E1 | Blitzstiefel des Magnokron | Boss nach 5 + Boss-Beschwörung |
| F-E2 | Geisterschuhe des Phantkor | Boss nach 5 + +20% Kampf-XP |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| F-L1 | Blitzschuhe des Unaufhaltsamen Measgon | Boss nach 3 + Boss-Beschwörung (Legendär) |
| F-L2 | Windstiefel des Ewigen Rennors | Boss nach 4 + +30% Kampf-XP + Boss-Beschwörung |

---

## 🧣 UMHANG-SLOT
*Thema: Ruf & Aura — Wahrscheinlicher Bonus: Boss-Beschwörung & globaler XP*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| U-G1 | Einfacher Reiseumhang | +5% XP global |
| U-G2 | Wollumhang des Zahlenläufers | +8% XP global |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| U-S1 | Umhang des Shapor | +15% XP global + Boss-Beschwörung |
| U-S2 | Kriegsumhang des Addrath | +12% XP global + Boss nach 6 |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| U-E1 | Kriegsmantel des Magnath | +25% XP global + Boss-Beschwörung |
| U-E2 | Schattenmantel des Geomkron | +20% XP global + Boss-Beschwörung + 2× XP-Schutz |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| U-L1 | Mantel des Legendären Geomkron | +40% XP global + Boss-Beschwörung (Legendär) |
| U-L2 | Auramantel des Uralten Numeromag | +35% XP global + Boss-Beschwörung + Boss nach 5 |

---

## 💍 ACCESSOIRE-SLOT
*Thema: Magie & Geheimnis — Wildcard: alle Bonus-Typen möglich*

### ✨ Gewöhnlich

| # | Name | Bonus |
|---|---|---|
| A-G1 | Zahlenstein des Lehrlings | +10% XP global |
| A-G2 | Glücksstein des Anfängers | Boss nach 7 statt 8 |

### 💛 Selten

| # | Name | Bonus |
|---|---|---|
| A-S1 | Amulett des Numerox | +20% XP global + 1× XP-Schutz |
| A-S2 | Talisman des Konfusor | Boss nach 6 + +15% Kampf-XP |

### 💜 Episch

| # | Name | Bonus |
|---|---|---|
| A-E1 | Kristall des Kalkulathor | +30% XP global + Boss-Beschwörung |
| A-E2 | Edelstein des Ewigen Frackor | +25% XP global + Boss nach 5 + 2× XP-Schutz |

### 🔴 Legendär

| # | Name | Bonus |
|---|---|---|
| A-L1 | Ring des Mathosauriers | +20% XP global + Boss nach 5 + 3× XP-Schutz |
| A-L2 | Orb des Uralten Numeromag | +15% XP global + Boss-Beschwörung (Legendär) + 3× XP-Schutz |

---

## Drop-Pool-Regeln

```yaml
drop_pool_regeln:
  pro_boss_sieg: "2 Items zufällig aus dem gesamten Pool"
  seltenheit_via: "ZARA_BALANCE_V1 Drop-Tabelle"
  kein_duplikat: "Beide Items sollen verschiedene Slots haben wenn möglich"
  varianten_auswahl: "Zufällig aus den 2 Varianten pro Seltenheitsstufe"
```

---

*ZARA_ITEMS_V1 · Kompatibel mit ZARA v2.0+ · Unabhängig vom Haupt-Prompt pflegbar*
*Neue Items: knowledge_id beibehalten, version erhöhen (ZARA_ITEMS_V1 → version: 1.1)*

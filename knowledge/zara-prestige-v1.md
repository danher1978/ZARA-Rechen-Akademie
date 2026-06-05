# ZARA Prestige-System V1
**Prestige-Mechanik nach Rang 10 für ZARA v2.0+**

Version: 1.0
Datum: März 2026

---

## 🔖 KNOWLEDGE FILE META

```yaml
KNOWLEDGE_FILE_META:
  knowledge_id: "ZARA_PRESTIGE_V1"
  type: "domain_knowledge"
  version: "1.0"
  datum: "März 2026"
  kompatibel_mit: "ZARA v2.0+"

  provides:
    - "prestige_mechanik"
    - "prestige_raenge"
    - "prestige_boni"

  fallback:
    wenn_nicht_geladen: "Prestige-Option nach Rang 10 nicht anzeigen"
```

---

## Was ist Prestige?

Wenn ein Kind **Rang 10 (👑 Legendärer Rechenheld)** erreicht und die maximale XP-Schwelle überschreitet, kann es "aufsteigen" — die Mathewelt braucht noch mehr Helden.

**Kernprinzip:**
- XP und Rang werden zurückgesetzt (Reset)
- Equipment bleibt vollständig erhalten
- Ein permanenter Prestige-Titel wird vergeben
- Ein unsichtbarer Prestige-Bonus bleibt dauerhaft aktiv
- Das Kind startet stärker als beim ersten Mal

---

## Prestige-Dialog

```
Zara: "✨✨✨ LEGENDÄRER AUFSTIEG! ✨✨✨

[Helden-Name] — du hast die Mathewelt gerettet!
Aber... die Dunkelheit kehrt zurück. Noch mächtiger.
Noch gefährlicher. Die Welt braucht dich erneut.

Du kannst aufsteigen — als Prestige-Held!
Das bedeutet:

✓ Deine Ausrüstung bleibt — du bleibst stark
✓ Du erhältst einen ewigen Prestige-Titel
✓ Ein geheimer Bonus begleitet dich für immer
✗ XP und Rang starten neu — der Weg beginnt wieder

Bist du bereit für den nächsten Aufstieg?

[⚡ Aufsteigen! Ich bin bereit!] [Noch warten]"
```

---

## Prestige-Stufen (3 Stufen)

### Prestige I — "Der Erwachte"

```yaml
prestige_1:
  voraussetzung: "Rang 10 erreicht (erste Mal)"
  titel_zusatz: "✦"           # Erscheint vor dem Rang-Namen
  beispiel: "✦ Rechen-Kämpfer"
  permanent_bonus:
    xp_boost: +5%             # Dauerhaft, stackt nicht mit Equipment
  session_state_aenderung:
    xp: 0
    rang_stufe: 1
    rang: "Rechenanfänger"
    prestige_stufe: 1
    prestige_titel: "Der Erwachte"
  equipment: "bleibt vollständig erhalten"
  zara_begruesssung: |
    "Willkommen zurück, ✦ [Name] der Erwachte!
     Die Mathewelt zittert vor deiner Kraft.
     Deine Ausrüstung leuchtet — du bist bereit! ⚔️"
```

### Prestige II — "Der Erleuchtete"

```yaml
prestige_2:
  voraussetzung: "Prestige I abgeschlossen, Rang 10 erneut erreicht"
  titel_zusatz: "✦✦"
  beispiel: "✦✦ Mathe-Ritter"
  permanent_bonus:
    xp_boost: +10%            # Ersetzt Prestige-I-Bonus (nicht additiv)
    xp_schutz_ladungen: +1    # Permanent eine Extra-Ladung zum Start jeder Session
  session_state_aenderung:
    xp: 0
    rang_stufe: 1
    rang: "Rechenanfänger"
    prestige_stufe: 2
    prestige_titel: "Der Erleuchtete"
  equipment: "bleibt vollständig erhalten"
  zara_begruesssung: |
    "✦✦ [Name] der Erleuchtete — die Legenden sprechen von dir!
     Mit jedem Abenteuer wirst du unaufhaltsamer.
     Die Monster fürchten dich bereits... ⚡"
```

### Prestige III — "Die Legende"

```yaml
prestige_3:
  voraussetzung: "Prestige II abgeschlossen, Rang 10 erneut erreicht"
  titel_zusatz: "✦✦✦"
  beispiel: "✦✦✦ Zahlen-Magier"
  permanent_bonus:
    xp_boost: +15%            # Ersetzt vorherige Prestige-Boni
    xp_schutz_ladungen: +2    # Permanent zwei Extra-Ladungen zum Start
    boss_beschleuniger: +1    # Boss kommt dauerhaft 1 früher
  session_state_aenderung:
    xp: 0
    rang_stufe: 1
    rang: "Rechenanfänger"
    prestige_stufe: 3
    prestige_titel: "Die Legende"
  equipment: "bleibt vollständig erhalten"
  zara_begruesssung: |
    "✦✦✦ [Name] — Die Legende der Mathewelt!
     Dein Name wird in die Zahlen der Welt geschrieben.
     Kein Monster kann dich aufhalten. Niemals. 👑"

  hinweis: "Prestige III ist die letzte Stufe. Danach: freies Weiterspielen ohne weiteren Prestige."
```

---

## Prestige im Session-State

```yaml
# Neue Felder in held:
held:
  prestige_stufe: 0           # 0 = kein Prestige, 1-3 = Prestige-Stufe
  prestige_titel: null        # "Der Erwachte" / "Der Erleuchtete" / "Die Legende"

# Neue Felder in aktive_boni:
aktive_boni:
  prestige_xp_boost: 0        # Aus Prestige-Stufe — permanent
  prestige_xp_schutz: 0       # Ladungen die JEDE Session neu vergeben werden
  prestige_boss_beschleuniger: 0
```

---

## /held Anzeige mit Prestige

```
⚔️ Dein Held, [Name]!
══════════════════════════════
[Symbol] [Prestige-Sterne] [Name] · [Rang]
[Prestige-Titel wenn vorhanden]
⭐ [XP] / [XP-Ziel] XP

[... Equipment wie gehabt ...]

AKTIVE BONI:
[Prestige-Bonus wenn aktiv: ✦ Prestige-Bonus: +[X]% XP dauerhaft]
[weitere Boni...]
══════════════════════════════
```

---

*ZARA_PRESTIGE_V1 · Kompatibel mit ZARA v2.0+*
*Erweiterung (z.B. 4. Prestige-Stufe): version erhöhen, knowledge_id beibehalten*

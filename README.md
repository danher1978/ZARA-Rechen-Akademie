# ZARA (Zauberhafte Adaptive Rechen-Akademie)

ZARA ist ein adaptive Mathe-Lernhelfer für Kinder der Klassen 1 bis 4 in Sachsen und orientiert sich am sächsichen lehrplan (https://www.schulportal.sachsen.de/lplandb/index.php). Der Assistent verbindet Mathematik mit einer spielerischen RPG-Welt, in der Kinder einen Helden aufbauen, Aufgaben lösen, XP sammeln, Bosse besiegen und Ausrüstung finden.

Die Idee dahinter ist persönlich: ZARA wurde entwickelt, um dem eigenen Kind einen abwechslungsreichen Zugang zum Mathe-Lernen zu geben, mit Monster- und Heldennamen in einer Stimmung, die an Yu-Gi-Oh erinnert, aber pädagogisch auf Grundschulmathematik ausgerichtet ist.

## Gliederung

1. Was ist ZARA?
2. Für wen ist ZARA?
3. Wie wird ZARA eingerichtet?
4. Wie wird ZARA genutzt?
5. Session speichern und laden
6. Erklärung der Knowledge-Files
7. Wichtige Hinweise für Eltern und Lehrkräfte
8. Lizenz

## Was ist ZARA?

ZARA ist ein vollständiger Assistent-Prompt für kindgerechtes Mathematiktraining mit Spielsystem. Der Prompt steuert die Rolle der Figur Zara, die Lernlogik, den Schwierigkeitsverlauf, Bosse, Ränge, Equipment, XP, Fehler-Feedback und die Session-Verwaltung.

Die aktuelle Basis ist [assistent/zara.md](assistent/zara.md), ergänzt durch optionale Wissensdateien im Ordner [knowledge](knowledge).

## Für wen ist ZARA?

ZARA ist für Kinder in der Grundschule gedacht, konkret für Klasse 1 bis 4 nach dem Mathematik-Lehrplan Sachsen.

ZARA eignet sich besonders, wenn:

- ein Kind Mathematik spielerischer üben soll
- Motivation über Fortschritt, Belohnung und Abenteuer helfen kann
- Aufgaben an das jeweilige Lernniveau angepasst werden sollen
- Eltern oder Lehrkräfte ein strukturierteres Übungsformat wünschen

ZARA ist nicht dafür gedacht, unbeaufsichtigt genutzt zu werden. Ein erwachsener Mensch sollte während der Nutzung dabei sein.

## Wie wird ZARA eingerichtet?

### In Claude

1. In [Claude](https://claude.ai/) ein neues Projekt anlegen.
2. Den Inhalt von [assistent/zara.md](assistent/zara.md) als Projekt-Prompt bzw. Projektanweisung verwenden.
3. Die Knowledge-Files aus dem Ordner [knowledge](knowledge) als Wissensdateien hochladen:
   - [knowledge/zara-items-v1.md](knowledge/zara-items-v1.md)
   - [knowledge/zara-balance-v1.md](knowledge/zara-balance-v1.md)
   - [knowledge/zara-prestige-v1.md](knowledge/zara-prestige-v1.md)
4. Danach mit einer neuen Unterhaltung im Projekt starten.

### In Gemini

1. In [Gemini](https://gemini.google.com/) einen neuen Gem anlegen.
2. Den Inhalt von [assistent/zara.md](assistent/zara.md) als Hauptprompt bzw. Anweisung einfügen.
3. Die Knowledge-Files aus dem Ordner [knowledge](knowledge) ergänzend hochladen:
   - [knowledge/zara-items-v1.md](knowledge/zara-items-v1.md)
   - [knowledge/zara-balance-v1.md](knowledge/zara-balance-v1.md)
   - [knowledge/zara-prestige-v1.md](knowledge/zara-prestige-v1.md)
4. Anschließend den Gem starten und mit ZARA arbeiten.

### Warum die Knowledge-Files wichtig sind

Der Haupt-Prompt ist bereits nutzbar, aber die Knowledge-Files geben ZARA die vollständigen Detaildaten für Equipment, Balance und Prestige. Damit bleiben die Inhalte klar getrennt und leichter wartbar.

## Wie wird ZARA genutzt?

Nach dem Start führt ZARA das Kind durch ein kindgerechtes Mathe-Abenteuer.

Typischer Ablauf:

1. ZARA begrüßt das Kind.
2. Falls noch keine Session geladen ist, wird der Held eingerichtet.
3. Das Lernfeld wird gewählt.
4. ZARA stellt Aufgaben passend zur Klassenstufe.
5. Richtige Antworten geben XP und Fortschritt.
6. Fehler werden in mehreren Stufen mit Ermutigung aufgefangen.
7. Nach mehreren Aufgaben kann ein Bosskampf erscheinen.
8. Am Ende kann die Session gespeichert oder beendet werden.

Wichtige Befehle aus dem Prompt sind unter anderem:

- `/aufgabe` für eine neue Aufgabe
- `/lernfeld` zum Wechseln des Lernfelds
- `/held` für die Helden-Übersicht
- `/speichern` zum Exportieren der Session
- `/laden [code]` zum Wiederherstellen einer Session

## Session speichern und laden

ZARA kann den aktuellen Spielstand als Session-Code sichern. Im Prompt wird dafür ein komprimierter Base64-JSON-Hash verwendet, der mit `ZARA2-` beginnt.

### Speichern

Wenn das Kind oder der Erwachsene `/speichern` nutzt, erzeugt ZARA einen Session-Code. Dieser Code sollte sicher aufbewahrt werden.

### Laden

In einer neuen Sitzung kann der gespeicherte Code mit `/laden [code]` wieder eingespielt werden. Damit wird der bisherige Fortschritt inklusive Held, XP, Ausrüstung und Lernstand fortgesetzt.

## Erklärung der Knowledge-Files

### [knowledge/zara-items-v1.md](knowledge/zara-items-v1.md)

Diese Datei enthält die Equipment-Bibliothek. Sie definiert:

- Item-Namen
- Slots wie Kopf, Schultern, Körper, Hände, Beine, Füße, Umhang und Accessoire
- Seltenheiten
- Boni wie XP-Boost, Boss-Beschleuniger, XP-Schutz und Boss-Beschwörung
- Drop-Regeln für Boss-Beute

### [knowledge/zara-balance-v1.md](knowledge/zara-balance-v1.md)

Diese Datei enthält die Balancing-Daten für das Spielsystem. Sie definiert:

- XP-Werte für richtige und falsche Antworten
- Boss-Schwellwerte
- Rangtabellen
- Boss-Tiers und Kampfwerte
- Drop-Raten und Rechenregeln

### [knowledge/zara-prestige-v1.md](knowledge/zara-prestige-v1.md)

Diese Datei ergänzt das Prestige-System ab Rang 10. Sie definiert:

- Prestige-Stufen
- Titel und permanente Boni
- Reset-Regeln für XP und Rang
- Anzeige und Verhalten nach dem Aufstieg

## Wichtige Hinweise für Eltern und Lehrkräfte

ZARA ist als begleiteter Lernassistent gedacht. Kinder sollen ZARA nicht unbeaufsichtigt nutzen. Ein Elternteil oder eine Lehrkraft sollte während des Spielens dabei sein.

Besonders wichtig ist sprachliche Unterstützung. ZARA ist so gedacht, dass Erwachsene bei Bedarf vorlesen, erklären und das Kind beim Sprechen unterstützen. Auch Sprachaufzeichnung oder Spracheingabe, zum Beispiel über ein Tablet, können hilfreich sein.

Weitere sinnvolle Hinweise:

- ZARA ersetzt keinen Unterricht, sondern ergänzt das Üben.
- Die Aufgaben sind für Mathematik in Klasse 1 bis 4 ausgelegt.
- Textaufgaben werden nicht direkt gelöst, sondern weitergeleitet.
- Der Lernstand sollte regelmäßig mit der Lehrkraft besprochen werden.
- Die Session-Daten sollten nicht mit Klarnamen oder unnötigen persönlichen Daten ergänzt werden.

## Lizenz

ZARA wird unter der MIT-Lizenz veröffentlicht. Details stehen in [LICENSE](LICENSE).

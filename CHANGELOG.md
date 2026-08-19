# Änderungsverlauf — S-IT-3Kopier

Alle nennenswerten Änderungen an S-IT-3Kopier, neueste zuerst.

## v3.3.2.9 — August 2026 · Internationale Fassung

- **Neu:** Das Tool spricht vier Sprachen – Deutsch, Englisch, Französisch und Spanisch. Die Sprache wird bei der Installation gewählt und lässt sich jederzeit unter ⚙ umstellen; die Auswahl zeigt zu jeder Sprache die zugehörige Flagge. Der Programmname wechselt mit: 3Kopier, 3Copy, 3Copier, 3Copiar.
- Übersetzt sind Oberfläche, alle Dialoge, die Meldungen während des Kopierens, die Zeitsteuerung und die Protokolle. Zu jeder Sprache gibt es eine eigene Hilfeseite; die Seiten sind untereinander verlinkt.
- Dateinamen und Einstellungen bleiben in allen Sprachen gleich (`3Kopier.ini`, Profile als `.3ko`, Ordner `Logs`) – ein Sprachwechsel ändert nichts an vorhandenen Profilen, Filtern und Einstellungen.
- **Verbessert:** Die Einstellungen (⚙) stehen jetzt zweispaltig – links Sprache und Skalierung, rechts Protokoll-Aufbewahrung und -Umfang. Das Fenster ist dadurch deutlich niedriger und passt auch bei hoher Skalierung vollständig auf den Bildschirm.
- **Verbessert:** Die Knöpfe der Profilleiste richten sich nach der Länge ihrer Beschriftung, damit der Text in jeder Sprache genügend Rand hat.

## v3.3.2.8 — August 2026

- **Neu:** Zeitstempel-Toleranz gegen Drift auf NAS- und Netzlaufwerken – im Modus „nur wenn neuer" werden unveränderte Dateien nicht mehr durch Sekunden-Abweichungen der Zeitstempel fälschlich als neuer erkannt und bei jedem Lauf neu kopiert (Toleranz von 2 Sekunden, wie bei Robocopy /FFT).
- **Neu:** 🛡-Symbol je Profil (neben 🚫) – stellt diese Toleranz ein (Automatisch / Immer / Aus); „Automatisch" wirkt nur bei `\\`-Netzwerkpfaden und ist voreingestellt, „Immer" hilft bei als Laufwerksbuchstabe eingebundenen Netzlaufwerken (`X:`, `Y:` …).
- **Verbessert:** Pfade in der Auftragsübersicht werden nicht mehr am Rand abgeschnitten, sondern sauber gekürzt angezeigt (Anfang…Ende); der vollständige Pfad steht im Tooltip.
- **Behoben:** Das Aktionsfenster ließ sich beim Start aus dem geöffneten Zeitsteuerungs-Fenster nicht minimieren; das Schließen-Kreuz (X) wirkt jetzt wie ⏹ Stop und bricht nur diesen einen Lauf sauber ab.

## v3.3.2 — Juli 2026

- **Neu:** Geschwindigkeitsanzeige – die Statuszeile zeigt während des Kopierens die aktuelle Übertragungsrate (z. B. `157.4 MB/s`), auch im Fortschrittsfenster der Zeitsteuerung.
- **Neu:** Auftragsfilter (🔰) je Auftrag – zusätzliche Ausschlüsse nur für diesen Auftrag oder eine NUR-Regel („nur bestimmte Dateitypen kopieren"), z. B. Auftrag 1 nur `*.pdf`. Das 🔰-Symbol wird grün, sobald eine Regel gesetzt ist; profilweite Ausschlüsse gelten weiterhin zusätzlich.
- **Neu:** Protokoll-Umfang wählbar (⚙) – Kompakt (Voreinstellung) mit einer Summenzeile je Auftrag, Ausführlich mit einer Zeile je Verzeichnis; Fehler stehen immer vollständig im Protokoll.
- **Neu:** Warteschlange für die Zeitsteuerung – kollidierende Läufe gehen nicht mehr verloren, sondern laufen nacheinander; Ergebnisfenster blockieren den nächsten Lauf nicht, ⏹ Stop bricht nur den laufenden ab. Das Aktionsfenster erscheint auch im Tray-Betrieb und lässt sich minimieren; Abbrüche stehen im Protokoll als „FAZIT (ABGEBROCHEN)".

## v3.3.1 — Juli 2026 · Wechsel auf Python

- Kompletter Wechsel von AutoIt auf Python – Bedienung und Ablauf unverändert, bestehende `3Kopier.ini`- und `.3ko`-Profildateien funktionieren ohne Anpassung weiter.
- Kopiervorgänge laufen im Hintergrund – die Oberfläche bleibt auch bei sehr vielen Dateien oder langsamen Netzlaufwerken reaktionsfähig; blockweise Kopie, „Stop" wirkt sofort.
- **Neu:** automatische Zeitsteuerung – Profile nach Zeitplan im Hintergrund ausführen, inklusive Silent-Modus und Tray-Betrieb mit Autostart.
- **Neu:** Ausschluss-Liste – Dateien und ganze Ordner (Browser-Caches, temporäre Dateien, große Image-Formate) vom Kopieren ausnehmen; mit Vorgaben ab Werk, pro Profil anpassbar.
- **Neu:** Ruhemodus nach dem Kopieren als Alternative zum Herunterfahren (beide Optionen schließen sich gegenseitig aus).
- Neue Einstellungen (⚙): Skalierung 90–200 %, Protokoll-Aufbewahrung (1 Tag bis unbegrenzt) mit Sofort-Aufräumen; Protokolle jetzt als eigene Datei je Lauf im Ordner `Logs`.
- Ergebnisfenster überarbeitet (eigene Spalte je Auftrag); Profil-Dropdown lädt sofort ohne „Laden"-Knopf; sehr lange Pfade werden verkürzt angezeigt (Anfang…Ende), voller Pfad im Tooltip.
- Netzwerk-/NAS-Pfade (UNC) verbessert, Datenmengen-Berechnung ohne Einfrieren; Ergebnis-Fazit steht jetzt oben; kleinere Layout-Korrekturen; `Lizenz.txt` liegt bei.

## v3.2.1 — AutoIt-Version

- Automatische Behandlung langer Pfade (MAX_PATH): Zielpfade ab 260 Zeichen werden automatisch gekürzt – zuerst der Dateiname, bei Bedarf auch der letzte Unterordner. Gekürzte Namen erhalten die Markierung `-3k`.
- Datenmenge auch bei langen Pfaden korrekt in Anzeige und Fortschrittsbalken berücksichtigt.
- Log-Größe automatisch auf 512 KB begrenzt – älteste Einträge werden entfernt, aktuelle Läufe bleiben erhalten.

## v3.2.0 — AutoIt-Version

- Überschreiben/Verschieben-Optionen je Auftrag werden jetzt sowohl in der INI als auch in `.3ko`-Profilen gesichert.
- Zielverzeichnisse werden vor der Prüfung angelegt; Netzwerkpfade werden bei der Datenmengenberechnung übersprungen, ohne einzufrieren.
- Optische Korrekturen: Header-Abstände, Label-Breiten und Checkbox-Positionen überarbeitet.

---

© 2026 Sattler IT-Service, Greifenstein · Autor: Hans Udo Sattler

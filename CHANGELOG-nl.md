# Wijzigingsoverzicht — S-IT-3Kopieer

Alle noemenswaardige wijzigingen in S-IT-3Kopieer, de nieuwste eerst.

## v3.3.2.10 — september 2026 · Nederlands en Italiaans

- **Nieuw:** twee talen erbij – **Nederlands** en **Italiaans**. Daarmee spreekt het programma zes talen. De programmanaam wisselt mee: 3Kopieer en 3Copia.
- Vertaald zijn zoals gebruikelijk de vensters, de dialoogvensters, de meldingen, de planner en de logboeken; bij beide talen hoort een eigen helppagina.
- De taalbalk op alle helppagina's biedt nu zes talen.
- Aan het programma zelf is niets veranderd – bestaande profielen, filters en instellingen blijven ongewijzigd.

## v3.3.2.9 — augustus 2026 · Internationale uitvoering

- **Nieuw:** het programma spreekt vier talen – Duits, Engels, Frans en Spaans. De taal wordt bij de installatie gekozen en kan op elk moment onder ⚙ worden gewijzigd; de keuze toont bij elke taal de bijbehorende vlag. De programmanaam wisselt mee: 3Kopier, 3Copy, 3Copier, 3Copiar.
- Vertaald zijn de vensters, alle dialoogvensters, de meldingen tijdens het kopiëren, de planner en de logboeken. Elke taal heeft een eigen helppagina; de pagina's verwijzen naar elkaar.
- Bestandsnamen en instellingen blijven in alle talen gelijk (`3Kopier.ini`, profielen als `.3ko`, map `Logs`) – een taalwissel verandert niets aan bestaande profielen, filters en instellingen.
- **Verbeterd:** de instellingen (⚙) staan nu in twee kolommen – links taal en schaal, rechts bewaartermijn en omvang van de logboeken. Het venster is daardoor duidelijk lager en past ook bij een hoge schaal volledig op het scherm.
- **Verbeterd:** de knoppen in de profielbalk passen zich aan de lengte van hun opschrift aan, zodat de tekst in elke taal genoeg marge houdt.

## v3.3.2.8 — augustus 2026

- **Nieuw:** marge op tijdstempels tegen afwijkingen bij NAS- en netwerkschijven – in de stand „alleen als nieuwer" worden onveranderde bestanden niet meer door verschillen van enkele seconden ten onrechte als nieuwer gezien en bij elke doorloop opnieuw gekopieerd (marge van 2 seconden, zoals bij Robocopy /FFT).
- **Nieuw:** teken 🛡 per profiel (naast 🚫) – stelt die marge in (Automatisch / Altijd / Uit); „Automatisch" werkt alleen bij `\\`-netwerkpaden en is de standaard, „Altijd" helpt bij netwerkschijven met een stationsletter (`X:`, `Y:` …).
- **Verbeterd:** paden in het opdrachtoverzicht worden niet meer bij de rand afgesneden maar netjes ingekort weergegeven (begin…einde); het volledige pad staat in de tooltip.
- **Opgelost:** het uitvoervenster kon niet worden geminimaliseerd wanneer het vanuit het geopende plannervenster was gestart; het kruisje (X) werkt nu als ⏹ Stop en breekt alleen die ene taak netjes af.

## v3.3.2 — juli 2026

- **Nieuw:** snelheidsweergave – tijdens het kopiëren toont de statusregel de actuele overdrachtssnelheid (bijvoorbeeld `157.4 MB/s`), ook in het voortgangsvenster van de planner.
- **Nieuw:** opdrachtfilter (🔰) per opdracht – extra uitsluitingen alleen voor die opdracht of een ALLEEN-regel („alleen bepaalde bestandstypen kopiëren"), bijvoorbeeld opdracht 1 alleen `*.pdf`. Het teken 🔰 wordt groen zodra er een regel is ingesteld; uitsluitingen voor het hele profiel gelden daarnaast gewoon.
- **Nieuw:** omvang van het logboek instelbaar (⚙) – Beknopt (standaard) met één samenvattende regel per opdracht, Uitgebreid met een regel per map; fouten staan altijd volledig in het logboek.
- **Nieuw:** wachtrij voor de planner – botsende taken gaan niet meer verloren maar draaien na elkaar; resultaatvensters blokkeren de volgende taak niet, ⏹ Stop breekt alleen de lopende af. Het uitvoervenster verschijnt ook bij werken in het systeemvak en kan worden geminimaliseerd; afgebroken taken staan in het logboek als „FAZIT (ABGEBROCHEN)".

## v3.3.1 — juli 2026 · Overstap naar Python

- Volledige overstap van AutoIt naar Python – bediening en verloop ongewijzigd, bestaande `3Kopier.ini`- en `.3ko`-profielbestanden werken zonder aanpassing verder.
- Het kopiëren gebeurt op de achtergrond – het venster blijft ook bij zeer veel bestanden of trage netwerkschijven reageren; kopiëren per blok, „Stop" werkt onmiddellijk.
- **Nieuw:** automatische planner – profielen volgens een schema op de achtergrond uitvoeren, met stille modus en werken in het systeemvak met automatisch starten.
- **Nieuw:** uitsluitingslijst – bestanden en hele mappen (browsercaches, tijdelijke bestanden, grote imageformaten) buiten het kopiëren houden; met verstandige uitgangswaarden, per profiel aan te passen.
- **Nieuw:** slaapstand na het kopiëren als alternatief voor afsluiten (de twee mogelijkheden sluiten elkaar uit).
- Nieuwe instellingen (⚙): schaal 90–200 %, bewaartermijn van de logboeken (1 dag tot onbeperkt) met meteen opruimen; logboeken nu een eigen bestand per taak in de map `Logs`.
- Resultaatvenster herzien (een eigen kolom per opdracht); de profielkeuzelijst laadt meteen, zonder knop „Laden"; heel lange paden worden ingekort weergegeven (begin…einde), het volledige pad in de tooltip.
- Netwerk- en NAS-paden (UNC) verbeterd, berekening van de hoeveelheid gegevens zonder vastlopen; de eindbalans staat nu bovenaan; kleine correcties in de opmaak; `Lizenz.txt` is bijgevoegd.

## v3.2.1 — AutoIt-versie

- Automatische behandeling van lange paden (MAX_PATH): doelpaden vanaf 260 tekens worden automatisch ingekort – eerst de bestandsnaam, zo nodig ook de laatste submap. Ingekorte namen krijgen de markering `-3k`.
- Hoeveelheid gegevens ook bij lange paden juist meegeteld, in de weergave en in de voortgangsbalk.
- Grootte van het logboek automatisch beperkt tot 512 KB – de oudste regels verdwijnen, recente taken blijven bewaard.

## v3.2.0 — AutoIt-versie

- De opties overschrijven/verplaatsen per opdracht worden nu zowel in het INI-bestand als in `.3ko`-profielen bewaard.
- Doelmappen worden vóór de controle aangemaakt; netwerkpaden worden bij het berekenen van de hoeveelheid gegevens overgeslagen, zonder vast te lopen.
- Correcties in de weergave: afstanden in de kop, breedte van de opschriften en plaats van de selectievakjes herzien.

---

© 2026 Sattler IT-Service, Greifenstein · Auteur: Hans Udo Sattler

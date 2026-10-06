# messerschmidt-karriere – Karriereseite des Zahnzentrums Messerschmidt (Mainz-Laubenheim)

Statische Karriereseite, gebaut von der AO Consulting GmbH nach dem Standard der Karriereseiten 2.0
(Aufbau wie whiteblick-karriere / ao-karriere), Gestaltung nach der Hauptseite https://zahnzentrum-messerschmidt.de.

- **Vorschau:** https://messerschmidt-karriere.vorschau.ao-consult.de (Zweig `main`, Google ausgesperrt)
- **Live:** https://zahnzentrum-messerschmidt-karriere.de (Zweig `live`, nur auf das Wort „live“ eines Mitarbeiters) – Domain ist **noch nicht registriert**

## Aufbau

```
kunde.json              Stammdaten: Firma, Standorte, Farben, Empfänger, Einstellungen
stellen/*.json          eine Datei je Stelle – DIE Quelle für Stellenseiten, Google for Jobs, Indeed
vorlagen/               HTML-Vorlagen für Stellenseite und Listeneintrag
scripts/bauen.py        baut aus kunde.json + stellen/ alles Generierte in website/
scripts/pruefen.py      prüft die fertige Seite (Google-Daten, Links, Platzhalter, Datenschutz)
scripts/stellen-aktualisieren.py  frischt Datumsangaben auf (monatlich automatisch)
website/                die Seite – nur was hier liegt, geht online
doku/                   Unterlagen, Entscheidungen, alte Adressen, Livegang-Stand
.github/workflows/      vorschau.yml, livegang.yml, stellen-aktualisieren.yml
```

## Stellen pflegen (das Tägliche)

1. Datei in `stellen/` anlegen oder ändern (Kopie einer bestehenden, `kennung` = Dateiname).
2. `python3 scripts/bauen.py` dann `python3 scripts/pruefen.py` – beides muss ohne FEHLER laufen.
3. Hochladen auf `main` → Vorschau ansehen → auf Zuruf „live“ den Zweig `live` nachziehen.

**Status** je Stelle: `aktiv` (offen) · `initiativ` (besetzt, Initiativbewerbungen willkommen –
bleibt online, wird weiter aufgefrischt) · `pausiert` (unsichtbar, nicht im Feed).
Besetzte Stellen setzt die AO Consulting auf `initiativ`, nicht der Kunde.

**Nie von Hand ändern:** `website/stellen/*.html`, der Block zwischen den STELLEN-Markern in
`website/index.html`, `website/assets/css/ci.css`, `sitemap.xml`, `indeed-feed.xml`,
`stellen.json`, `bewerbung-konfiguration.php`. Das baut `bauen.py` – Änderungen dort sind beim
nächsten Lauf weg.

## Automatik

Am 1. jedes Monats setzt `stellen-aktualisieren.yml` `veroeffentlicht` und `gueltig_bis` neu,
baut, prüft und checkt auf `main` **und** `live` ein. Das ist die einzige Ausnahme von der
Regel „live nur auf Zuruf“ – es ändern sich ausschließlich Datumsangaben. Google for Jobs
braucht das, sonst verschwinden die Anzeigen nach Ablauf von `validThrough`.

## Bewerbungen

Formular auf jeder Stellenseite → `bewerbung-senden.php` (nur auf All-Inkl, nicht in der Vorschau):
Mail mit allen Angaben und PDF-Anhängen an die Empfänger der Stelle (`bewerbungen_an`), Eingangsbestätigung
an den Bewerber. Es wird nichts gespeichert. In der Vorschau öffnet sich stattdessen das Mailprogramm.

## Stand 2026-10-06

Erstfassung von Awan Tofik mit Claude: drei Stellen (ZFA Voll-/Teilzeit, ZMP/ZMF, Ausbildung ZFA September 2027),
Fotos aus dem Shooting (Ordner „iwanartemjew_AO_Consuting_-_Zahnzentrum_Messerschmidt“), Logo als PNG von der Hauptseite,
Schriften Roboto Condensed + Open Sans lokal. Annahmen und offene Punkte: `doku/entscheidungen.md`.

## Vor dem Livegang zu erledigen

- [ ] Platzhalter weg (`pruefen.py` grün), Impressum und Datenschutz vom Kunden freigegeben
- [ ] `kunde.json → vorschau: false`, Absenderadresse auf der Live-Domain existiert als Postfach
- [ ] Alte Adressen in `.htaccess` weitergeleitet (`doku/alte-adressen.md`)
- [ ] Testbewerbung auf der Übergangsadresse: kommt bei der Praxis UND beim Bewerber an, nicht im Spam
- [ ] Search Console: Property, Sitemap, Rich-Results-Test für zwei Stellenseiten grün
- [ ] Indeed: `https://zahnzentrum-messerschmidt-karriere.de/indeed-feed.xml` bei Indeed für Arbeitgeber eingereicht
- [ ] Matomo-Eintrag angelegt, `matomo_id` eingetragen, Datenschutz passt

Ablauf für Projekt, Vorschau, DNS und Livegang: Skill `webseite-veroeffentlichen`.

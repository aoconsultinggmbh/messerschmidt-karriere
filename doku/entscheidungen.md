# Entscheidungen und offene Punkte – Karriereseite Zahnzentrum Messerschmidt

Stand 06.10.2026, Awan Tofik mit Claude.

## Vorgaben von Awan (Chat 06.10.2026)

- Aufbau nach dem Standard der Karriereseiten (ao-karriere, whiteblick-karriere), CI der Hauptseite zahnzentrum-messerschmidt.de.
- Logo und CI von der Hauptseite nehmen (SVG kommt laut Onboarding später von der Kundin).
- Bewerbungen und alle sichtbaren Adressen: **info@zahnzentrum-messerschmidt.de** (Kundenmail, Korrektur Awan 06.10.2026 – AO bekommt nur den ersten Formulartest). Absender: **jobs@zahnzentrum-messerschmidt-karriere.de**.
- WhatsApp-Knopf **und** normale Telefonnummer. Upload-Feld trotzdem anbieten (Erstkontakt ohne Unterlagen möglich).
- ZFA: Voll- und Teilzeit, ab sofort. ZMP/ZMF: eine Stelle. Ausbildung: September 2027, Anzahl der Plätze NICHT nennen.
- Standardtexte für die Stellen. Arbeitszeiten (Sprechzeiten) dürfen auf die Seite. Noch keine Teamstimmen → Abschnitt weggelassen.
- Impressum und Datenschutz erstmal von der Hauptseite. Matomo unter statistik.ao-consult.de wie üblich.

## Von Awan bestätigt (06.10.2026)

- Foto Nr. 62 ist Dr. Sabine Messerschmidt.
- WhatsApp-Nummer +49 1515 4321140 darf auf die Seite.
- ZMP/ZMF: ab sofort.
- Sichtbare E-Mail und Empfänger: info@zahnzentrum-messerschmidt.de.
- Keine Hochkantbilder, kein Motiv doppelt; Ampel: Offen grün, Initiativ senfgelb; keine Datumszeile auf den Stellenseiten.
- Fotos: Iwan Artemjew, Fotograf der AO Consulting GmbH.

## Weitere Annahmen

- **ZMP/ZMF:** Voll-/Teilzeit angenommen („ab sofort“ bestätigt).
- **Telefon** auf der Seite: Praxisnummer 06131 86926. Die Nummer 06249 905437 aus dem Onboarding ist nicht auf der Seite.

## Offen vor dem Livegang

- [ ] Falls die Kundin eine eigene Bewerbungsadresse anlegt (z. B. karriere@zahnzentrum-messerschmidt.de): in kunde.json `bewerbungen.standard_empfaenger` tauschen.
- [ ] Domain zahnzentrum-messerschmidt-karriere.de registrieren; Postfach jobs@ auf dieser Domain anlegen (Absender).
- [ ] Impressum: „Umsatzsteueridentifikationsnummer 28/114/5003/0“ ist das Format einer Steuernummer – mit Kundin klären.
- [ ] Datenschutz von der Kundin freigeben lassen (Hauptseite war Stand 2018 mit Google Analytics/Privacy Shield – nicht übernommen).
- [ ] Logo als SVG von der Kundin einsetzen (jetzt PNG 246×135 von der Hauptseite).
- [ ] Stellentexte und Benefits von der Kundin freigeben lassen; Gehalt nur mit Freigabe.
- [ ] Matomo-Eintrag anlegen, `matomo_id` in kunde.json eintragen.
- [ ] Instagram-Passwort stand im Onboarding-PDF im Klartext → in den Passwort-Manager, Kundin sollte es ändern.

## Angleichung an die neue Hauptseite (06.10.2026)

- Gestaltung 1:1 von der neuen Hauptseite (messerschmidt-website): `website/assets/css/stil.css` ist eine **Kopie** der Hauptseite,
  Karriere-Eigenes steht in `karriere.css`. Änderungen am Grunddesign in der Hauptseite machen und stil.css herüberkopieren.
- Schrift Manrope (lokal), Logo quer (`logo-quer.png`, `logo-quer-weiss.png`), Kopf durchsichtig über dem Teamfoto, Bewegungen wie auf der Hauptseite.
- AO-Standard: Barrierefreiheits-Widget und Einwilligungsbanner. Das Banner erscheint hier nicht, weil die Karriereseite nichts
  Einwilligungspflichtiges lädt (`assets/js/ao-konfiguration.js` hat nur „Notwendig“). Neue Seite `rechtliches/barrierefreiheit.html`.
- WhatsApp bleibt auf der Karriereseite (nur auf der Hauptseite entfernt): am Rechner links unten, am Handy in der Schnellleiste.
- Vorschau: Links auf zahnzentrum-messerschmidt.de zeigen in der Vorschau auf messerschmidt.vorschau.ao-consult.de (`hauptseite_vorschau` in kunde.json).
- `.htaccess` korrigiert: enthielt noch Regeln und Weiterleitungen der Whiteblick-Karriereseite.
- `bauen.py` hängt `?v=<Prüfsumme>` an CSS/JS, damit nach Änderungen keine alten Dateien aus dem Zwischenspeicher kommen.
- Stellenseiten: `seo_titel` (unter 60 Zeichen) für Google, Kopf mit Bild, Ansprechpartnerin und Eckdaten rechts (am Handy oben).

## Bilder (Shooting Iwan Artemjew, Nummer = Dateiname ZahnzentrumMesserschmidt_<Nr>.jpg)

Regel: nur Querformat-Originale, jedes Motiv (Serie) nur einmal auf der Startseite.

| Datei | Nr. | Verwendung |
|---|---|---|
| hero-flur-2 / hero-flur-mobil | 52 | Titelbild, steht still (seit 08.10.2026, Wunsch Awan; vorher hero-team Nr. 29 mit langsamem Zoom) |
| og-bild | 29 | Vorschaubild für Links |
| haus | 14 | Über uns |
| leitsatz | 17 | Hintergrund Leitsatz |
| job-familie | 24 | Team |
| gruende-kollegen / -modern / -hell | 47 / 2 / 112 | Drei Gründe |
| ansprechpartner(-quer) | 62 | Dr. Sabine Messerschmidt (bestätigt) |
| faq-empfang | 33 | FAQ |
| stelle-zfa-behandlungszimmer / stelle-zmp-zmf-empfang / stelle-ausbildung-flur | 23 / 45 / 54 | Kopfbild der Stellenseiten, seit 08.10.2026 als ganzes Foto im Rahmen neben dem Text (keine angeschnittenen Köpfe, Wunsch Awan; vorher 21 / 80 / 102 als Hintergrund). Frau Messerschmidt bewusst nicht im Kopfbild, sie steht als Ansprechpartnerin auf derselben Seite |

Jede Serie nur einmal auf der Startseite. Fotoband und Bilder beim Bewerbungsprozess entfernt (dort waren Serien doppelt: Hände 17/19, Empfang 33/36).
Nicht verwendet: Hochkant (3, 5, 7, 15, 27, 49–55) und Wiederholungen derselben Serie. Zuschnitt: `bilder.py` (Mac-Arbeitsordner), jpg + webp.

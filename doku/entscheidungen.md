# Entscheidungen und offene Punkte – Karriereseite Zahnzentrum Messerschmidt

Stand 06.10.2026, Awan Tofik mit Claude.

## Vorgaben von Awan (Chat 06.10.2026)

- Aufbau nach dem Standard der Karriereseiten (ao-karriere, whiteblick-karriere), CI der Hauptseite zahnzentrum-messerschmidt.de.
- Logo und CI von der Hauptseite nehmen (SVG kommt laut Onboarding später von der Kundin).
- Testbewerbungen an **tofik@ao-consult.de**. Absender: **jobs@zahnzentrum-messerschmidt-karriere.de**.
- WhatsApp-Knopf **und** normale Telefonnummer. Upload-Feld trotzdem anbieten (Erstkontakt ohne Unterlagen möglich).
- ZFA: Voll- und Teilzeit, ab sofort. ZMP/ZMF: eine Stelle. Ausbildung: September 2027, Anzahl der Plätze NICHT nennen.
- Standardtexte für die Stellen. Arbeitszeiten (Sprechzeiten) dürfen auf die Seite. Noch keine Teamstimmen → Abschnitt weggelassen.
- Impressum und Datenschutz erstmal von der Hauptseite. Matomo unter statistik.ao-consult.de wie üblich.

## Von Awan bestätigt (06.10.2026)

- Foto Nr. 62 ist Dr. Sabine Messerschmidt.
- WhatsApp-Nummer +49 1515 4321140 darf auf die Seite.
- ZMP/ZMF: ab sofort.
- Sichtbare E-Mail info@zahnzentrum-messerschmidt.de passt.
- Fotos: Iwan Artemjew, Fotograf der AO Consulting GmbH.

## Weitere Annahmen

- **ZMP/ZMF:** Voll-/Teilzeit angenommen („ab sofort“ bestätigt).
- **Telefon** auf der Seite: Praxisnummer 06131 86926. Die Nummer 06249 905437 aus dem Onboarding ist nicht auf der Seite.

## Offen vor dem Livegang

- [ ] Empfängeradresse Bewerbungen (Vorschlag karriere@zahnzentrum-messerschmidt.de) – in kunde.json `bewerbungen.standard_empfaenger` tauschen.
- [ ] Domain zahnzentrum-messerschmidt-karriere.de registrieren; Postfach jobs@ auf dieser Domain anlegen (Absender).
- [ ] Impressum: „Umsatzsteueridentifikationsnummer 28/114/5003/0“ ist das Format einer Steuernummer – mit Kundin klären.
- [ ] Datenschutz von der Kundin freigeben lassen (Hauptseite war Stand 2018 mit Google Analytics/Privacy Shield – nicht übernommen).
- [ ] Logo als SVG von der Kundin einsetzen (jetzt PNG 246×135 von der Hauptseite).
- [ ] Stellentexte und Benefits von der Kundin freigeben lassen; Gehalt nur mit Freigabe.
- [ ] Matomo-Eintrag anlegen, `matomo_id` in kunde.json eintragen.
- [ ] Instagram-Passwort stand im Onboarding-PDF im Klartext → in den Passwort-Manager, Kundin sollte es ändern.

## Bilder (Shooting, Nummer = Dateiname ZahnzentrumMesserschmidt_<Nr>.jpg)

| Datei | Nr. | Verwendung |
|---|---|---|
| hero-team(-mobil), og-bild | 29 | Titelbild, Vorschaubild für WhatsApp/Social |
| haus | 14 | Über uns (Haus von oben mit Solaranlage) |
| job-familie | 24 | Team-Abschnitt |
| gruende-kollegen / -modern / -hell | 17 / 4 / 21 | Drei Gründe |
| prozess-unterlagen / -telefonat / -gespraech / -schnuppertag | 39 / 35 / 44 / 54 | Bewerbungsprozess |
| ansprechpartner(-quer) | 62 | Dr. Sabine Messerschmidt (bestätigen!) |
| faq-empfang | 33 | FAQ |
| stelle-zfa / -zmp-zmf / -ausbildung | 23 / 47 / 113 | Stellenseiten |
| praxis-<Nr> | 29, 23, 14, 33, 16, 53, 43, 2, 112, 36, 19, 47, 105, 28 | Fotoband |

Zuschnitt: Skript `bilder.py` (Mac-Arbeitsordner), jpg + webp. Die Einzelportraits (Nr. 56–104) sind noch ungenutzt – ohne Namen
nicht verwendbar; ideal für einen späteren Team-Abschnitt, wenn Namen und Rollen da sind.

# mh anwälte – Vorlagengenerator

Ein Werkzeug für die tägliche Kanzleikommunikation: Einladungen, LinkedIn-Kacheln,
E-Mails, Briefbogen, Bescheinigungen, Visitenkarten, Signatur und Logo-Dateien –
alles im Auftritt von mh anwälte (mhanwaelte.de).

## Öffnen

`Vorlagengenerator mh anwaelte v2.dc.html` im Browser öffnen. Kein Server, kein
Build, keine Installation. Die Datei lädt `support.js` und die Bilder aus `assets/`
über relative Pfade – der Ordner muss also vollständig bleiben.

Getestet in aktuellen Versionen von Chrome, Edge und Safari.

## Aufbau

Kopfleiste, darunter die Tab-Leiste mit acht Vorlagen. Links das Eingabefeld,
rechts die Vorschau. Alle Eingaben werden im Browser gespeichert
(`localStorage`, Schlüssel `mh-generator-v2`) und stehen beim nächsten Öffnen
wieder bereit. „Beispieldaten laden" setzt auf den Ausgangsstand zurück.

| Tab | Ausgabe |
| --- | --- |
| Einladung & Save the Date | A4 quer, 1 Seite oder vollständige Einladung mit Programmseite je Tag – über „Drucken / PDF" |
| LinkedIn-Kacheln | PNG in 1080×1080, 1200×627, 1080×1350, 1080×1920; optional Karussell als PNG-Serie |
| E-Mails | Tabellenbasiertes HTML zum Kopieren oder als Datei |
| Briefbogen | A4 hoch mit Anschriftenfeld, Aktenzeichen, Fußsteg |
| Teilnahmebescheinigung | A4 quer, § 15 FAO |
| Visitenkarte | Vorder- und Rückseite auf einem Bogen, 85 × 55 mm |
| E-Mail-Signatur | HTML zum Einfügen ins Mailprogramm, oder als Text |
| Logo-Dateien | Wortmarke als PNG – auf Weiß, auf Anthrazit, quadratisch |

## Eingabe mehrzeiliger Felder

Wo mehrere Einträge nötig sind, steht je Zeile ein Eintrag, die Felder trennt ein
senkrechter Strich:

```
Tage       Datum | Monat | Wochentag | Uhrzeit | Kurztitel | Zusammenfassung
Programm   Tag | Zeit | Titel | Referent | Unterpunkte mit Semikolon getrennt
Logistik   Rubrik | Zeile / Zeile / Zeile
Karussell  Titel | Text
```

Ein `~` vor dem Titel eines Programmpunkts kennzeichnet eine Pause – sie wird
gedämpft gesetzt.

## Farben und Schrift

| | |
| --- | --- |
| Orange | `#FF5900` |
| Gold | `#EFBB20` |
| Anthrazit | `#2C353D` |
| Text | `#333333` |
| Grau | `#616161` |
| Linien | `#CFD2D5` |
| Fläche | `#E4E5E7` |

Open Sans für Fließtext und Überschriften, IBM Plex Mono für Prompt-Felder;
beide werden von Google Fonts geladen. Ohne Internetverbindung fällt die
Darstellung auf Arial zurück – die Maße bleiben gleich.

## Vorbehalt zum Logo

`assets/mh-logo-dreizeiler.png` ist ein Freisteller in Bildschirmauflösung. Die
dunkle Fassung im Tab „Logo-Dateien" ist eine **Nachbildung in Open Sans**, nicht
die Originalschrift der Wortmarke. Für Druck und Fremddienstleister bitte die
Originaldateien der Agentur verwenden.

## Dateien

```
Vorlagengenerator mh anwaelte v2.dc.html   der Generator
Prompt der Woche B Anthrazit.dc.html       Entwurf der Kachelform, so übernommen
support.js                                 Laufzeitumgebung, nicht bearbeiten
assets/                                    Logodateien
briefing.txt                               Design-Auslese der Live-Site, Juni 2026
uploads/                                   Ausgangsmaterial
```

Die Dateinamen enthalten Leerzeichen. Beim Verlinken auf GitHub werden sie zu
`%20` – die Datei selbst öffnet normal.

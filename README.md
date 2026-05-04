# Sportdata PSS Simulator

Öffentliches Download-Repository für die Windows-Releases des Sportdata PSS Simulators.

Der Simulator ist eine Desktop-Anwendung zum lokalen Aufzeichnen, Inspizieren, Annotieren und Wiedergeben von UDP-basierten JSON-Paketen im PSS-Umfeld. Dieses Repository enthält keine Quelltexte der Anwendung, sondern nur die öffentlich bereitgestellten Installer-Releases.

## Download

1. Öffne die Seite [Latest Release](https://github.com/Dbro93/sportdata-pss-simulator-releases/releases/latest).
2. Lade unter `Assets` die Datei `Sportdata.PSS.Simulator.Setup.X.Y.Z.exe` herunter.
3. Starte den Installer und folge dem Setup-Dialog.

Falls Windows SmartScreen eine Warnung zeigt, liegt das daran, dass der Installer aktuell nicht code-signiert ist. Prüfe in diesem Fall, ob du die Datei direkt aus diesem GitHub-Repository geladen hast.

## Wofür die Anwendung gedacht ist

Der Sportdata PSS Simulator hilft beim Testen von Systemen, die PSS-nahe UDP-JSON-Pakete empfangen oder verarbeiten. Typische Einsätze sind lokale Integrations- und Entwicklungstests, Nachstellen aufgezeichneter Abläufe und kontrolliertes Senden einzelner Aktionen ohne eine echte Live-Quelle.

## Features

- Lokaler Windows-Desktop-Installer.
- Senden einzelner kuratierter Aktionen an eine frei wählbare Ziel-IP und einen UDP-Port.
- Integrierte Beispielbibliotheken für Ju-Jutsu Fighting, BJJ und Duo.
- Countdown-CLOCK-Wiedergabe, wenn für eine Aufnahme ein CLOCK-Template vorhanden ist.
- Autopilot-Modus, der CLOCK-Pakete und annotierte Aktionen in einer kontrollierten Reihenfolge sendet.
- Live-Aufnahme eingehender UDP-Pakete auf einem wählbaren Port.
- Speicherung von Rohpayloads, geparsten JSON-Daten, Zeitstempeln, Quell-IP und Quell-Port.
- Manuelle Annotation von Paketen als wiederverwendbare Aktionen inklusive Notizen.
- Inspektionsansicht für gespeicherte Sessions mit Suche, Filtern, JSON-Ansicht und Änderungsdiffs.
- Lokale Bibliothek für eigene Sportarten und eigene Aufnahmen.
- Keine eingebaute Telemetrie, keine Benutzerkonten und kein automatischer Cloud-Upload.

## Schnellstart

1. Installiere und starte den Simulator.
2. Öffne den Bereich `Simulator`.
3. Wähle eine Sportart bzw. Session aus der Bibliothek.
4. Trage Zielhost und Zielport des empfangenden Systems ein. Für lokale Tests ist der Host oft `127.0.0.1`, der Standardport ist `23456`.
5. Wähle eine Aktion aus und sende sie einzeln, oder starte den Countdown bzw. Autopilot, wenn die gewählte Session das unterstützt.
6. Beobachte im Zielsystem, ob die UDP-JSON-Pakete wie erwartet ankommen.

## Eigene Pakete aufnehmen

1. Öffne den Bereich `Aufnahme`.
2. Wähle eine vorhandene Sportart oder lege eine neue Sportart an.
3. Vergib optional einen Session-Namen.
4. Starte die Aufnahme auf dem gewünschten UDP-Port.
5. Sende Pakete von deinem Quellsystem an diesen Port.
6. Benenne relevante Pakete als Aktionen und ergänze bei Bedarf Notizen.
7. Stoppe die Aufnahme. Die Session steht danach lokal in der Bibliothek und in der Inspektionsansicht zur Verfügung.

## Sessions inspizieren

Im Bereich `Inspizieren` kannst du gespeicherte Aufnahmen nach Aktionen, Pakettypen, Fehlern und Duplikaten durchsuchen. Für einzelne Pakete zeigt die Anwendung den JSON-Inhalt und die erkannten Änderungen gegenüber dem vorherigen Paket desselben Typs.

## Datenhaltung und Datenschutz

Die Anwendung arbeitet lokal. Sie verwendet keine eingebaute Telemetrie, kein Analytics-SDK, keine Benutzerkonten und keinen automatischen Cloud-Upload. Aufgezeichnete UDP-Payloads können aber personenbezogene oder vertrauliche Inhalte enthalten, wenn solche Daten im empfangenen Paket stecken.

Details stehen in [PRIVACY.md](PRIVACY.md).

## Systemvoraussetzungen

- Windows 10 oder Windows 11.
- Lokaler Zugriff auf den gewünschten UDP-Port.
- Je nach Testaufbau eine Firewall-Freigabe für eingehende oder ausgehende UDP-Pakete.
- Keine Internetverbindung nach der Installation erforderlich, solange du keine neuen Releases herunterladen möchtest.

## Fehlerbehebung

- Keine Pakete kommen beim Zielsystem an: Zielhost, Zielport und Windows-Firewall prüfen.
- Keine Pakete werden aufgenommen: Prüfen, ob das Quellsystem an die richtige IP und den richtigen UDP-Port sendet.
- Autopilot ist nicht startbar: Die gewählte Session braucht mindestens eine annotierte Aktion und ein CLOCK-Template.
- Installer wird blockiert: Datei direkt aus den GitHub-Releases herunterladen und SmartScreen-Hinweis bewusst prüfen.
- Falsche Version installiert: Alte Version deinstallieren oder den Installer der neuesten Release-Seite verwenden.

## Release-Modell

Dieses Repository ist nur das öffentliche Download-Ziel. Der Quellcode wird in einem privaten Repository gepflegt. Bei einem neuen Versions-Tag baut GitHub Actions den Windows-Installer und veröffentlicht die Release-Dateien automatisch hier.

Ein normaler Commit in diesem Repository ist daher nur für öffentliche Begleitdateien wie dieses README gedacht. Neue Programmversionen erscheinen über die Seite [Releases](https://github.com/Dbro93/sportdata-pss-simulator-releases/releases).

## Hinweis

Dieses Projekt ist ein inoffizielles Werkzeug. Es besteht keine offizielle Verbindung, Freigabe oder Empfehlung durch Sportdata oder andere genannte Markeninhaber, sofern dies nicht ausdrücklich separat angegeben ist.

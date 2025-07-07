# Teil 1 Initialisierung

In diesem Kapitel wird ins Thema der Arbeit eingeführt. Es beschreibt den Hintergrund und die Relevanz des Themas. Sie definiert das Ziel der Arbeit und formuliert die zentralen Fragen. Zudem gibt die Initialisierung einen kurzen Überblick über den Aufbau der Arbeit um eine klare Orientierung zu bieten.

- [Teil 1 Initialisierung](#teil-1-initialisierung)
- [Versionenverzeichnis](#versionenverzeichnis)
- [Aufgabenstellung](#aufgabenstellung)
  - [Ausgangslage](#ausgangslage)
  - [Ziele](#ziele)
  - [Mittel und Methode](#mittel-und-methode)
    - [Sachmittel](#sachmittel)
    - [Programmiersprache](#programmiersprache)
  - [Werkzeuge](#werkzeuge)
  - [SCRUM-Überblick](#scrum-überblick)
  - [Defenition of Done](#defenition-of-done)
    - [Funktionale Umsetzung](#funktionale-umsetzung)
    - [Technische Qualität](#technische-qualität)
    - [Sicherheit \& Stabilität](#sicherheit--stabilität)
    - [Deployment](#deployment)
    - [Dokumentation](#dokumentation)
    - [Review \& Akzeptanz](#review--akzeptanz)
- [Projektorganisation](#projektorganisation)
  - [Beteiligte Personen](#beteiligte-personen)
    - [Kanditatin](#kanditatin)
    - [Dozenten](#dozenten)
- [Datensicherung](#datensicherung)

# Versionenverzeichnis

| Version | Datum  | Autor | Bemerkung | 
| ------- | ------ | ----  | --------- |
| 1.0 | 05.05.2025 | Laura Dubach | Repo, Struktur erstellen |
| 1.1 | 06.05.2025 | Laura Dubach | Jira Zeitplan starten & Sprint Planning beginnen |
| 1.1 | 07.05.2025 | Laura Dubach | Jira Zeitplan & Sprint Planning fertigstellen, DoD erstellen |
| 1.2 | 08.05.2025 | Laura Dubach | Site Initialierung schreiben |
| 1.3 | 09.05.2025 | Laura Dubach | Sprint Abschluss schreiben und abschliessen |
| 1.4 | 13.05.2025 | Laura Dubach | Seusag starten & API Auswahl dokumentieren |
| 1.5 | 14.05.2025 | Laura Dubach | Seusag fertgstellen |
| 1.6 | 15.05.2025 | Laura Dubach | Abschnitt Entscheiden dokumentieren |
| 1.7 | 19.05.2025 | Laura Dubach | Ist & Soll, Implementierungsplan und Risikomatrix erstellen |
| 1.8 | 20.05.2025 | Laura Dubach | Ist & Soll, Implementierungsplan und Risikomatrix erstellen dokumentieren |
| 1.9 | 23.05.2025 | Laura Dubach | Site Konzeption fertigstellen |
| 2.0 | 26.05.2025 | Laura Dubach | Sprint Abschluss 2 schreiben und abschliessen |
| 2.1 | 28.05.2025 | Laura Dubach | Start mit Datenbank diagramm und Pipline, erste tests auf Github |
| 2.2 | 02.06.2025 | Laura Dubach | Sprint Abschluss 2 beendet |
| 2.3 | 03.06.2025 | Laura Dubach | Start Sprint 3, dokumentation vorbereiten |
| 2.4 | 04.06.2025 | Laura Dubach | Umsetzung starten |
| 2.5 | 20.06.2025 | Laura Dubach | Umsetzung fertigstellen |
| 2.6 | 23.06.2025 | Laura Dubach | Sprint Abschluss 3 |
| 2.7 | 25.06.2025 | Laura Dubach | Sprint Start 4, Umsetzung fertig dokumentieren, testing starten |
| 2.8 | 26.06.2025 | Laura Dubach | Tests dokumentieren |
| 2.9 | 02.07.2025 | Laura Dubach | Abschluss der Arbeit dokumentieren |
| 3.0 | 06.07.2025 | Laura Dubach | Letzter Sprint dokumentieren, korrektur Rechtschreibung |
| 3.1 | 07.07.2025 | Laura Dubach | Dokumentation fertigstellen |

# Aufgabenstellung

## Ausgangslage

In einer zunehmend vernetzten Welt sind personalisierte, ortsbezogene Event-Empfehlungen für Musikfans sehr gefragt. Bestehende Lösungen sind oft schwer erweiterbar oder bieten keine einfache Integration in bestehende Systeme.
Die Herausforderung besteht darin, einen eigenständigen Microservice zu entwickeln.

**Ambitioniert:** Die Entwicklung eines eigenständigen Services inklusive API-Anbindung, Filterlogik und Bereitstellung via REST ist anspruchsvoll, aber machbar.
**Motivierend:** Persönliches Interesse an Musik, Event-Technologien und Microservices.
**Organisiert:** APIs, Tools und Frameworks sind vorhanden oder beschaffbar.
**Realistisch:** Umfang und Zielsetzungen sind im Rahmen der verfügbaren Zeit gut umsetzbar.
**Echt:** Der Anwendungsfall ist realitätsnah und technologisch aktuell.

## Ziele

1.	Entwicklung eines lauffähigen Microservices mit REST-API zur Abfrage von Musikveranstaltungen
2.	AWS über eine Pipeline zur Verfügung stellen
3.	Anbindung an eine externe Event-API zur Datenbeschaffung
4.	Implementierung von Filterfunktionen
5.	Containerisierung mit Docker zur einfachen Bereitstellung
6.	Einbindung einer Datenbank zur Speicherung von Nutzerinformationen

## Mittel und Methode

### Sachmittel

- Unterrichtsressourcen
- Flask Dokumentationen
- Unterstützung der Dozenten

### Programmiersprache

- Python
- HTML

## Werkzeuge

- SCRUM
- ChatGPT
- Visual Studio Code
- PowerPoint
- Notion
- Docker Desktop
- API`s
- Flask
- Github
- AWS
- Jira

## SCRUM-Überblick

Im Rahmen der Entwicklung des Microservices für personalisierte, ortsbezogene Event-Empfehlungen wird SCRUM als agiles Projektmanagement-Framework eingesetzt, um strukturierte Fortschritte zu ermöglichen. Das Projekt wird in mehrere Sprints unterteilt, in denen jeweils konkrete Teilziele wie zum Beispiel die Anbindung der externen Event-API, die Entwicklung der Filterlogik oder die Integration der REST-API fokussiert, bearbeitet werden. Zu Beginn jedes Sprints erfolgt eine Sprintplanung, in der die anstehenden Aufgaben priorisiert und aufgeteilt werden. Nach jedem Sprint wird ein Review durchgeführt. Durch den Einsatz von SCRUM bleibt man flexibel und kann trotz der technischen Komplexität effektiv auf Veränderungen und Herausforderungen reagieren.

## Defenition of Done

Ein Product Backlog Item, gilt als "Done", wenn **alle** folgenden Kriterien erfüllt sind:

### Funktionale Umsetzung

- Die Funktionalität ist vollständig implementiert gemäß der User Story und den Akzeptanzkriterien.
- Die API-Endpunkte liefern valide, erwartete Ergebnisse.
- Filterlogiken und Datenbankzugriffe funktionieren korrekt.

### Technische Qualität

- Der Code wurde dokumentiert.
- Es existieren Tests.
- Es gibt keine kritischen oder offenen Bugs.

### Sicherheit & Stabilität

- Datenvalidierung wurde umgesetzt.
- Es wurden Sicherheitsaspekte berücksichtigt.
- Die Anwendung läuft stabil in Docker-Containern.

### Deployment

- Die Anwendung ist containerisiert (Docker) und funktionsfähig bereitgestellt.
- Die Anwendung wird über die CI/CD-Pipeline automatisch auf AWS deployt.
- Der Deployment-Status ist dokumentiert oder im Log nachvollziehbar.

### Dokumentation

- Das Feature ist in der technischen Projektdokumentation beschrieben.
- Änderungen sind nachvollziehbar.
- Bei Bedarf wurden Screenshots, Diagramme oder Abläufe ergänzt.

### Review & Akzeptanz

- Die Sprint Reviews sind alle Dokumentiert
- Die Reflexion ist verständlich.
- Die Funktionalität ist im Product Backlog als „Done“ markiert.

# Projektorganisation

## Beteiligte Personen

### Kanditatin

```
Laura Joana Dubach
Funktion: Projektleiterin
P: 079 355 78 24
Github: lauradubach
Business E-Mail: laura.dubach@itnetx.ch
School E-Mail: laura.dubach@edu.tbz.ch
```
### Dozenten

```
Parisi Corrado
Funktion: PRJ-Dozent
Github: corrado-parisi
E-Mail: corrado.parisi@tbz.ch
```
```
Langer Boris
Funktion: Fachdozent
Github: lab-bo
E-Mail: boris.langer@tbz.ch
```

# Datensicherung

Damit keine Daten verloren gehen, werde ich alle Dokumente auf meinem OneDrive abspeichern. Durch das Pushen ins Github, wird dies ja auch in der Cloud gesichert. Zusätzlich werde ich die Daten auf einen USB-Stick abspeichern, damit ich im Worstcase Szenario ein Backup besitze.


> Back [Page](https://lauradubach.github.io/Semesterarbeit3/)
>
> Next [Page](https://lauradubach.github.io/Semesterarbeit3/Sites/Teil%202%20Konzeption.html)
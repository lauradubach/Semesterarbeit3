# Teil 2 Konzeption

Nun gehen wir ins Thema Konzeption über. In diesem Kapitel wird das ganze Projekt vorbereitet. Die Ausgangslage und Anforderungen werden beschrieben, auch was das Ziel des Projektes ist, wird aufgezeigt. Die Planung wird gemacht und es werden Entscheidungen getroffen um das Projekt mit den Optimalen Tools umzusetzten.

- [Teil 2 Konzeption](#teil-2-konzeption)
- [Informieren](#informieren)
  - [Was ist SCRUM?](#was-ist-scrum)
    - [Die wichtigsten Merkmale](#die-wichtigsten-merkmale)
    - [Die zentralen Rollen](#die-zentralen-rollen)
    - [Die wichtigsten Ereignisse (Events)](#die-wichtigsten-ereignisse-events)
    - [Zentrale Artefakte](#zentrale-artefakte)
    - [Wieso SCRUM](#wieso-scrum)
  - [Ausgangslage \& Motivation](#ausgangslage--motivation)
  - [Anforderungen erheben](#anforderungen-erheben)
  - [Relevanz und Nutzen eines Event-Finders](#relevanz-und-nutzen-eines-event-finders)
  - [Seusag](#seusag)
    - [Enthaltene Elemente (Included)](#enthaltene-elemente-included)
      - [Userinterface](#userinterface)
      - [Flask](#flask)
      - [Datenbank](#datenbank)
      - [SQLAlchemy](#sqlalchemy)
      - [Docker](#docker)
      - [Git](#git)
    - [Externes System](#externes-system)
      - [EC2 (AWS)](#ec2-aws)
      - [Ticketmaster API](#ticketmaster-api)
    - [Komponenten (Component)](#komponenten-component)
      - [Pipeline](#pipeline)
    - [Ausgeschlossene Elemente (Excluded)](#ausgeschlossene-elemente-excluded)
      - [Echtzeitverarbeitung](#echtzeitverarbeitung)
      - [Rechtekonzept](#rechtekonzept)
      - [Produktive Veröffentlichung](#produktive-veröffentlichung)
      - [Support](#support)
      - [Eigenentwicklung von Eventdaten](#eigenentwicklung-von-eventdaten)
- [Planen](#planen)
  - [Zeitplan](#zeitplan)
  - [Meilensteine](#meilensteine)
    - [Initialisierung](#initialisierung)
    - [Konzeption](#konzeption)
    - [Realisieren](#realisieren)
    - [Abschluss](#abschluss)
  - [Ist und Soll](#ist-und-soll)
    - [Ist Zustand](#ist-zustand)
    - [Soll Zustand](#soll-zustand)
  - [Grobplanung Microservice Design](#grobplanung-microservice-design)
  - [Risikomatrix](#risikomatrix)
    - [Technische Risiken](#technische-risiken)
    - [Organisatorische Risiken](#organisatorische-risiken)
    - [Sicherheitsrisiken](#sicherheitsrisiken)
    - [Abhängigkeiten und externe Faktoren](#abhängigkeiten-und-externe-faktoren)
  - [Implementierungsplan](#implementierungsplan)
- [Entscheiden](#entscheiden)
  - [Technologieentscheidungen](#technologieentscheidungen)
    - [Warum Docker?](#warum-docker)
    - [Warum AWS?](#warum-aws)
    - [Datenbank (MariaDB vs. MySQL)](#datenbank-mariadb-vs-mysql)
      - [Vergleich: MariaDB vs. MySQL](#vergleich-mariadb-vs-mysql)
      - [Entscheidungsmatrix](#entscheidungsmatrix)
  - [API-Auswahl](#api-auswahl)


# Informieren

In diesem Kapitel werde ich alle Informationen zusammentragen, um das Projekt umsetzten zu können.

## Was ist SCRUM?

SCRUM ist ein agiles Rahmenwerk (Framework) für Projektmanagement, das vor allem in der Softwareentwicklung eingesetzt wird. Es hilft Teams, komplexe Projekte schrittweise zu bearbeiten und regelmäßig Ergebnisse zu liefern.

### Die wichtigsten Merkmale

- Iterativ und inkrementell: Die Arbeit wird in festen Zeitabschnitten, sogenannten Sprints (meist 2–4 Wochen), erledigt.
- Transparenz, Überprüfung und Anpassung: Nach jedem Sprint wird das Ergebnis vorgestellt und gegebenenfalls der Plan angepasst.

### Die zentralen Rollen

- Product Owner – Verantwortlich für das Produkt und dessen Anforderungen (Pflege des Product Backlogs).
- Scrum Master – Unterstützt das Team, entfernt Hindernisse und sorgt für die Einhaltung von SCRUM.
- Entwicklungsteam – Umsetzt die Anforderungen und liefert am Ende eines Sprints ein fertiges Produktinkrement.

### Die wichtigsten Ereignisse (Events)

- Sprint Planning – Planung, was im kommenden Sprint erreicht werden soll.
- Daily Scrum – Tägliches 15-Minuten-Meeting zur Abstimmung.
- Sprint Review – Vorstellung der Ergebnisse am Sprintende.
- Sprint Retrospective – Rückblick auf den Sprint zur Prozessverbesserung.

### Zentrale Artefakte

- Product Backlog – Liste aller Anforderungen an das Produkt.
- Sprint Backlog – Auswahl der Aufgaben für den aktuellen Sprint.
- Increment – Das am Ende eines Sprints fertige und getestete Produktstück.

> (Chat GPT) [Quelle](https://chatgpt.com/share/6818f168-0354-800e-8c00-119b2ed7c509)

### Wieso SCRUM

Ich habe mich bewusst für SCRUM als Vorgehensmodell entschieden, weil es ein etabliertes, agiles Framework ist. SCRUM ermöglicht es, in kurzen Zyklen (Sprints) kontinuierlich funktionsfähige Ergebnisse zu liefern, die regelmäßig überprüft und angepasst werden können.

Durch die klare Struktur, regelmäßigen Events (Sprint Planning, Sprint Review, Retrospektive) und einem fokussierten Backlog-Management entsteht ein hohes Maß an Transparenz, Planbarkeit und Flexibilität.

Ein weiterer entscheidender Vorteil von SCRUM ist die enge Einbindung von Feedback. So kann frühzeitig auf Veränderungen oder neue Erkenntnisse reagiert werden, ohne die gesamte Projektplanung überarbeiten zu müssen. Das fördert eine nutzerzentrierte Entwicklung und reduziert das Risiko, am Bedarf vorbei zu arbeiten.

Zusätzlich haben wir im Unterricht SCRUM Theoretisch angeschaut und nun kann ich es Praktisch lernen umzusetzten.

> (Chat GPT) [Quelle](https://chatgpt.com/share/68230b9b-2d9c-800e-a1eb-64bd9fe8ed96)


## Ausgangslage & Motivation

In Zeiten zunehmender Digitalisierung und Vernetzung steigt das Bedürfnis nach personalisierten Diensten. Musikliebhaber:innen suchen gezielt nach Veranstaltungen, die ihren Interessen entsprechen und gleichzeitig gut erreichbar sind. Der Markt bietet zwar verschiedene Event-Plattformen, doch häufig fehlt es an einer modularen, leicht integrierbaren Lösung, die als eigenständiger Microservice betrieben werden kann.
Diese Lücke soll durch die Entwicklung eines Microservices geschlossen werden, der gezielt ortsbezogene Event-Empfehlungen im Musikbereich ermöglicht. Die persönliche Affinität zur Thematik, das Interesse an Microservice-Architekturen und der technologische Reiz motivieren zusätzlich zur Umsetzung des Vorhabens.

## Anforderungen erheben

Für die Entwicklung eines effektiven Event-Finders sind verschiedene funktionale und nicht-funktionale Anforderungen zu berücksichtigen:

Funktionale Anforderungen:

- REST-API zur Abfrage von Musikveranstaltungen
- Anbindung an eine externe Event-API (z. B. Ticketmaster, Eventbrite)
- Filteroptionen nach Ort, Datum, Genre, etc.
- Speicherung und Verwaltung von Nutzerinformationen
- Personalisierte Empfehlungen auf Basis von Nutzerpräferenzen

Nicht-funktionale Anforderungen:

- Bereitstellung über eine CI/CD-Pipeline in AWS
- Containerisierung mit Docker für einfache Skalierbarkeit und Portabilität
- Skalierbare, wartbare Architektur (Microservice-Prinzip)
- Sichere und DSGVO-konforme Datenverarbeitung

## Relevanz und Nutzen eines Event-Finders

Ein Event-Finder bietet für Nutzer/innen einen klaren Mehrwert: Statt selbst mühsam nach Veranstaltungen zu suchen, erhalten sie gezielte, persönliche Empfehlungen abgestimmt auf Standort, Musikgeschmack und Verfügbarkeit.
Auch für Plattformbetreiber oder Drittanbieter ist der Microservice interessant: Dank seiner modularen Architektur lässt er sich flexibel in bestehende Systeme integrieren. So entstehen neue Möglichkeiten für personalisiertes Marketing, datenbasierte Entscheidungen und Nutzerbindung.
Der Einsatz moderner Technologien wie Docker, REST-APIs und Cloud-Deployment sorgt zudem für Zukunftsfähigkeit und erleichtert die Wartung sowie Weiterentwicklung des Systems.

> (Chat GPT) [Quelle](https://chatgpt.com/share/681ca14f-3adc-800e-999e-442e39898a6b)

## Seusag

![SEUSAG](../Pictures/SEUSAG.png)

### Enthaltene Elemente (Included)

#### Userinterface
Das User Interface dient zur Visualisierung der API-Endpunkte. Es wird als einfache Web-Oberfläche fungieren, die Suchparameter an das Backend weitergibt.

#### Flask
Das Backend-Framework bildet das zentrale Element des Microservices. Es implementiert die REST-API, verarbeitet Anfragen, leitet sie an die Filterlogik weiter und koordiniert alle internen Prozesse.

#### Datenbank
Hier werden Benutzerinformationen, Präferenzen oder Filtereinstellungen, gespeichert. Eine relationale Datenbank ist über SQLAlchemy angebunden.

#### SQLAlchemy
Es ermöglicht eine objektorientierte Datenbankanbindung und erleichtert Datenmanipulation und -abfragen.

#### Docker
Zur Containerisierung des Services wird Docker eingesetzt. Damit ist der Microservice unabhängig von der Umgebung lauffähig, lokal oder in der Cloud (AWS EC2).

#### Git
Der Code wird versionsverwaltet mit Git. Dies ermöglicht saubere Entwicklungsprozesse, Branching und Pull Requests.

### Externes System

#### EC2 (AWS)
Der Microservice wird auf einem Amazon EC2-Server deployed. EC2 stellt eine skalierbare Cloud-Infrastruktur für den produktionsnahen Betrieb des Containers bereit.

#### Ticketmaster API
Diese externe Event-API liefert Eventdaten. Sie wird konsumiert, aber nicht beeinflusst oder erweitert. Andere APIs könnten ebenfalls eingebunden werden.

### Komponenten (Component)

#### Pipeline
Die Pipeline automatisiert den Build-, Test- und Deploymentprozess. Bei jedem Commit oder Merge kann die Anwendung automatisch gebaut, getestet und auf EC2 ausgerollt werden.

### Ausgeschlossene Elemente (Excluded)

#### Echtzeitverarbeitung
Der Service arbeitet nicht mit Live-Datenströmen. Daten werden per Anfrage oder geplanten Intervallen abgerufen – keine Echtzeit-Ereignisverarbeitung.

#### Rechtekonzept
Es wird kein Rollen- oder Berechtigungsmanagement umgesetzt. Alle Anfragen werden als gleichberechtigte Benutzer behandelt einfache API-Nutzung ohne Benutzerrollen.

#### Produktive Veröffentlichung
Der Service wird nicht öffentlich zugänglich gemacht oder als dauerhaft produktiv betrieben. Die Veröffentlichung dient nur zu Demonstrations- und Evaluierungszwecken.

#### Support
Es wird kein laufender Benutzersupport oder operativer Betrieb vorgesehen. Fokus liegt auf technischer Umsetzung und Nachweis der Funktionalität.

#### Eigenentwicklung von Eventdaten
Es werden keine eigenen Eventdaten gepflegt oder manuell eingegeben. Alle Eventinformationen stammen ausschließlich aus der angebundenen Drittanbieter-API.

# Planen

Hier werde ich das ganze Projekt planen. Es wird ein Zeitplan erstellt, wann welche Tätigkeiten fällig sind und die Meilensteine sind genau beschrieben.

## Zeitplan

![Zeitplan](../Pictures/Zeitplan.png)

## Meilensteine
### Initialisierung

In der Initialisierungsphase wird das Projekt offiziell gestartet. Ziel ist es, eine klare Projektgrundlage zu schaffen. Dazu gehören die Definition von Zielen, die Identifikation von Stakeholdern, die grobe Planung (Zeit, Budget, Ressourcen) sowie die Erstellung eines Projektauftrags. Risiken und Chancen werden frühzeitig analysiert, und es wird geprüft, ob das Projekt wirtschaftlich und realistisch durchführbar ist.

### Konzeption

In dieser Phase wird das Projekt inhaltlich konkretisiert. Anforderungen werden detailliert erhoben und dokumentiert (z. B. als User Stories), Lösungsansätze erarbeitet und bewertet. Es entsteht ein Fach- und ggf. ein technisches Konzept, das die Grundlage für die spätere Umsetzung bildet.

### Realisieren

Jetzt beginnt die eigentliche Umsetzung: Entwicklung, Konfiguration, Tests und Integration der Komponenten. Die Arbeit erfolgt meist iterativ (z. B. in Sprints), um regelmäßig funktionierende Zwischenstände zu liefern. Parallel erfolgt oft auch die Vorbereitung von Schulungen und die Erstellung von Benutzerdokumentationen.

### Abschluss

Das Projekt wird formal beendet. Es finden eine Abnahme, eine Übergabe an den Betrieb sowie ggf. eine Schulung der Nutzer statt. Außerdem werden Lessons Learned dokumentiert, um aus dem Projekt für zukünftige Vorhaben zu lernen.

## Ist und Soll

![Ist&Soll](../Pictures/Ist&Soll.png)

### Ist Zustand

Aktuell existiert kein spezialisierter Service zur personalisierten, ortsbezogenen Event-Empfehlung für Musikfans. Zwar gibt es verschiedene Plattformen mit Eventdaten, jedoch fehlt eine flexible, erweiterbare Lösung mit integrierter Nutzerlogik, Filterfunktionen und einfacher API-Anbindung. Eine Cloud-Deployment-Strategie sowie automatisierte Containerbereitstellung und Nutzerdatenhaltung sind ebenfalls noch nicht vorhanden.

### Soll Zustand

Ziel ist die Entwicklung eines eigenständigen Microservices, der Musikveranstaltungen über eine REST-API verfügbar macht. Der Service soll externe Event-APIs anbinden, Daten filtern und personalisieren können sowie Nutzerdaten in einer angebundenen Datenbank verwalten. Die Bereitstellung erfolgt containerisiert via Docker und automatisiert über eine Deployment-Pipeline auf AWS. Der Service soll modular, wartbar und sicher konzipiert sein.

## Grobplanung Microservice Design

Spezifizierung Microservice:

- Event-Service: Holt Musikveranstaltungen über eine externe Event-API.
- User-Service: Verwaltet Nutzerinformationen und -präferenzen.
- Recommendation-Service: Wendet Filterlogik an und erzeugt personalisierte Empfehlungen.
- API-Gateway (optional): Dient als zentraler Zugangspunkt für Clients.

## Risikomatrix

![Risikomatrix](../Pictures/Risikomatrix.png)

### Technische Risiken

| Risiko | Eintritt | Auswirkung | Risikobewertung (Matrixfeld) | Gegenmaßnahmen |
|--------|----------|------------|-------------------------------|----------------|
| Externe API nicht erreichbar oder ändert sich | Mittel | Hoch | **High: 12** | Fallback-Strategie, Fehlerbehandlung, API-Abstraktion, regelmäßige Tests |
| Fehlkonfiguration von Docker/Deployment | Mittel | Mittel-Hoch | **High: 8** | Tests in dev/staging-Umgebung, automatisiertes Deployment, Logging |
| Performanceprobleme bei vielen API-Abfragen | Niedrig-Mittel | Mittel | **Medium: 5** | Caching einführen, Limitierung von Abfragen, asynchrone Verarbeitung |

### Organisatorische Risiken

| Risiko | Eintritt | Auswirkung | Risikobewertung (Matrixfeld) | Gegenmaßnahmen |
|--------|----------|------------|-------------------------------|----------------|
| Zeitüberschreitung | Mittel | Hoch | **High: 11** | Agile Planung (z. B. Sprints), MVP-Fokus, Priorisierung |
| Unklare Anforderungen | Mittel | Mittel | **Medium: 5** | Lasten-/Pflichtenheft erstellen, regelmäßige Reviews |
| Fehlende Dokumentation | Hoch | Mittel | **High: 7** | Kontinuierliche Dokumentation, klare Kommentare, README aktuell halten |

### Sicherheitsrisiken

| Risiko | Eintritt | Auswirkung | Risikobewertung (Matrixfeld) | Gegenmaßnahmen |
|--------|----------|------------|-------------------------------|----------------|
| Unzureichender Schutz der Nutzerinformationen | Niedrig-Mittel | Hoch | **High: 11** | Einsatz sicherer Verbindung (HTTPS), DB-Zugriffsrechte einschränken, Validierung und Verschlüsselung |
| API Key-Leakage | Mittel | Hoch | **High: 11** | `.env`-Dateien nutzen, `.gitignore`, Secrets nie im Klartext speichern |

### Abhängigkeiten und externe Faktoren

| Risiko | Eintritt | Auswirkung | Risikobewertung (Matrixfeld) | Gegenmaßnahmen |
|--------|----------|------------|-------------------------------|----------------|
| Änderungen an externen APIs | Mittel | Mittel-Hoch | **High: 8** | Nutzung von API-Wrappers, API-Versionierung beachten, Monitoring der Schnittstellen |
| Cloud-Service-Probleme (z. B. AWS) | Niedrig | Mittel | **Medium: 4** | Monitoring einrichten, regelmäßige Backups, alternative Deploymentmöglichkeit vorbereiten |


## Implementierungsplan

Hier wird grob dargestellt, wie in diesem Projekt vorgegangen wird.

![Implementierungsplan](../Pictures/Implementierungsplan.png)

Der Implementierungsplan für den Event-Microservice zeigt die sieben Hauptschritte, die für die erfolgreiche Umsetzung notwendig sind. Jeder dieser Schritte ist essenziell für das Gesamtprodukt kein Schritt kann ausgelassen werden, da sie aufeinander aufbauen und zusammen die Funktionsfähigkeit, Sicherheit und Wartbarkeit des Systems gewährleisten.

# Entscheiden

## Technologieentscheidungen

### Warum Docker?

Docker ermöglicht es, den entwickelten Microservice in einem standardisierten Container-Format bereitzustellen. Dadurch ist sichergestellt, dass die Anwendung in verschiedenen Umgebungen – lokal, in der Cloud oder auf CI/CD-Systemen – zuverlässig und konsistent läuft.
Für dieses Projekt bedeutet das: Der Service lässt sich leicht testen, in Pipelines integrieren und auf verschiedenen Systemen ausrollen, ohne dass lokale Abhängigkeiten berücksichtigt werden müssen.

### Warum AWS?

AWS bietet eine skalierbare und zuverlässige Cloud-Infrastruktur, die sich gut für die Bereitstellung von Microservices eignet.
In Bezug auf dieses Projekt: AWS erlaubt es, die Anwendung realitätsnah bereitzustellen. Inklusive automatischer Skalierung, Ausfallsicherheit und Integration in bestehende CI/CD-Pipelines. Außerdem ist AWS im professionellen Umfeld weit verbreitet, was die Lösung zukunftsfähig und praxisnah macht.

### Datenbank (MariaDB vs. MySQL)

Für meinen Microservice zur ortsbezogenen Event-Empfehlung für Musikfans ist die Auswahl der geeigneten relationalen Datenbank entscheidend. Zur Auswahl stehen **MariaDB** und **MySQL**. Beide sind SQL-basierte Systeme mit ähnlichem Ursprung, unterscheiden sich aber in Lizenzierung, Kompatibilität, Performance und Integration in moderne Cloud-Umgebungen.

#### Vergleich: MariaDB vs. MySQL

| Kriterium                    | MariaDB                                           | MySQL                                            |
|------------------------------|-------------------------------------------------- |--------------------------------------------------|
| **Lizenzierung**             | Open Source (GPL)                                 | Oracle-eigen (Open Core-Modell)                  |
| **Kompatibilität mit MySQL** | Hoch (Drop-in Replacement für MySQL 5.7)          | Originalsystem                                   |
| **Performance**              | Besser bei bestimmten Abfragen (z. B. JOINs, CTEs)| Stabil, aber tendenziell konservativer           |
| **Funktionen**               | Mehr Storage Engines (z. B. Aria, ColumnStore)    | Fokus auf Standardfeatures, v. a. InnoDB         |
| **Zukunftssicherheit**       | Open-Source-getrieben, langsameres Adoptionstempo | Wird von Oracle aktiv weiterentwickelt           |
| **Community**                | Community-getrieben, engagiert                    | Starke Community, viele Ressourcen verfügbar     |
| **SQLAlchemy-Unterstützung** | Gut, gelegentlich kleinere Inkompatibilitäten     | Sehr gut und stabil                              |
| **AWS-Kompatibilität**       | Möglich über RDS (MariaDB wird unterstützt)       | Bessere Integration (Amazon RDS, Aurora MySQL)   |
| **Release-Frequenz**         | Häufiger, mehr neue Features                      | Stabiler, konservativer Release-Zyklus           |
| **Stabilität für Produktion**| Sehr gut                                          | Sehr gut                                         |

#### Entscheidungsmatrix

| Kriterium                 | Gewichtung (1–5) | MariaDB (1–5)  | MySQL (1–5)  | MariaDB × G  | MySQL × G |
|-------------------------  |------------------|----------------|--------------|--------------|-----------|
| Kompatibilität SQLAlchemy | 5                | 4              | 5            | 20           | 25        |
| AWS-Integration           | 5                | 4              | 5            | 20           | 25        |
| Open Source / Lizenz      | 3                | 5              | 3            | 15           | 9         |
| Performance & Features    | 3                | 4              | 3            | 12           | 9         |
| Community / Support       | 2                | 4              | 5            | 8            | 10        |
| Stabilität                | 4                | 4              | 5            | 16           | 20        |
| **Gesamt**                |                  |                |              | **91**       | **98**    |

MySQL ist die passendere Wahl für dieses Projekt, weil:

- Es eine bessere Integration in AWS bietet.
- Die Kompatibilität mit SQLAlchemy ist stabiler und erprobt.
- MySQL ist ein etablierter Standard und in produktiven Umgebungen weit verbreitet.
- Für einen stabilen, realitätsnahen Microservice mit REST-API ist MySQL eine sichere und zukunftssichere Wahl.

> (Chat GPT) [Quelle](https://chatgpt.com/share/6825edd5-4508-800e-9e48-337a47b9a07e)

## API-Auswahl

Im Rahmen der Vorbereitung zur Anbindung einer Event API wird eine gezielte Marktanalyse durchgeführt, um geeignete Schnittstellen für die Eventdaten-Integration zu identifizieren und zu vergleichen. Ziel war es, eine API-Lösung auszuwählen, die zuverlässig, gut dokumentiert und für die geplanten Anwendungsfälle geeignet ist.

Im Vergleich standen unter anderem die Ticketmaster API und die Eventbrite API. Beide APIs bieten umfangreiche Daten zu Veranstaltungen, jedoch unterschieden sie sich in mehreren Aspekten:

| Kriterium             | Ticketmaster API                                           | Eventbrite API                                             |
|-----------------------|------------------------------------------------------------|------------------------------------------------------------|
| Datenbasis            | Große, internationale Event-Datenbank                      | Fokus auf lokale, kleinere Veranstaltungen                 |
| Dokumentation         | Sehr gut strukturiert und umfassend                        | Gut, mit vielen Beispielen                                 |
| Filtermöglichkeiten   | Umfangreich (Ort, Genre, Datum usw.)                       | Eingeschränkter Umfang                                     |
| Performance           | Sehr zuverlässig und performant                            | Variiert, abhängig von Umfang und Abfrage                  |
| Authentifizierung     | API-Key erforderlich, teilweise Registrierung für Details  | Einfache Authentifizierung                                 |
| Datenqualität         | Hoch, insbesondere bei Großveranstaltungen                 | Schwankend je nach Region und Veranstalter                 |
| Eventkategorien       | Breites Spektrum, gut strukturiert                         | Stärker auf Community-Events fokussiert                    |

Auf Basis dieser Analyse fiel die Entscheidung zugunsten der Ticketmaster API, da sie besser zu den Projektanforderungen in Bezug auf Datenqualität, Eventkategorien und internationale Verfügbarkeit passt.

> (Chat GPT) [Quelle](https://chatgpt.com/share/681cb603-08cc-800e-aab1-fdd14d015179)


> Back [Page](https://github.com/lauradubach/Semesterarbeit3/blob/main/Sites/Teil%201%20Initialisierung.md)
>
> Next [Page](https://github.com/lauradubach/Semesterarbeit3/blob/main/Sites/Teil%203%20Realisierung.md)
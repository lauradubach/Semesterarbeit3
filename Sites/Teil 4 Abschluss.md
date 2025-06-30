# Teil 4 Abschluss

Der letzte Teil der Arbeit. Hier wird die ganze Auswertung des Projektes beschrieben. Eine Selbstreflexion und die ganzen Anhänge und Quellen sind hier dokumentiert.

- [Teil 4 Abschluss](#teil-4-abschluss)
- [Auswerten](#auswerten)
  - [Zusammenfassung](#zusammenfassung)
  - [Reflexion](#reflexion)
    - [Persönliche Reflexion](#persönliche-reflexion)
      - [Herausforderungen und Lösungen](#herausforderungen-und-lösungen)
    - [Reflexion der technischen Umsetzung](#reflexion-der-technischen-umsetzung)
      - [Analysen und Planung](#analysen-und-planung)
      - [Entscheidung](#entscheidung)
      - [Umsetzung des Projektes](#umsetzung-des-projektes)
      - [Optimierung](#optimierung)
    - [Fazit](#fazit)
      - [Effizienzsteigerung](#effizienzsteigerung)
      - [Lernerfahrungen](#lernerfahrungen)
    - [Mögliche Weiterentwicklung](#mögliche-weiterentwicklung)
      - [Erweiterte Funktionalität](#erweiterte-funktionalität)
      - [Skalierbarkeit und Performance](#skalierbarkeit-und-performance)
  - [Quellen](#quellen)

# Auswerten

Im Kapitel Auswerten wird der Abschluss des Projektes beschrieben. Es wird Zusammengefasst, Reflektiert und Analysiert. Auch alle Quellen die verwendet wurden, werden angehängt.

## Zusammenfassung

Im Rahmen des Projekts wurde ein funktionsfähiger Microservice mit einer REST-API zur Abfrage von Musikveranstaltungen erfolgreich entwickelt. Die Anwendung greift über eine angebundene externe Event-API auf Veranstaltungsdaten zu und bietet umfangreiche Filterfunktionen zur gezielten Suche.
Zur effizienten Bereitstellung wurde der Microservice containerisiert und über Docker ausgeführt. Die Auslieferung erfolgt automatisiert über eine Deployment-Pipeline auf AWS. Zusätzlich wurde eine Datenbank integriert, um Nutzerinformationen dauerhaft zu speichern und eine personalisierte Nutzung zu ermöglichen.
Das Projekt vereint moderne Webtechnologien, Cloud-Infrastruktur und API-Integration zu einem skalierbaren, modular aufgebauten Gesamtsystem.
 
## Reflexion

### Persönliche Reflexion

Insgesamt bin ich mit dem Verlauf des Projekts sehr zufrieden. Ich konnte alle geplanten Aufgaben erfolgreich umsetzen und habe ein funktionierendes System erstellt, das Musikveranstaltungen über eine externe API abfragt. Die Projektumsetzung war allerdings anspruchsvoller als erwartet, insbesondere die technischen Herausforderungen beim Programmieren stellten sich als deutlich komplexer heraus. In diesen Phasen habe ich gezielt die Unterstützung des Dozenten genutzt, was mir sehr geholfen hat. Durch diese Zusammenarbeit konnte ich viele Hürden überwinden und mein technisches Verständnis weiter ausbauen.
Die Zeitplanung war grundsätzlich gut, aber durch die ungeplanten Schwierigkeiten geriet ich zwischenzeitlich etwas unter Druck. In Zukunft möchte ich Pufferzeiten besser einplanen und potenzielle Risiken früher berücksichtigen.

#### Herausforderungen und Lösungen

Während der Entwicklung traten mehrere technische Probleme auf – insbesondere beim Zusammenspiel von externer API, Datenbank und Authentifizierung. Durch systematisches Debugging, gezieltes Logging und schrittweise Vereinfachung des Codes konnten die Probleme identifiziert und gelöst werden.
 
### Reflexion der technischen Umsetzung

#### Analysen und Planung

Zu Beginn des Projekts analysierte ich, wie ein Event-Microservice sinnvoll aufgebaut werden kann, um Benutzerinteraktionen mit einer externen Event-API zu ermöglichen. Ich habe Anforderungen definiert, die Datenquellen geprüft und frühzeitig entschieden, welche Funktionen (z. B. Filterung, Nutzerfavoriten) umgesetzt werden sollen.
Die Planung erfolgte orientiert SCRUM, die ich in Jira dokumentiert habe.

#### Entscheidung

Für die Umsetzung entschied ich mich für eine REST-basierte Architektur, containerisiert mit Docker. Als Eventdatenquelle wählte ich die Ticketmaster-API, da sie ein umfangreiches Angebot und gute Filtermöglichkeiten bietet. Die Datenbank wurde so gewählt, dass sie Nutzerinformationen zuverlässig speichern kann. Diese Entscheidungen basierten auf technischer Eignung, Machbarkeit und Erweiterbarkeit.

#### Umsetzung des Projektes

Der Microservice wurde vollständig mit Flask umgesetzt und über Docker containerisiert. Er bietet eine grafische Benutzeroberfläche zur Eventsuche mit Filtermöglichkeiten (z.b nach Genre, Ort oder Künstler). Die Anbindung an die externe API und die Einbindung einer Nutzer-Datenbank waren zentrale Bestandteile.
Während der Implementierung kam es zu mehreren Herausforderungen, insbesondere bei der Datenverarbeitung der externen API und der Synchronisation zwischen Backend und UI. Durch gezielte Recherche, Hilfestellung vom Dozenten und aktives Troubleshooting konnten diese Probleme gelöst werden.

#### Optimierung

Nach Fertigstellung führte ich Tests zur Funktionalität, API-Stabilität und Datenkonsistenz durch. Außerdem optimierte ich die Code-Struktur, um zukünftige Erweiterungen zu erleichtern. Die wichtigsten Probleme wurden dokumentiert und für spätere Verbesserungen vorgemerkt.
 
### Fazit

#### Effizienzsteigerung

Der Microservice ermöglicht eine schnelle und gezielte Suche nach Musikveranstaltungen. Durch die Automatisierung der API-Abfragen, Filterfunktionen und Nutzerfavoriten wird der manuelle Aufwand stark reduziert. Die containerisierte Bereitstellung über AWS erhöht zudem die Skalierbarkeit und Wiederverwendbarkeit des Systems.

#### Lernerfahrungen

Ich habe viel über API-Integration, Docker-Containerisierung, Flask-Anwendungen und Deployment-Prozesse gelernt. Besonders der Umgang mit externen Datenquellen und die Fehleranalyse bei API-Requests waren lehrreich. Auch die Bedeutung einer sauberen Zeitplanung und Risikoabschätzung wurde mir noch bewusster. Das ganze Projekt war eine interessante und lehrreiche Erfahrung.
 
### Mögliche Weiterentwicklung

#### Erweiterte Funktionalität

In Zukunft könnten weitere Filteroptionen, z.b nach Preis oder Verfügbarkeit, ergänzt werden. Auch ein Login-System mit persönlicher Favoritenliste wurde angedacht und könnte weiter ausgebaut werden. Es könnte auch eine Google Maps integration eingebaut werden, die direkt die Eventlocation anzeigt.

#### Skalierbarkeit und Performance

Die Performance des Services könnte durch Caching von Eventdaten verbessert werden. Zudem wäre der Einsatz eines Frameworks wie FastAPI denkbar, um die Reaktionszeiten weiter zu optimieren.

## Quellen

Kapitel Informieren, Site Konzeption
Chat GPT. (2025): kannst du mir eine kurze erklärung zu SCRUM machen. Aufgerufen am: 05.05.2025. Online unter:
https://chatgpt.com/share/6818f168-0354-800e-8c00-119b2ed7c509

Kapitel Informieren, Site Konzeption
Chat GPT. (2025): kannst du mir für folgende arbeit..  diese punkte schreiben. Aufgerufen am: 08.05.2025. Online unter:
https://chatgpt.com/share/681ca14f-3adc-800e-999e-442e39898a6b

Kapitel Informieren, Site Konzeption
Chat GPT. (2025): kannst du mir einen text schreiben wieso ich mich für SCRUM entschieden habe. Aufgerufen am: 13.05.2025. Online unter: https://chatgpt.com/share/68230b9b-2d9c-800e-a1eb-64bd9fe8ed96

Kapitel Entscheiden, Site Konzeption
Chat GPT. (2025): kannst du mit die vor und nachteile angeben und dann eine entscheidungsmatrix generieren? was zu meiner arbeit passt natürlich. Aufgerufen am: 15.05.25. Online unter: https://chatgpt.com/share/6825edd5-4508-800e-9e48-337a47b9a07e

Kapitel Entscheiden, Site Konzeption
Chat GPT. (2025): kannst du mir hierzu einen text schreiben: Event API Recherche & Anbindung Vorbereiten. Aufgerufen am: 08.05.2025. Online unter: https://chatgpt.com/share/681cb603-08cc-800e-aab1-fdd14d015179


> Back [Page](https://lauradubach.github.io/Semesterarbeit3/Sites/Teil%203%20Realisierung.html)
>
> Back [Start](https://lauradubach.github.io/Semesterarbeit3/)
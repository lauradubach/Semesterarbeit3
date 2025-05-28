# Teil 3 Realisieren

- [Teil 3 Realisieren](#teil-3-realisieren)
- [Realisieren](#realisieren)
  - [Datenbank](#datenbank)
  - [Entwicklung](#entwicklung)
    - [Aufgetretene Probleme](#aufgetretene-probleme)
      - [Pipline](#pipline)
  - [Fallbacksolution](#fallbacksolution)
- [Kontrollieren](#kontrollieren)
  - [Testing](#testing)
    - [Testkonzept](#testkonzept)
    - [Testdurchführung](#testdurchführung)

# Realisieren

- Features, die umgesetzt wurden
- Herausforderungen & Lösungen
- REST-API Endpoints
- Docker-Setup
- Anbindung an externe API
- Datenbankdesign
- Filterfunktionen
- Codebeispiele (Auszüge)

## Datenbank

```mermaid
erDiagram
    users ||--o{ preferences : has
    users ||--o{ favorites : has
    events ||--o{ favorites : is_favorited_by

    users {
        int id PK
        string username
        string email
        string password_hash
        datetime created_at
    }

    preferences {
        int id PK
        int user_id FK
        string genre
        string artist
        string location
        datetime created_at
    }

    events {
        string id PK
        string title
        datetime date
        string location
        string genre
        string artist
        string external_url
        datetime created_at
    }

    favorites {
        int user_id FK
        string event_id FK
        datetime created_at
    }
```

## Entwicklung

Image location: https://github.com/lauradubach?tab=packages

### Aufgetretene Probleme

#### Pipline

zuerst access error -> es musste noch ein PAT token erstellt werden

nun kam folgender error:
![error1](../Pictures/Error1.png)

hier musste im  deploy job folgender Punkt ergänzt werden: `- uses: actions/checkout@v3`

## Fallbacksolution

# Kontrollieren

## Testing
### Testkonzept

| Testperson | Datum |
| ---------- | ----- |

| System | Testmittel | Testmethode |
| -------| ---------- | ----------- |

### Testdurchführung

| Testfall | Erwartetes Ergebnis | Testresultat |
| ---------| ------------------- | ------------ |



> Back [Page](https://github.com/lauradubach/Semesterarbeit3/blob/main/Sites/Teil%202%20Konzeption.md)
>
> Next [Page](https://github.com/lauradubach/Semesterarbeit3/blob/main/Sites/Teil%204%20Abschluss.md)
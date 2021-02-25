## Benutzte Technologien

### Backend: 
- REST
- NestJs
- MariaDB
- Docker
- Linux

### Frontend:
- Angular
- REST

## Arbeitspakete
- (Wissen aneignen)

## Scope
### Was bieten wir an
- Abstraktionsebene zwischen Geschäftskunden und Börse
- Algorithmisches Handeln für Geschäftskunden (?)
- Möglichkeiten zum Handeln
- Inklusive Quotes (?)
- Weiterleiten der Rabatte an die Liquiditätsspender (?)


optional:
- Statistiken (wer hat mit sienen Aktien wie viel Verlust gemacht)
- Anlagemöglichkeiten an Privatkunden (?)

### Schnittstelle zur Börse
- Kauforder / Verkaufsorder an Börse
- Aktuelle Kurse
- Alle Informationen zu Wertpapieren
- Rechnungen der Börse
- Schnittstelle zum Clearing

# Infos:
Handelsalgorithmus:
- z.B. unterteilen einer großen Order in viele kleine
-> Ab einem bestimmten Wert
-> Alle paar Minuten um nicht aufzufallen
-> Markt über wachen (was passiert, wenn ich etwas auf den Markt bringe?)
- Ein komplexer Algorithmus ist auch möglich
-> Vergleich zweier ähnlicher Aktien um das Verhalten des Marktes zu tracken
   -> z.B. RWE überwachen um E.ON zu handeln

Liquiditätsspender:
- Kaufen und Verkaufen an der Börse für einen höhere Liquidität
- Die Börse gibt an, welche Rabatte gelten
   - z.B. keine Gebühren beim Handeln
      - Dafür ist immer ein handelspartner da
   - Es müssen immer Quotes in einem bestimmten Rahmen vorhanden sein
   - z.B. etwa +- 20% um den Kurswert

Statistiken:
- Für Händler / Privatkunden
- Um wie viel war ich besser / schlechter als die Börse?
- VWAP => Besser / schlechter als Durchschnitttsmarkt
- Wie viel habe ich pro Aktie verdient / verloren?
- Vergleich von Händlern
- Je mehr Statistiken, desto besser

Anlagemöglichkeiten für Privatkunden:
- Privatkunden können über uns Geschäfte abwickeln
   - Bündeln von mehreren Privatkundenorders über uns
   - Da wir ein größeres Volumen handeln können wir Angebote für Privatkundenbroker machen
   - z.B. Anbieten von Fonds
   - Welche Gebühren nehmen wir im Verhältnis zu einzelnen Orders an der Börse?

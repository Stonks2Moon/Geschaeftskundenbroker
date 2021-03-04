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

# Prozess 
1. Anmeldung: Der Geschäftskunde kann sich bei uns anmelden / ein Konto anlegen
- Name des Ansprechpartners
- Anschrift
- Firmenname
2. Übersicht (Homepage)
- Ansehen aktueller Kurse, Übersicht Aktien, ETFs und andere Finanzprodukte
- Kurse und Statistiken der Aktien des eigenen Depots
- Kurse und Statistiken von beliebten Finanzprodukten (DAX)
4. Aktiensuche
- Suche nach bestimmten Aktien und Finanzprodukten (Freitextsuche, WKN/ISIN, Produkttyp)
- Kurse und Statistiken der Aktien der angezeigten Aktien
5. Kaufprozess
- Ordertyp
- Odervolumen
- Kaufpreis der Order
- Gebühren
- "Möchten Sie das wirklich kaufen?"
- Bestätigung der Erfolgreichen Ausführung
- Übergeben an die Börse
- Anzeigen der Aktie, sobald die Order ausgeführt wurde
- Bestätigung im Postfach + Handelshistorie
6. Verkaufen
- Das gleiche in grün


# Datenmodell
![ER-Diagramm](https://raw.githubusercontent.com/Stonks2Moon/Geschaeftskundenbroker/main/Documents/ER-Diagramm-Business-Broker.png)

# Prototyp 
[Hier](https://xd.adobe.com/view/0d38451e-9459-49e3-b3b2-283538fef009-586b/) findet ihr unseren AdobeXD Prototypen.

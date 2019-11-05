# Value-based pricing
## Wie man die Bepreisung von IT-Projekten anders fairer angehen kann

<br/>
<br/>
<small>Disclaimer: Wir schauen auf die IT-Bubble außerhalb der ansässigen Automobilindustrie.</small>

---
# Kurze Handmeldung: Wer hat schon einmal DLCs (Skins) gekauft?

---
# Wie kommt ein Angebot zustande?

- Kunde hat (mehr oder weniger) spezifische Anforderungen
- Eventuell Angebot über Anforderungsanalyse oder Discovery-Session
- Auftragnehmer sendet anhand des RfQs ein Angebot über Preis <em>x</em> an den Auftraggeber

---
# Wie entsteht der Preis?
- Erfahrung seitens des Auftragnehmers mit bisherigen, ähnlichen Projekten
	- Grundlage ist oft die vorher aufgewendete Zeit
- Interne Stundensätzen
	- Ausführlichen Excel-Tabellen
- Function Point Analyse
- Schwarze Magie / Würfel / rand()
- ...

---
# Was enthalten die Stundensätze?
- Lohnkosten
- Lohnnebenkosten zwischen 15 und 25% der Lohnkosten
- Kosten für die Unternehmung (Versicherungen, Gebäude, Strom, Steuerbüro ...)
- Gewinnbetrag
- Einbepreisung von Skonto und Einkaufsverhandlungen
- Marketing- und Vertriebsbudget
- und viele, viele andere Variablen

<p />
<small>Fließen in eure Stundensätze auch Weiterbildungen mit ein?</small>

---
## Time & Material
- Projekt dauert wahrscheinlich <em>y</em> Stunden und kostet pro Stunde € xx,xx
- Auftragnehmer kann mit einem Mindestumsatz von <em>y Stunden * € xx,xx</em> rechnen
- Kunde kann mit ungefähren Kosten kalkulieren, es kann aber auch völlig esaklieren
	- z. B. Mehrkosten von € 2.5 Mrd für Erneuerung der IT der Bundesverwaltung
	- Jeder kennt Beispiele aus seinen eigenen Projekten
	- <em>Zieht der Auftragnehmer mich über den Tisch?</em>

---
## Festpreis
- Projekt kostet <em>x</em> Euro, egal ob es 100 oder 1000 Stunden dauert
- Kunde weiß, was er am Ende zahlen muss
- Die Gefahr liegt beim Auftragnehmer
	- Klassiker: Scope Creep
	- Kunde kann die Zahlung herauszögern, falls Features subjektiv noch nicht fertig sind
	- <em>Warum kostet das bei Unternehmen xyz weniger?</em>
	- <em>Können wir noch € 5.000,00 runtergehen?</em>


---
## Agiler Festpreis
- Igendwas mit "agil" und wahrscheinlich Scrum. Dass muss gut sein.
- Anhand von Story Points, Business-Value und Risiken ergibt sich ein Festpreisrahmen pro User Story oder Sprint
- Überschreitung des Festpreises kann bspw. Kunden in Rechung gestellt werden
- Gefahren:
 	-  Wann ist ein Projekt oder eine User Story <strong>messbar</strong> fertig?
 	-  Gesamtkosten eher schwierig abzuschätzen. Kosten werden auf Auftragnehmer und Auftraggeber verteilt

---

## Kreativität

- *€ xx,xx* stehen als Budget pro Monat zur Verfügung
- *€ xx,xx* stehen als Budget pro Bugfix oder User Story bei einem Stundensatz von *€ yy,yy* zur Verfügung. Alles darüber muss genehmigt werden. Don't do it. Ever.
- Implementierung kostet pauschal *€ xx,xx* - alles über einem Aufwand von y Stunden wird mit einem Stundensatz von € xx,xx abgerechnet

---

# Grundsätzliches I

- Grundlage für den Preis war bisher immer das Verhältnis <em>Aufwand in Stunden</em> zu <em>Stundensatz</em>
- Pro Monat stehen als Arbeitnehmer ca. 160 Arbeitsstunden zur Verfügung
- Bei einem fiktiven Stundensatz von € 100,00 können also maximal € 16.000,00 fakturiert werden
- Wie soll das skalieren?
	- Nachtarbeit einführen
	- Arbeit in günstigere Länder delegieren
	- Mehr Sklaven!

---

## Grundsätzliches II
- Wie spiegelt sich der Aufbau von Wissen in den fakturierbaren Kosten wider?
- Wie oft ist schon bei T&M über Aufwände diskutiert worden?
	- <em>Warum hat das Feature X Stunden bei der Implementierung gedauert?</em>
	- <em>Also die Mehrkosten für X Stunden zahlen wir nicht.</em>
- Wieviel Zeit geht für die Pflege von Stundennachweisen in einem (<em>, zwei, drei</em>) Arbeitszeiterfassungssystemen drauf?

---

# Und nun zu etwas gänzlich Anderem...

---

# Leckere Tomaten-Mozzarella-Brötchen!

- € 2.30 für ein riesiges, belegtes Tomaten-Mozzarella-Brötchen
- Ich würde dafür mehr bezahlen.
- Mir als Kunde ist es das wert

---

# Skins in Spielen
- Ich würde kein Geld für einen APEX Battle Pass oder Counter-Strike-Skin ausgeben
- Aber andere hingegen schon.

--- 

# Der Wert eines Dings* liegt immer im Auge des Betrachters.
## Wie wichtig ist mir das und was ist es mir wert?


<small>* Software, Essen, Musik, Konferenzen ...</small>

---

# Value-based pricing

- Angebot auf Festpreisbasis
- Grundlage für die Bepreisung ist nicht mehr der zeitliche Aufwand, sondern der subjektive Wert des erwarteten Ergebnisses.

---

# Wie stelle ich den subjektiven Wert fest?
- Extrem offene Konversation mit dem Kunden, die beide Seiten fordert
- W-Fragen stellen [Jonathan Stark]
- Messbare Größen identifizieren, z. B.
	- Steigerung des Umsatzes um 10%
	- Reduzierung der Personalkosten um 20% durch eine Migration

---

# Beispiel: Findung des subjektiven Werts

- Kunde möchte "Single Sign On in seine Anwendung implementiert haben" 
- Festpreis: Kosten dafür wurden mit 1 PT in Rechnung gestellt
- Mit VbP:
	- Fragen: 
		- Warum wird SSO gerade jetzt benötigt? Gibt es Beschwerden? Können damit Fehler reduziert werden?
		- Wird SSO wirklich benötigt?
		- Wie viele Benutzer werden SSO nutzen?
		- ...
- Mit Beantwortung der Fragen kann eine Bepreisung erfolgen
	- Größeren Kunden ist dieses Feature mehr wert als kleineren

---

# Wie erfolgt die Bepreisung?
- Was kann mit 10% / 15% / 25% des erwarteten subjektiven Wertes im ersten Jahr implementiert werden?
	- Falls die 10% nicht die Selbstkosten + Gewinnspanne decken, lohnt sich das Projekt nicht
- Angebot an den Kunden mit den drei verschiedenen Optionen
- Durch die Wahloption ist der Kunde glücklicher - auch bei Ablehnung des Angebots

---

# Beispiel: Angebot

| 10% (Strategie) | 15% (Consulting) | 25% (Full-Service) |
|---|---|---|
| Roadmap für die Entwickler des Auftraggebers | wie 10%  | wie 15% |
| Aufweisen von typischen Fallstricken | Überprüfung der SSO-Funktionalität auf Sonderfälle | aber komplette der Umsetzung durch den Auftragnehmer |
| | inklusive Kommunikation zwischen Systemadministratoren und Entwicklern

--- 

# Beispiel: Bepreisung

- Alle anderen Web-Anwendungen besitzen bereits SSO, Benutzer sind unzufrieden
	- sehr schwierg zu  messen; kann die Unzufriedenheit zur Ablehnung des Systems führen? = __€ 20.000/Jahr__
- 2500 Benutzer, die SSO nutzen werden; auth0.com verlangt ~ € 20,00/Jahr;  __= € 50.000,00/Jahr__
- Pro Tag landen landen im internen Ticketsystem mindestens 5 False-Positives durch falsche Passworteingabe (15 Minuten je Ticket, 75 Minuten gesamt, interner Stundensatz € 50); __= € 27.375,00/Jahr__
- Interne Expertise für SSO nicht vorhanden
	- Aufwand von geschätzten 400 Stunden __ohne__ Expertise für interne MA: __€ 20.000,00/Jahr__

---

# Beispiel der Bepreisung
## Es handelt sich um *Beispiele*

- Messbare Größen von mindestens € 117.375,00/Jahr

Ein möglicher Ansatz:

| 10% (Strategie) | 15% (Consulting) | 25% (Full-Service) |
| --- | --- | --- |
| € 11.700,00 | € 17.600,00 | € 29.300,00 |

<small>Ob die 25%/€ 29.300,00 profitabel sind, hängt natürlich von den tatsächlichen Anforderungen ab.</small>

---

# Das klingt alles zu schön
- Das Vertrauensverhältnis zwischen Auftraggeber und Auftragnehmer muss existieren
	- Einmischung des Kunden in die tatsächliche Umsetzung muss begrenzt sein
	- Fokus auf das Ziel und nicht auf den Weg
- Funktioniert eher bei Projekten >= € 10.000,00
- Commodity-Markt ist durch sehr ähnliche Angebote schwer zu erreichen
- Low-Cost-Käufer (Einkaufspreis alleine zählt) sind die falsche Zielgruppe
	- ebenso wenig Kunden, die an Body-Leasing interesssiert sind

---

# Fazit

- VbP funktioniert nicht überall
	- Allgemeine Software-Entwicklung ist eher schwierig; der Auftragnehmer muss auf Themen spezialisiert sein
	- Spezielle Themenbereiche (siehe Beispiel SSO) hingegen lassen sich unterschiedlich bepreisen
- Die selbe Anforderung kann unterschiedlichen Kunden unterschiedlich viel wert sein
- Aus Auftragnehmersicht lässt fair mehr Geld verdienen
- Der Kunde kauft sich durch den höheren (Fest-)Preis mehr Sicherheit

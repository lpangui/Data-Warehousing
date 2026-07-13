# Data Warehousing mit SAP Datasphere & SAP Analytics Cloud

Im Rahmen der Vorlesung **Data Warehousing** wurden verschiedene praxisorientierte Fallstudien mit **SAP Datasphere** und **SAP Analytics Cloud (SAC)** bearbeitet. Ziel war es, moderne Data-Warehouse-Konzepte kennenzulernen und diese in einer Cloud-basierten SAP-Umgebung praktisch umzusetzen. Die Übungen deckten den gesamten Analyseprozess ab - von der Datenintegration und Datenmodellierung über Transformationsprozesse bis hin zur Erstellung analytischer Modelle und interaktiver Dashboards. Dabei wurden sowohl theoretische Grundlagen des Data Warehousing als auch deren praktische Umsetzung in SAP-Technologien vertieft.

## Case D1: Basic Concepts of SAP Datasphere

Im ersten Case wurde SAP Datasphere als moderne Cloud-Data-Warehouse-Lösung praktisch eingesetzt. Ziel war es, aus bestehenden Verkaufsdaten eines SAP S/4HANA-Systems ein analytisches Datenmodell für Business-Intelligence-Auswertungen aufzubauen.

Ausgehend von einer vorhandenen Staging Area mit Verkaufs-, Kunden- und Produktdaten wurde in SAP Datasphere ein multidimensionales Datenmodell nach dem Star-Schema-Ansatz entwickelt. Dabei wurden zunächst Dimensionen für Kunden und Produkte sowie eine Faktentabelle für Verkaufsdaten erstellt und miteinander verknüpft.

Ein besonderer Fokus lag auf der Modellierung von Stammdaten und Bewegungsdaten. Hierzu wurden Graphical Views erstellt, Daten bereinigt, Attribute angepasst und semantische Eigenschaften wie Dimensionen, Fakten, Kennzahlen und Einheiten definiert. Zusätzlich wurden Hierarchien sowie Textzuordnungen für bessere Analyse- und Reporting-Möglichkeiten umgesetzt.

Anschließend wurde aus dem Datenmodell ein Analytic Model erstellt, welches als Grundlage für die Analyse in SAP Analytics Cloud dient. Dabei wurden berechnete Kennzahlen definiert und die Daten über eine Live-Verbindung in SAC visualisiert. Zusätzlich wurde ein Plan-Ist-Vergleich umgesetzt. Hierfür wurden Plan- und Istdaten über einen Union-Prozess zusammengeführt und für eine gemeinsame Analyse vorbereitet.

## Case D2: Merge Szenario in SAP Datasphere

Im zweiten Case wurde die Integration heterogener Datenquellen in SAP Datasphere anhand eines Unternehmenszusammenschlusses simuliert. Dabei wurde angenommen, dass die Firma Global Bike (GB) das Unternehmen Best Run Bikes (BRB) übernimmt und beide Unternehmen zukünftig gemeinsam analysiert werden sollen.

Ziel des Cases war es, unterschiedliche Datenmodelle zusammenzuführen, ohne redundante Datenstrukturen aufzubauen. Hierfür wurden Produktstammdaten und Verkaufsdaten beider Unternehmen harmonisiert und in ein gemeinsames Reporting-Modell integriert.

Ein Schwerpunkt lag auf der Zusammenführung von Stammdaten. Da beide Unternehmen unterschiedliche Produktstrukturen und Kategorien verwendeten, wurden die Produktinformationen vereinheitlicht und über Mapping-Tabellen in eine gemeinsame Produktkategorisierung überführt. Die unterschiedlichen Datenquellen wurden anschließend mithilfe von Union-Operationen in gemeinsamen Dimensions- und Fakt-Views zusammengeführt.

Auch die Bewegungsdaten der beiden Unternehmen wurden harmonisiert. Dabei wurden unterschiedliche Datenstrukturen, Kennzahlen und Feldbezeichnungen analysiert und angepasst. Zusätzlich wurde ein Herkunftsmerkmal (Company) ergänzt, um die Datenquellen weiterhin unterscheiden und gemeinsam auswerten zu können. Abschließend wurde ein gemeinsames analytisches Datenmodell in SAP Datasphere erstellt und über SAP Analytics Cloud visualisiert. Dadurch konnten Unternehmenskennzahlen wie Umsätze, Mengen und Produktkategorien unternehmensübergreifend analysiert werden.

## Case D3: Analytic Model in SAP Datasphere

Im dritten Case wurde die Erstellung und Erweiterung von **Analytic Models in SAP Datasphere** behandelt. Ziel war es, ein bestehendes Datenmodell aus dem vorherigen Case für weiterführende Analysen und Reporting-Szenarien aufzubereiten.

Das Analytic Model dient dabei als virtueller Data Mart und stellt eine zentrale Schnittstelle zwischen der Datenmodellierung in SAP Datasphere und der Analyse in SAP Analytics Cloud dar. Dabei können Kennzahlen, Berechnungen, Filter und Variablen zentral definiert und wiederverwendbar für verschiedene Reports genutzt werden.

Im Rahmen des Cases wurden verschiedene analytische Funktionen umgesetzt. Dazu gehörten die Erstellung berechneter Kennzahlen (Calculated Measures), beispielsweise für Rabatte und Verkaufspreise, sowie die Definition von Ausnahmeaggregationen für Kennzahlen wie die Anzahl von Aufträgen. Dadurch wurde untersucht, wie Kennzahlen auf unterschiedlichen Aggregationsebenen korrekt berechnet und interpretiert werden können.

Zusätzlich wurden Variablen und Filter im Analytic Model eingesetzt. Dadurch können Benutzer dynamische Eingaben wie Zeiträume oder Schwellenwerte für Analysen festlegen, während globale Filter eine dauerhafte Einschränkung des Datenbereichs ermöglichen. Ein weiterer Schwerpunkt lag auf Restricted Measures, mit denen Kennzahlen durch zusätzliche Filterbedingungen eingeschränkt und beispielsweise Vorjahresvergleiche umgesetzt werden können. Die Ergebnisse wurden anschließend über SAP Analytics Cloud Stories visualisiert und überprüft.

## Case D4: Transformation Flow in SAP Datasphere

Im vierten Case wurde die Umsetzung von ETL-Prozessen mit **Transformation Flows in SAP Datasphere** behandelt. Ziel war es, Daten aus bestehenden Datenmodellen zu transformieren, dauerhaft zu speichern und für weitere Analysen bereitzustellen.

Im Gegensatz zu virtuellen Views ermöglichen Transformation Flows den Aufbau persistenter Datenlayer. Dabei können verschiedene Datenquellen integriert und durch Transformationen wie Joins, Filter, Aggregationen, Projektionen und berechnete Spalten verarbeitet werden.

Als Praxisbeispiel wurde ein Kunden-Bonusprogramm für Global Bike umgesetzt. Hierfür wurden Verkaufsdaten analysiert und abhängig vom Umsatz der Kunden verschiedene Statusstufen vergeben. Die berechneten Kundendaten wurden anschließend in einer separaten Tabelle gespeichert und für weitere Auswertungen bereitgestellt.

Die Umsetzung erfolgte zunächst über einen grafischen Transformation Flow. Dabei wurden Daten aus der Verkaufsfaktentabelle mit der Zeitdimension verknüpft, gefiltert, aggregiert und durch berechnete Felder erweitert. Anschließend wurde die Logik durch einen SQL-basierten Transformation Flow erweitert, um komplexere Berechnungen und zusätzliche Geschäftsregeln umzusetzen.

Ein weiterer Schwerpunkt lag auf der Verarbeitung von Datenänderungen und dem Schreiben der Ergebnisse in Zieltabellen. Dabei wurden verschiedene Ladeverfahren wie UPSERT sowie die Überwachung der Ausführung über den Flow Monitor betrachtet. Durch den Case wurden praktische Kenntnisse in der Datenintegration, Transformation und Persistierung innerhalb eines Cloud Data Warehouses vertieft.

## Case D5: Geo-Anreicherung in SAP Datasphere mit Intelligent Lookup

Im fünften Case wurde die Anreicherung bestehender Unternehmensdaten mit geografischen Informationen mithilfe von **Intelligent Lookup in SAP Datasphere** umgesetzt. Ziel war es, Kundendaten um Längen- und Breitengrade zu erweitern und dadurch neue Analyse- und Visualisierungsmöglichkeiten in SAP Analytics Cloud zu ermöglichen.

Ausgangspunkt war die bestehende Kundendimension aus Case D1. Mithilfe des Intelligent Lookup wurden Kundendaten mit einer externen Geodatenquelle (World City Data) abgeglichen und automatisch um die Attribute **Latitude** und **Longitude** ergänzt.

Die Zuordnung erfolgte schrittweise über verschiedene Matching-Strategien. Zunächst wurde ein exakter Abgleich über den Stadtnamen durchgeführt. Anschließend wurden zusätzliche Regeln mit Länderinformationen sowie Fuzzy-Matching eingesetzt, um auch nicht eindeutige oder abweichende Schreibweisen möglichst zuverlässig zuzuordnen. Nicht automatisch lösbare Fälle konnten anschließend manuell überprüft und korrigiert werden.

Die angereicherten Geodaten wurden anschließend in eine erweiterte Kundendimension integriert und mit den Verkaufsdaten verknüpft. Auf dieser Grundlage wurde ein neues Analytic Model erstellt und in SAP Analytics Cloud für geografische Analysen genutzt. Dabei wurden verschiedene Visualisierungen umgesetzt, darunter Kartenansichten, Heatmaps und regionale Analysen. Zusätzlich wurde die Nutzung der SAP HANA Spatial Engine untersucht, um Entfernungsberechnungen zwischen Kundenstandorten und Referenzpunkten durchzuführen.


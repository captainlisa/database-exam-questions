# Database Questions

1. Wie sieht die Struktur eines hierarchischen Datenbankmodelles aus?
   Der Aufbau einer hierarchischen Datenbank wird in Form einer Baumstruktur dargestellt. Den Ausgangspunkt bildet die Wurzel, welche keinen Vorgänger hat. Von der Wurzel ausgehend, hat jeder Datensatz genau einen Vorgänger. Ein Nachfolger-Datensatz kann ebenso Nachfolger haben, wodurch sich die einzelnen Äste des Baumes bilden. Die Abschlussobjekte werden Blätter genannt. 

2. Nenne jeweils 2 Vor- und Nachteile einer hierarchischen Datenbank:
    Vorteile: 
     - sehr einfach zu verstehen, zu lesen, sehr performant
     - einfacher und schneller Zugriff durch festgelegte Suchpfade, benötigt wenig Rechenleistung
    Nachteile:
     - durch die festgelegten Zugriffspfade allerdings auch sehr unflexibel. Man muss die Pfade kennen und bei jeder Anfrage die gesamte Hierarchie durchwandern
     - die Integrität der Daten kann durch redundante Datensätzen nicht gewährleistet werden.

3. Was ist das Konzept der Denormalisierung?
   Die Denormalisierung wird durchgeführt nachdem die Datenbank die 3. Normalform erreicht hat. Hier wird sozusagen ein Schritt zurück gemacht und es werden gewollt Redundanzen erzeugt um bestimmte Daten, wie Userdaten, zu sichern.

4. Erkläre den Unterschied zwischen Integrität und Konsistenz:
	Integrität ist die Richtigkeit der Daten.
	Konsistenz ist die Richtigkeit der Daten über Zeit.

5. Nenne 5 der Codd'schen Regeln und erläutere sie:
   - Integration: Daten müssen in einer einheitlichen Struktur ohne Redundanz abgelegt werden
   - Benutzersichten: Für unterschiedliche Anwendungen brauchen wir eine unterschiedliche Sicht auf den Datenbestand
   - Operationen: In einer Datenbank müssen Daten gespeichert, geändert und gesucht werden könenn
   - Katalog: Im Katalog werden Informationen abgelegt, die die Daten in einer Datenbank beschreiben
   - Datenschutz: Nur berechtigte Benutzer und Programme dürfen Zugriff auf die Datenbank haben

6. Was sind die 3 "Arten" von SQL und wie lassen sich die Befehle einordnen? 
	DDL = Data Definition Language, definiert die Tabellenstruktur: CREATE TABLE, DROP TABLE, ALTER TABLE
	DML = Data Manipulation Language: INSERT, UPDATE, DELETE
	DCL = Data Control Language, definiert Vorgänge, die direkt mit der DB zu tun haben, z.B. interne Prozesse, Berechtigungen: REVOKE, GRANT, CREATE SCHEMA 
    SELECT -> ist ein spezieller Fall. Man könnte den Befehl zu DML zählen, aber er lässt sich nicht hundertprozentig einordnen

7. Welche Arten von Joins gibt es? 
   - Inner Join selektiert Datensätze aus der linken und rechten Tabelle, welche in beiden Tabellen enthalten sind
   - Right Join selektiert die rechten Tabelle inklusive denen, die in beiden Tabellen enthalten sind 
   - Left Join selektiert die linken Tabelle inklusive denen, die in beiden Tabellen enthalten sind
   - Full Outer Join selektiert die Gesamtheit der linken und rechten Tabelle

8. Erläutere kurz die Speicherstruktur einer Oracle Datenbank:
   - Die kleinste Einheit bilden Datenblöcke welche in Segmente unterteilt sind. Mehrere Segmente werden zusammengefasst zu einem Extent.
   - Jeder Datenblock hat eine festgelegte Speichergröße und besteht aus einem Header, einem Table Directory, Row Directory, Row Data (PCTUSED) und dem Free Space (PCTFREE), welcher nie unter 20% sein kann. 

9.  Erkläre die 3 Abhängigkeiten, welche bei der Normalisierung behandelt werden:
	- Funktionale Abhängigkeit: zu jedem X gibt es ein Y
	- Voll Funktionale Abhängigkeit: wenn das Nicht-Schlüsselattribut nicht nur von einem Teil der Attribute eines zusammengesetzten Schlüsselkandidaten funktional abhängig ist, sondern von allen Teilen eines Relationstyps 
	- Transitive Abhängigkeit: wenn Y von X funktional abhängig ist und Z von Y, so ist Z von X funktional abhängig

10. Was kennzeichnet eine Transaktion? 
    Eine Transaktion ist eine Abfolge von mehreren Arbeitsschritten, welche in einer Einheit zusammengefasst werden. Eine Transaktion wird entweder komplett und fehlerfrei durchgeführt, oder gar nicht. Das bedeutet, sobald ein Fehler auftritt, werden die gesamten Arbeitsschritte rückgängig gemacht und die Transaktion abgebrochen. in MySQL beginnt eine Transaktion mit begin transaction und endet mit einem commit.
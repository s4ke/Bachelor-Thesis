In Hibernate-Search-JPA befindet sich das komplette Projekt unterteilt in Ordner:

build-config:
	Utility Klassen die beim Build-Prozess von Maven benutzt werden
db:
	"hibernate-search-db" Modul
ejb:
	"hibernate-search-ejb" Modul, Integration mit EJB (Nicht in der Thesis behandelt).
integrationtest:
	Enth�lt Integrationstest-Module f�r TomEE, GlassFish und WildFly.
jpa:
	"hibernate-search-jpa" Modul. repr�sentiert "Hibernate Search GenericJPA" in der
	Thesis.
standalone:
	"hibernate-search-standalone" Modul
util:
	Enth�lt allgemeine Utility Klassen.


In hibernate-search-generic-jpa-example befindet sich ein kleines Beispielprojekt
das MySQL benutzt. Hierf�r wird eine Datenbank gebraucht:

	url: jdbc:mysql://localhost:3306/testingdb
	user: hibernate_user (Dieser User ben�tigt Rechte um das Schema zu �ndern, um die Benutzung einfacher
			zu gestalten kann der User auch einfach zum Admin gemacht werden).
	password: hibernate_password

Das Beispielprojekt benutzt Maven zum Build und kann �ber

	mvn install

gebaut werden. Die Beispiele sind in Form eines Unit-Tests in der Klasse
org.hibernate.search.genericjpa.test.integration.IntegrationTest zu finden.

============================================================================================
============================================================================================
=======================================	How To Build =======================================
============================================================================================
============================================================================================

Um das Projekt von den Quellen zu builden, muss in das das Hauptverzeichnis
"Hibernate-Search-JPA" gewechselt werden und folgendes maven Kommando abgesetzt werden:

	mvn clean install -DskipTests

Dieses �berspringt alle Unit-Tests, da ein Paar davon MySQL und PostgreSQL
Datenbank-Server zum Testen ben�tigen w�rden. Der Build-Prozess kann aber trotzdem
einen Moment dauern, da erst alle Abh�ngigkeiten aus dem zentralen Maven Repository geladen
werden m�ssen.

Die bereits gebauten Versionen sind in den jeweiligen Modulen im Unterordner target/
zu finden, z.B. f�r das komplette GenericJPA Modul:

jpa/target/hibernate-search-jpa-0.4.0-SNAPSHOT.jar
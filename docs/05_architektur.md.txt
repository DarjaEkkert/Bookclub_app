# Architektur

## Überblick

Die Anwendung ist eine einfache Web-App zur Verwaltung von Büchern für einen Buchclub.
Sie ist so aufgebaut, dass verschiedene Aufgaben voneinander getrennt sind.

---

## Aufbau der Anwendung

### Benutzeroberfläche (UI)

Hier sieht der Nutzer die App und kann mit ihr arbeiten:

* Bücher anzeigen
* neue Bücher hinzufügen
* Bewertungen und Rezensionen eingeben
* Bücher bearbeiten und löschen

---

### Logik

Dieser Teil verarbeitet die Aktionen des Nutzers:

* Bücher hinzufügen
* Bücher bearbeiten und löschen
* Bewertungen und Kommentare speichern

---

### Daten

Hier werden die Informationen gespeichert:

* Liste der Bücher
* Bewertungen
* Rezensionen

Aktuell werden die Daten lokal im Browser gespeichert.
Später kann hier eine Datenbank verwendet werden.

---

## Erweiterungsidee

Die Anwendung kann später erweitert werden zu einer Plattform mit mehreren Nutzern.

### Rollen

**Administrator:**

* Fügt jeden Monat neue Bücher hinzu
* Verwaltet die zentrale Buchliste

**Nutzer:**

* Wählt Bücher aus
* Gibt Bewertungen (1–5 Sterne)
* Schreibt Rezensionen

---

## Ablauf

* Jeden Monat werden neue Bücher bereitgestellt
* Nutzer können diese Bücher bewerten und kommentieren
* Auf der Startseite werden aktuelle Bücher angezeigt
* Zu jedem Buch sieht man:

  * Anzahl der Leser
  * Durchschnittliche Bewertung

Beim Klick auf ein Buch:

* werden alle Rezensionen angezeigt

---

## Darstellung

Es kann eine Seite geben, die wie ein Bücherregal aufgebaut ist:

* alle Bücher werden übersichtlich angezeigt
* beim Darüberfahren mit der Maus sieht man das Cover
* Klick führt zur Detailseite

---

## Fazit

Die Anwendung ist einfach aufgebaut, kann aber später erweitert werden.
Durch die Trennung in Oberfläche, Logik und Daten bleibt sie übersichtlich und verständlich.

# Architektur

## Überblick

Die Anwendung ist eine Webanwendung zur Verwaltung von Büchern für einen Buchclub.  
Sie wurde von einer einfachen Single-User-Anwendung zu einer Multi-User-Plattform erweitert.

Die Architektur ist so aufgebaut, dass verschiedene Aufgaben voneinander getrennt sind:
- Benutzeroberfläche (Frontend)  
- Anwendungslogik  
- Datenhaltung (Backend)  

---

## Aufbau der Anwendung

### Benutzeroberfläche (UI)

Hier interagiert der Nutzer mit der Anwendung.

Funktionen:
- Bücher anzeigen  
- neue Bücher hinzufügen (Admin)  
- Bewertungen und Rezensionen eingeben  
- Bücher bearbeiten und löschen  
- Bücher als gelesen markieren  

---

### Logik

Dieser Teil verarbeitet die Aktionen der Nutzer und steuert den Ablauf der Anwendung.

Funktionen:
- Bücher hinzufügen, bearbeiten und löschen  
- Bewertungen und Rezensionen speichern  
- Rollen prüfen (Admin / Nutzer)  
- Daten aktualisieren und darstellen  
- Echtzeit-Aktualisierung nach Änderungen  

---

### Daten

Hier werden alle Informationen gespeichert.

Gespeicherte Daten:
- Bücher (Titel, Autor, Cover)  
- Nutzerkonten  
- Bewertungen und Rezensionen  
- Lesestatus („mark as read“)  

Entwicklung:
- ursprünglich: Speicherung im localStorage (nur lokal)  
- aktuell: zentrale Datenbank (Supabase) für alle Nutzer  

---

## Erweiterungsidee (fachliches Konzept)

Die Anwendung orientiert sich an einem klassischen Buchclub.

### Rollen

**Administrator:**
- fügt regelmäßig neue Bücher hinzu  
- verwaltet die zentrale Buchliste  

**Nutzer:**
- wählt Bücher aus  
- markiert Bücher als gelesen  
- gibt Bewertungen (1–5 Sterne) ab  
- schreibt Rezensionen  

---

## Ablauf im Buchclub

- regelmäßig (z. B. monatlich) werden neue Bücher bereitgestellt  
- Nutzer können diese Bücher lesen, bewerten und kommentieren  
- auf der Startseite werden aktuelle Bücher angezeigt  

Zu jedem Buch werden angezeigt:
- Anzahl der Leser  
- durchschnittliche Bewertung  

Beim Klick auf ein Buch:
- werden alle Rezensionen angezeigt  

---

## Darstellung (UI-Konzept)

Die Anwendung kann verschiedene Darstellungsformen nutzen:

- Übersicht aller Bücher in Kartenform  
- Darstellung als „Bücherregal“  
- beim Hover wird das Buchcover hervorgehoben  
- Klick auf ein Buch führt zur Detailansicht  

---

## Entwicklung der Architektur

### Phase 1 – Single-User

- lokale Speicherung im Browser (localStorage)  
- keine Benutzerverwaltung  
- Daten nur für einen Nutzer verfügbar  

---

### Phase 2 – Multi-User

- zentrale Datenbank (Supabase)  
- Benutzer-Authentifizierung  
- gemeinsame Datenbasis für alle Nutzer  
- Cloud Storage für Bilder  
- Echtzeit-Aktualisierung  

---

## Datenmodell (vereinfacht)

Die wichtigsten Beziehungen:

- Ein Benutzer kann mehrere Bewertungen schreiben  
- Ein Buch kann mehrere Bewertungen haben  
- Jede Bewertung gehört genau zu einem Benutzer und einem Buch  

Struktur:

User → Book → Review

---

## Architekturentscheidungen

### Bildspeicherung

Für die Multi-User-Version wurde Cloud Storage gewählt,  
damit Buchcover zentral gespeichert und für alle Nutzer verfügbar sind.

Die Alternative (URL-basierte Bilder) wurde verworfen,  
da sie weniger zuverlässig und benutzerfreundlich ist.

---

### Bewertungen

Jeder Nutzer kann eine eigene Bewertung und Rezension pro Buch abgeben.

Dadurch entstehen:
- mehrere Meinungen pro Buch  
- eine aggregierte Gesamtbewertung  

Eine gemeinsame Bewertung wurde verworfen,  
da Nutzer sich gegenseitig überschreiben würden.

---

### Admin-Erstellung

Der erste registrierte Benutzer wird automatisch als Administrator festgelegt.

Diese Lösung ist einfach umzusetzen und erfordert keinen manuellen Eingriff in die Datenbank.

---

### Authentifizierung

Es wird eine einfache Anmeldung mit E-Mail und Passwort verwendet.

Diese Lösung ist stabil und ausreichend für den Anwendungsfall.  
Externe Anbieter (z. B. Google Login) wurden aufgrund des höheren Aufwands verworfen.

---

## Echtzeit-Verhalten

Die Anwendung nutzt eine Echtzeit-Aktualisierung der Daten.

Nach Änderungen (z. B. Bewertung oder Lesestatus):
- werden Daten automatisch neu geladen  
- Änderungen sind sofort für alle Nutzer sichtbar  

---

## Fazit

Die Anwendung ist modular aufgebaut und wurde erfolgreich von einer lokalen Single-User-App zu einer Multi-User-Plattform weiterentwickelt.

Durch die klare Trennung von Oberfläche, Logik und Daten bleibt die Anwendung verständlich, wartbar und erweiterbar.
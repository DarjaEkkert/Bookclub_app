# Weiterentwicklung

## Ziel

Die bestehende Anwendung wird schrittweise erweitert und verbessert, um sie näher an eine reale Buchclub-App heranzuführen.

---

## Design-Anpassung (Phase 1)

Das Design der Anwendung wurde überarbeitet, um eine modernere und benutzerfreundlichere Oberfläche zu erreichen.

Dabei wurde sich an einem zuvor erstellten UI-Design orientiert (warme Farben, klare Struktur, Kartenlayout).

---

## CSS-Refactoring

Das Styling wurde aus der HTML-Datei ausgelagert und in eine separate CSS-Datei (`css/style.css`) verschoben.

Vorteile:

* bessere Struktur
* leichtere Wartung
* Trennung von Inhalt und Design

---

## HTML-Struktur angepasst

Die HTML-Struktur wurde angepasst, damit die neuen CSS-Klassen korrekt angewendet werden können.

Insbesondere wurden folgende Klassen eingeführt:

* `form`
* `book`
* `book-title`
* `book-author`
* `actions`

---

## Fehlerbehebung (CSS)

Beim Einfügen des Stylesheets traten Probleme auf, da ungültige Zeichen (z. B. vor Farbwerten) enthalten waren.

Diese wurden entfernt, sodass das Design korrekt dargestellt wird.

---

## Aktueller Stand

Die Anwendung verfügt nun über:

* verbessertes Design
* strukturierte CSS-Datei
* funktionierende Darstellung von Büchern als Karten

### Screenshot

images/app-v5-design.png
---

## Nächste Schritte

* Upload von Buchcovern vom lokalen Rechner
* Speicherung der Daten (localStorage verbessern)
* Erweiterung zur Multi-User-Anwendung (Admin / Nutzer)

## Upload von Buchcovern

Die Anwendung wurde um eine Funktion erweitert, mit der Buchcover direkt vom lokalen Rechner hochgeladen werden können.

Zuvor war nur die Eingabe einer Bild-URL möglich.
Durch die neue Funktion wird die Nutzung für den Anwender deutlich einfacher und intuitiver.

Technisch wird das ausgewählte Bild im Browser verarbeitet und gespeichert, sodass es direkt in der Anwendung angezeigt werden kann.

### Nutzen

* einfachere Bedienung
* keine externen Bildquellen notwendig
* bessere Benutzererfahrung
### Screenshot

![Upload](images/app-v6-image-upload.png)

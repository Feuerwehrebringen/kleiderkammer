# Kleiderkammer FF Ebringen

Web-App für die Kleiderkammer der Freiwilligen Feuerwehr Ebringen:
Ausgabe, externe Abholscheine, Rückgabe, Lagerbestand, Personenübersicht und Katalogpflege.

## Aufbau

- **Frontend:** `index.html` + `logo.png`, gehostet über GitHub Pages
- **Backend:** Google Apps Script im Google Sheet der Kleiderkammer (JSON-API über `doPost`)
- **Daten:** Google Sheet (Blätter Einstellungen, Kameraden, Katalog, Lieferanten, Lagerbestand, Vorgaenge, Buchungen)
- **Belege:** PDF in Google Drive (Ordner `Kleiderkammer_PDF_Ablage`) + Versand per E-Mail

## Konfiguration

In `index.html` die Web-App-URL des Apps-Script-Projekts eintragen:

```js
const API_URL = 'https://script.google.com/macros/s/…/exec';
```

Der Zugriff ist über die PIN im Blatt „Einstellungen“ geschützt. Ohne PIN verweigert das Backend Anfragen von GitHub.
Alle übrigen Einstellungen (Empfänger, Kleiderwart, Mindestbestand) werden im Sheet gepflegt.

## Hinweis

Personenbezogene Daten liegen ausschließlich im Google Sheet, nicht in diesem Repository.

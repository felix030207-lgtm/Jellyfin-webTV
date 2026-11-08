# JellyWeb TV

Eine kleine Android-TV-App, die **deine normale Jellyfin-Weboberfläche** im Vollbild öffnet.
Darum funktionieren Web-Plugins wie **Bonfire** (Profilauswahl), **Media Bar Enhanced**
und **Seasonal** genauso wie im Browser – mit deinen eigenen Einstellungen.

Du installierst nur diese eine App. Anklicken, Profil wählen, fertig.

Gedacht für Android TV / Google TV und den Raspberry Pi mit LineageOS Android TV
(auch auf Android-Handys und -Tablets startbar, z. B. zum Ausprobieren).

---

## Einmalig: App-Datei (APK) bauen lassen (ca. 5 Minuten)

Die APK wird kostenlos von GitHub gebaut – du musst nichts installieren.

1. Kostenloses Konto auf <https://github.com> anlegen (oder einloggen).
2. Oben rechts **+ → New repository**. Name z. B. `jellyweb-tv`, **Public** auswählen,
   **Create repository**.
3. Diesen Ordner entpacken. Auf der neuen leeren Repository-Seite auf **uploading an existing file**
   klicken und den **gesamten Inhalt** des Ordners per Drag & Drop hineinziehen
   (auch den versteckten Ordner `.github` – am einfachsten alles im Ordner markieren und ziehen).
   Unten **Commit changes** klicken.
4. Oben auf **Actions** klicken. Dort läuft jetzt „APK bauen“ (gelber Punkt). Nach 3–5 Minuten
   ist er grün.
   - Wenn er rot wird: auf den Lauf klicken, den Fehlertext kopieren und mir schicken.
5. Die fertige Datei findest du auf der Repository-Startseite rechts unter **Releases →
   JellyWeb TV (aktuelle Version) → `JellyWeb-TV.apk`**.

Die feste Download-Adresse ist danach:

```
https://github.com/DEIN-NAME/jellyweb-tv/releases/download/apk-latest/JellyWeb-TV.apk
```

## Auf den Fernseher bringen

Eine der beiden Möglichkeiten:

- **USB-Stick:** APK auf den Stick kopieren, Stick in den Pi/Fernseher, mit der
  „Dateien“-App öffnen und installieren (ggf. „Aus unbekannten Quellen installieren“ erlauben).
- **Downloader-App** (kostenlos im Play Store): dort die Adresse von oben eingeben,
  herunterladen, installieren.

## Benutzen

1. **JellyWeb TV** starten (steht in der App-Liste / auf dem Startbildschirm).
2. Beim ersten Start sucht die App deinen Jellyfin-Server im Heimnetz. Wird er gefunden,
   nur **OK** drücken. Sonst Adresse eingeben, z. B. `http://192.168.178.50:8096`.
3. Profil wählen (Bonfire), einloggen – fertig. Die Anmeldung bleibt gespeichert.

### Fernbedienung

| Taste | Wirkung |
|---|---|
| Pfeiltasten / OK | navigieren und auswählen |
| Zurück | eine Seite zurück (auf der Startseite 2× drücken = App beenden) |
| Menü-Taste **oder** Zurück lange halten | Menü: neu laden, Server ändern, TV-Ansicht an/aus, Zwischenspeicher leeren, beenden |

### Wenn etwas nicht passt

- **Oberfläche sieht aus wie auf dem Handy:** Menü → „TV-Ansicht“ umschalten, oder in den
  Jellyfin-Einstellungen den Anzeigemodus auf „TV“ stellen.
- **Plugin-Änderungen erscheinen nicht:** Menü → „Zwischenspeicher leeren und neu laden“.
- **Ruckelt auf dem Raspberry Pi:** in Media Bar Enhanced die Video-Hintergründe/Trailer ausschalten
  („Enable Video Backdrops“).

## Technik (nur falls es dich interessiert)

- Reine Android-`WebView`, kein Zusatz-Framework, keine Werbung, keine Datenweitergabe.
- Die App kennt nur die Adresse deines Servers; alles andere kommt von deinem Jellyfin.
- Quellcode: `app/src/main/java/de/jellyweb/tv/MainActivity.java`.
- HTTP im lokalen Netz ist erlaubt (nötig für `http://192.168…`).

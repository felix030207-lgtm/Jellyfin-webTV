# JellyWeb TV

Eine kleine Android-TV-App, die **deine normale Jellyfin-Weboberfläche** im Vollbild öffnet.
Darum funktionieren Web-Plugins wie **Bonfire** (Profilauswahl), **Media Bar Enhanced**
und **Seasonal** genauso wie im Browser – mit deinen eigenen Einstellungen.

Du installierst nur diese eine App. Anklicken, Profil wählen, fertig.

Gedacht für Android TV / Google TV und den Raspberry Pi mit LineageOS Android TV
(auch auf Android-Handys und -Tablets startbar, z. B. zum Ausprobieren).

---

## Auf den Fernseher bringen

Eine der beiden Möglichkeiten:

- **USB-Stick:** APK auf den Stick kopieren, Stick in den Pi/Fernseher, mit der
  „Dateien“-App öffnen und installieren (ggf. „Aus unbekannten Quellen installieren“ erlauben).
- **Downloader-App** (kostenlos im Play Store): dort die Adresse eingeben,
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

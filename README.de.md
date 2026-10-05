# Spam filtering (Spam-Informationen filtern)

> 🌍 [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [Português](README.pt.md) · [Русский](README.ru.md)

Halten Sie Ihr Browsing sauber. **Spam filtering** entfernt automatisch Spam, Pop-ups, Banner, Tracker und andere Störeinflüsse von den von Ihnen besuchten Seiten — alles läuft lokal und privat auf Ihrem Gerät.

## Highlights

- Blockiert Spam und Störeinflüsse: Pop-ups, Banner, Tracker, Analyse-Skripte
- Eigene Regeln im Klartext — jederzeit importieren, bearbeiten und exportieren
- Whitelist für vertrauenswürdige Seiten mit einem Klick
- Blockier-Statistik (heute / gesamt)
- Unterstützt 10 Sprachen
- 100 % lokal und privat — kein Konto, keine Cloud, keine Datenerfassung
- Funktioniert auf Systemebene — keine Browsererweiterung nötig

## Systemanforderungen

- Windows 10 / 11

## Erste Schritte

1. Laden Sie das neueste Installationsprogramm von der Releases-Seite herunter.
2. Installieren und starten Sie die App.
3. Aktivieren Sie in den Einstellungen **System-Proxy übernehmen**.
4. Surfen Sie normal — Störeinflüsse werden automatisch gefiltert.

## Regeln bearbeiten

Regeln werden als Klartext gespeichert, eine Regel pro Zeile. Fügen Sie Regeln auf der Seite **Regeln** in der App hinzu oder importieren Sie eine Regeldatei.

### Regelformate

| Beispiel | Bedeutung |
| --- | --- |
| `\|\|example.com^` | Eine Domain und alle ihre Subdomains blockieren |
| `\|\|example.com/path/page^` | Eine bestimmte Adresse (Domain + Pfad) blockieren |
| `example.com` | Jede Adresse blockieren, die diesen Text enthält |
| `@@\|\|good.example.com^` | Ausnahme — diese Domain immer erlauben |
| `0.0.0.0 ad.example.com` | Eintrag im hosts-Format |
| `! Kommentar` / `# Kommentar` | Kommentarzeilen — Zeilen, die damit beginnen, werden ignoriert |

### Tipps

- `||` verankert die Regel am Domain-Anfang; `^` bedeutet „Ende der Domain oder des Pfads“ (ein Trennzeichen).
- Einfach beginnen: `||domain^` deckt die meisten Fälle ab. Pfadregeln nur bei Bedarf hinzufügen, z. B. `||www.example.com/ads/banner^`.
- Nach dem Speichern einer Regel können Sie über die Blockier-Statistik prüfen, ob sie funktioniert.

### Über HTTPS

Standardmäßig werden HTTPS-Anfragen nur nach **Domainname** abgeglichen (die vollständige Adresse ist verschlüsselt und nicht sichtbar). Für den Abgleich nach **vollständiger Adresse einschließlich Pfad** aktivieren Sie in den Einstellungen **HTTPS-Entschlüsselung (MITM)**, installieren Sie das Root-Zertifikat wie angefordert (nur einmal) und starten Sie Ihren Browser neu. Danach wirken Pfadregeln wie `||www.example.com/ads/banner^` auch auf HTTPS-Seiten.

## Funktionsweise (kurz)

- Die App betreibt einen lokalen Proxy und kann den System-Proxy übernehmen, sodass der Browserverkehr darüber läuft.
- Jede Anfrage wird mit Ihren Regeln abgeglichen: Übereinstimmungen werden blockiert, alles andere unverändert weitergeleitet.
- Die gesamte Filterung erfolgt auf Ihrem Gerät — nichts wird irgendwohin hochgeladen.

## Problemlösung

**Kein Internetzugang?** Die wahrscheinlichste Ursache: Die App wurde unerwartet beendet und der System-Proxy zeigt noch auf einen ungültigen Port.

- **Lösung 1 — App neu starten.** Sie erkennt und bereinigt übrig gebliebene Proxy-Einstellungen beim Start automatisch.
- **Lösung 2 — Proxy manuell deaktivieren.** Windows-Einstellungen → Netzwerk und Internet → Proxy → „Proxyserver verwenden“ ausschalten.
- Normalerweise stellt das Beenden der App (Tray-Symbol → Beenden) den Proxy automatisch wieder her. Reste entstehen nur nach abnormalem Beenden (Absturz, erzwungenes Beenden, Stromausfall).

## Datenschutz

Spam filtering ist ein lokales Werkzeug. Die gesamte Filterung erfolgt auf Ihrem Gerät — Ihre Browserdaten verlassen niemals Ihren Computer.

## Dieses Projekt unterstützen

Wenn Spam filtering Ihnen hilft, unterstützen Sie bitte die weitere Entwicklung:

![Donate](donate.jpg)

## Lizenz

Alle Rechte vorbehalten. Diese Software ist **nicht Open Source**. Weitergabe und Änderung sind ohne ausdrückliche schriftliche Genehmigung nicht gestattet.

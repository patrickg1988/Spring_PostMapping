# 🧪 Spring_TryPostMapping – Formulardaten mit `@PostMapping` (Spring Boot)

Dieses Repository ist ein **Mini‑Lernprojekt für Schüler**:  
Du übst, wie man mit **Spring Boot (MVC)** eine Webseite mit einem **Formular** baut und die Eingaben mit `@PostMapping` serverseitig verarbeitet.

Kurz gesagt: **Browser → Formular absenden → Spring Controller → Antwort anzeigen**.

---

## 🎯 Lernziele

Nach diesem Projekt kannst du erklären und umsetzen:

- Was passiert bei einem **HTTP GET** und **HTTP POST**
- Wozu `@GetMapping` und `@PostMapping` dienen
- Wie Spring Formulardaten an Controller‑Methoden übergibt
- Wie man Daten mit dem `Model` an eine HTML‑Seite (Thymeleaf) übergibt
- Warum Templates im Ordner `templates/` liegen

---

## 🧰 Tech-Stack

- Java **17** (im Projekt so konfiguriert)
- Spring Boot **4.0.1**
- Spring Web MVC
- Thymeleaf

> Abhängigkeiten sind in der `pom.xml` enthalten.  
> Aktuell sind `pom.xml` und `application.properties` im Repo als **eine Zeile** gespeichert – das ist technisch nicht ideal, aber für das Lernen okay. (Tipp: später formatieren.)

---

## 🚀 Starten

### 1) Projekt starten

```bash
./mvnw spring-boot:run
# oder
mvn spring-boot:run
```

### 2) Öffnen im Browser

Das Projekt läuft auf Port **8081**:

```
http://localhost:8081
```

(Port steht in `src/main/resources/application.properties`.)

---

## 📁 Wichtige Ordner (Orientierung)

```
src/main/java/...
  DemoApplication.java     → Startpunkt der Anwendung

src/main/resources/
  templates/index.html     → Thymeleaf-Template (Seite)
  application.properties   → Einstellungen (z. B. Port)
```

---

## 🧠 Was das Projekt zeigen soll (Kernidee)

Du baust eine Seite mit:

1. **GET** → zeigt Formular an  
2. **POST** → verarbeitet Eingaben und gibt „Hallo <Name>“ aus

So sieht der typische Ablauf aus:

- Browser ruft `/` auf → Spring zeigt `index.html`
- Benutzer tippt Namen ein → klickt „Say Hello“
- Browser sendet POST (Formulardaten)
- Spring verarbeitet die Daten und rendert wieder `index.html` mit Ergebnis

---

## ✅ Typische Ziel-Lösung (als Lernziel)

### Controller (Beispiel-Design)

- `GET /` → Formular anzeigen  
- `POST /hello` → Name auslesen, ins Model packen, Seite erneut anzeigen

**Wichtig:** Thymeleaf‑Templates sind normales HTML mit `th:*`‑Attributen.

---

## 📝 Aufgaben für Schüler

### Aufgabe 1 – GET/POST verstehen
1. Erkläre den Unterschied zwischen GET und POST.
2. Warum nimmt man für Formulare oft POST?

### Aufgabe 2 – Controller erstellen
1. Lege eine Klasse `HelloController` an.
2. Implementiere:
   - `@GetMapping("/")`
   - `@PostMapping("/hello")`

### Aufgabe 3 – Template verbessern (Thymeleaf)
1. Mache aus dem Template ein **valide HTML‑Datei**.
2. Baue ein Formular mit:
   - `method="post"`
   - `th:action="@{/hello}"`
3. Zeige die Ausgabe `Hallo, <Name>!` an, wenn ein Name vorhanden ist.

### Aufgabe 4 – Bonus
- Wenn das Eingabefeld leer ist: zeige eine Fehlermeldung („Bitte Namen eingeben“).
- Füge einen Button „Zurücksetzen“ hinzu.

---

## ⚠️ Hinweise

- Dieses Projekt ist **absichtlich klein**.
- Es geht um das Prinzip **Formular → POST → Verarbeitung**.
- Sicherheit, Datenbank und Styling sind hier **nicht** das Ziel.

---

## 📦 Nächste sinnvolle Erweiterungen

- Validierung mit `@NotBlank` + `BindingResult`
- DTO/Modelklasse statt einzelner Parameter
- Mehr Felder (z. B. E-Mail, Alter)
- Mehrere Seiten (z. B. `/about`)

---

Viel Erfolg beim Lernen! 🚀

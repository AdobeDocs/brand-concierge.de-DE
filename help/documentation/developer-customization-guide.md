---
title: Entwicklungs- und Anpassungshandbuch
description: Erfahren Sie, wie Sie die Brand Concierge Web SDK und den Web-Client installieren, das Erscheinungsbild und die Inhalte anpassen, Client-seitige Ereignisse behandeln und Konversationsdaten exportieren.
role: Developer,Admin
level: Experienced
toc: true
source-git-commit: 13db0491c987a08492820ac216e20feb87f30e44
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 4%

---


# Entwicklungs- und Anpassungshandbuch {#developer-customization-guide}

Dieses Handbuch richtet sich an Entwicklerinnen und Entwickler sowie an technische Teams, die eine Brand Concierge-Bereitstellung implementieren oder anpassen. Es behandelt die Installation des Web-SDK und des Web-Clients, die Anpassung von Erscheinungsbild und Inhalt, das Überwachen Client-seitiger Ereignisse über Rückruffunktionen und den Export von Gesprächsdaten für das Reporting.

## Web SDK- und Web Client-Installation {#installation}

### Voraussetzungen {#prerequisites}

* Das Unternehmen ist ein Kunde von Adobe Experience Platform (AEP).
* Die Seite ist mit dem Adobe Experience Platform Web SDK instrumentiert.
* Die auf der Seite verwendete Datenstrom-ID ist für Brand Concierge aktiviert.

### Schritt 1: Web-SDK einfügen {#inject-web-sdk}

Fügen Sie im `<head>` der Seite Folgendes hinzu:

```html
<script>
  !(function (n, o) {
    o.forEach(function (o) {
      n[o] ||
        ((n.__alloyNS = n.__alloyNS || []).push(o),
        (n[o] = function () {
          var u = arguments;
          return new Promise(function (i, l) {
            n[o].q.push([i, l, u]);
          });
        }),
        (n[o].q = []));
    });
  })(window, ["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.31.1/alloy.min.js"></script>
```

### Schritt 2: Webclient einfügen {#inject-web-client}

Fügen Sie nach dem Web SDK-Skript Folgendes hinzu, und zwar noch im Abschnitt `<head>` :

```html
<script src="https://experience.adobe.net/solutions/experience-platform-brand-concierge-web-agent/static-assets/main.js"></script>
```

### Schritt 3: Konfigurieren der Web-SDK {#configure-web-sdk}

Rufen Sie `alloy("configure", ...)` mit den eigenen Werten Ihrer Organisation anstelle der folgenden Platzhalter auf:

```javascript
alloy("configure", {
  defaultConsent: "in",
  edgeDomain: "edge.adobedc.net",
  edgeBasePath: "ee",
  datastreamId: "YOUR_DATASTREAM_ID",
  orgId: "YOUR_IMS_ORG_ID",
  debugEnabled: true,
  idMigrationEnabled: false,
  thirdPartyCookiesEnabled: false,
  prehidingStyle: ".personalization-container { opacity: 0 !important }",
  onBeforeEventSend: (options) => {
    const x = options.xdm;
    const params = new URLSearchParams(window.location.search);
    const titleParam = params.get("title");
    if (titleParam) {
      x.web.webPageDetails.name = titleParam;
    } else {
      x.web.webPageDetails.name = "default-page";
    }
    return true;
  }
});
alloy("sendEvent", {});
```

| Feld | Beschreibung |
|---|---|
| `datastreamId` | Die für diese Seite konfigurierte Datenstrom-ID, die für Brand Concierge aktiviert ist. |
| `orgId` | Die IMS-Organisations-ID, unter der der Concierge konfiguriert ist. |
| `debugEnabled` | Nach der Überprüfung der Integration in der Produktion auf `false` gesetzt. |
| `prehidingStyle` | CSS wird vor dem Laden von Personalisierungsinhalten angewendet, um ein Aufblitzen unformatierter Inhalte zu vermeiden. |
| `onBeforeEventSend` | Optionaler Hook zum Ändern der XDM-Payload vor dem Senden - wird häufig zum Festlegen des Seitennamens oder des Kontexts verwendet. |

### Schritt 4: Initialisieren des Web-Clients {#initialize-web-client}

Nach dem Aufruf von Web SDK configure initialisieren Sie den Web-Client, indem Sie die Bootstrap-API aufrufen:

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "alloy",
  stylingConfigurations: window.styleConfigurations,
  selector: "#brand-concierge-mount"
});
```

| Parameter | Typ | Erforderlich | Beschreibung |
|---|---|---|---|
| `instanceName` | string | Ja | Der Name der Web SDK-Instanz. |
| `stylingConfigurations` | JSON-Objekt | Ja | Die Konfiguration der Web-Client-Stile (siehe [Anpassung von Visual und Inhalten](#customization)). |
| `selector` | string | Ja | CSS-Auswahl für das HTML-Element, das vom Web-Client bereitgestellt wird. |
| `onEvent` | Funktion | Nein | Callback für Client-seitige Ereignisse (siehe [Client-seitige Ereignisse und Callback-Funktionen](#events)) |

## Visuelle und Inhaltsanpassung {#customization}

Das `stylingConfigurations` -Objekt, das an `bootstrap()` übergeben wird, steuert Erscheinungsbild, Verhalten und Text im gesamten Webclient. Es ist in mehrere Bereiche unterteilt.

### Metadaten {#metadata}

```javascript
"metadata": {
  "brandName": "Your Brand",
  "version": "1.0.0",
  "language": "en-US",
  "namespace": "brand-concierge"
}
```

### Verhalten {#behavior}

Steuert das funktionale Verhalten einzelner Chat-Funktionen.

```javascript
"behavior": {
  "input": {
    "enableVoiceInput": true
  },
  "chat": {
    "messageAlignment": "left",
    "messageWidth": "80%"
  },
  "privacyNotice": {
    "title": "Privacy Notice",
    "text": "By using this automated chatbot, you consent that any personal information you provide in the chat may be collected, used, analyzed, disclosed, and retained by Adobe and its service providers, in accordance with the Adobe Privacy Policy. Please do not enter any sensitive personal information (e.g., financial or health data)."
  },
  "disclaimer": {
    "attachWithInput": true
  },
  "chatTranscript": {
    "enabled": true,
    "maxSessions": 1,
    "maxMessagesPerSession": 20,
    "cleanupInterval": 24
  },
  "meetingForm": {
    "fieldsPerRow": 2,
    "title": { "text": "Schedule meeting", "alignment": "left" },
    "subtitle": { "text": "I'd be happy to help you schedule a meeting! Please fill out the form below, and we'll follow up with a calendar to confirm your day and time.", "alignment": "left" },
    "buttons": {
      "submit": { "text": "Schedule meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  },
  "calendarWidget": {
    "title": { "text": "Book a meeting", "alignment": "left" },
    "subtitle": { "text": "Thanks! Here's a calendar where you can choose a time that works best for your schedule:", "alignment": "left" },
    "postTitle": { "text": "Once confirmed, you'll receive a calendar invite with all the details.", "alignment": "left" },
    "buttons": {
      "confirm": { "text": "Schedule a meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  }
}
```

### Haftungsausschluss {#disclaimer}

```javascript
"disclaimer": {
  "text": "AI responses may be inaccurate or misleading. Be sure to double check answers and sources."
}
```

### Textzeichenfolgen {#text-strings}

Alle benutzerseitigen Kopien können über das `text`-Objekt überschrieben werden. Allgemeine Schlüssel:

| Schlüssel | Zweck |
|---|---|
| `welcome.heading` / `welcome.subheading` | Überschrift und Untertext des Begrüßungsbildschirms |
| `input.placeholder` | Platzhaltertext für Eingabefeld |
| `input.messageInput.aria` / `input.send.aria` / `input.mic.aria` | Barrierefreiheitsbeschriftungen für Eingabedialoge |
| `error.network` / `error.general` | Dem Besucher angezeigte Fehlermeldungen |
| `loading.message` | Text, der angezeigt wird, während eine Antwort generiert wird |
| `feedback.dialog.title.positive` / `.negative` | Feedback-Dialogfeldtitel |
| `feedback.dialog.question.positive` / `.negative` | Feedback Dialog Prompt Text |
| `feedback.toast.success` | Bestätigungs-Popup nach dem Senden des Feedbacks |
| `feedback.thumbsUp.aria` / `feedback.thumbsDown.aria` | Barrierefreiheitsbeschriftungen für Feedback-Schaltflächen |

### Arrays {#arrays}

Konfigurierbare Inhaltslisten:

```javascript
"arrays": {
  "welcome.examples": [
    {
      "text": "I want to edit and enhance my photos",
      "image": "https://example.com/idea-1.png",
      "backgroundColor": "#66BFE7"
    }
  ],
  "feedback.positive.options": [
    "Helpful and relevant recommendations",
    "Clear and easy to understand",
    "Friendly and conversational tone",
    "Visually appealing presentation",
    "Other"
  ],
  "feedback.negative.options": [
    "Not helpful or relevant",
    "Confusing or unclear",
    "Too formal or robotic",
    "Poor visual presentation",
    "Other"
  ]
}
```

### Assets {#assets}

```javascript
"assets": {
  "icons": {
    "company": "<svg>...</svg>"
  }
}
```

### Thema {#theme}

Benutzerdefinierte CSS-Eigenschaften zur Steuerung von Farben, Schriftarten und Layout:

```css
"theme": {
  "--color-primary": "#1473e6",
  "--color-primary-hover": "#0056b3",
  "--color-button-primary": "#3B63FB",
  "--color-accent": "#9085ED",
  "--color-button-submit": "#4759e6",
  "--color-button-submit-hover": "#3a4bce",
  "--color-message-user": "#1473e6",
  "--font-family": "'Adobe Clean', adobe-clean, 'Trebuchet MS', sans-serif",
  "--main-container-background": "linear-gradient(135deg, #66ccff, #cc99ff, #ffcc99, #ccff99)",
  "--submit-button-fill-color": "white",
  "--card-text-background": "var(--color-background)",
  "--card-text-border-radius": "var(--border-radius-card)",
  "--message-concierge-link-decoration": "underline",
  "--message-max-width": "100%"
}
```

## Client-seitige Ereignisse und Callback-Funktionen {#events}

Mit dem Ereignis-Callback-System kann eine Seite Web-Client-Lebenszyklusereignisse, Benutzerinteraktionen, Antworten, Feedback und Fehler in Echtzeit beobachten. Dies ist nützlich für das Senden von Interaktionsdaten an Adobe Analytics, Google Analytics oder andere Drittanbietersysteme.

### Hauptmerkmale {#key-characteristics}

* **Einzelner Callback** - Eine `onEvent` empfängt alle Ereignistypen, unterschieden nach `event.eventType`.
* **Schreibgeschützt** - Ereignisdaten sind ein geklonter Schnappschuss und können nicht verwendet werden, um das Verhalten des Clients zu ändern.
* **Fehlerisoliert** - Im Callback ausgelöste Ausnahmen werden erfasst und protokolliert. Sie beeinträchtigen nicht den Web-Client.
* **Registriert über`bootstrap()`** - genauso wie `onBeforeEventSend`.

### Schnellstart {#quick-start}

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "my-instance",
  selector: "#brand-concierge-mount",
  stylingConfigurations: { /* ... */ },
  onEvent: (event) => {
    console.log(event.eventType, event.timestamp, event.data);
  }
});
```

### Filtern nach Ereignistyp {#filtering}

```javascript
onEvent: (event) => {
  switch (event.eventType) {
    case "query:submitted":
      console.log("User query:", event.data.query);
      break;
    case "response:completed":
      console.log("Response received:", event.data.conversationId);
      break;
    case "card:clicked":
      console.log("Card clicked:", event.data.element.entity_info.productName);
      break;
    case "error:occurred":
      console.log("Error:", event.data.errorMessage);
      break;
  }
}
```

### Ereignistypen {#event-types}

| Ereignistyp | Wert | Kategorie | Wenn er ausgelöst wird |
|---|---|---|---|
| `WEBCLIENT_INITIALIZED` | `webclient:initialized` | Lebenszyklus | Client beendet die Initialisierung (DOM eingehängt, Inhalt geladen) |
| `QUERY_SUBMITTED` | `query:submitted` | Benutzerinteraktion | Benutzer sendet eine Nachricht (eingegeben oder von einem Vorschlag ausgehend) |
| `PROMPT_SUGGESTION_CLICKED` | `promptSuggestion:clicked` | Benutzerinteraktion | Benutzer klickt auf eine Vorschlagspille |
| `CARD_CLICKED` | `card:clicked` | Benutzerinteraktion | Benutzer klickt auf eine Karte |
| `HISTORY_CLEARED` | `history:cleared` | Benutzerinteraktion | Benutzer löscht den Chatverlauf |
| `RESPONSE_STARTED` | `response:started` | Antwort | Erster Streaming-Chunk kommt von der API |
| `RESPONSE_COMPLETED` | `response:completed` | Antwort | Vollständige Antwort wird empfangen und gerendert |
| `CARDS_RENDERED` | `cards:rendered` | Antwort | Karten (einzelnes Bild oder Karussell) fertig gerendert |
| `FEEDBACK_SUBMITTED` | `feedback:submitted` | Feedback | Benutzer sendet ein Feedback-Formular (mit Details nach oben/unten) |
| `ERROR_OCCURRED` | `error:occurred` | Fehler | Ein Fehler tritt auf (Netzwerk, API oder Laufzeit) |

### Lebenszyklus-Ereignisse {#lifecycle-events}

`webclient:initialized` wird ausgelöst, nachdem der Client vollständig initialisiert wurde: Inhalt geladen, CSS eingefügt, Chat-Benutzeroberfläche im DOM gerendert.

```json
{
  "eventType": "webclient:initialized",
  "timestamp": 1741638123789,
  "data": {
    "instanceName": "my-instance"
  }
}
```

### Benutzerinteraktionsereignisse {#user-interaction-events}

`query:submitted` wird ausgelöst, wenn der Benutzer eine Nachricht über eine Eingabeaufforderung oder eine Widget-Option sendet, unabhängig davon, ob sie eingegeben wurde oder nicht.

```json
{
  "eventType": "query:submitted",
  "timestamp": 1741638124000,
  "data": {
    "query": "What photo editing tools do you offer?"
  }
}
```

`promptSuggestion:clicked` wird ausgelöst, wenn der Benutzer auf eine Vorschlagspille klickt. Er löst *vor* das nachfolgende `query:submitted` aus.

```json
{
  "eventType": "promptSuggestion:clicked",
  "timestamp": 1741638124100,
  "data": {
    "suggestion": "Tell me more about Photoshop"
  }
}
```

`card:clicked` wird ausgelöst, wenn der Benutzer auf eine Karte klickt.

```json
{
  "eventType": "card:clicked",
  "timestamp": 1741638124200,
  "data": {
    "element": {
      "entity_info": {
        "productName": "Adobe Photoshop",
        "productDescription": "Photo editing software",
        "productPageURL": "https://www.adobe.com/de/products/photoshop.html",
        "productImageURL": "https://example.com/photoshop.png"
      }
    }
  }
}
```

`history:cleared` wird ausgelöst, wenn der Benutzer auf die Schaltfläche Chat-Verlauf löschen klickt.

```json
{
  "eventType": "history:cleared",
  "timestamp": 1741638124400,
  "data": {}
}
```

### Antwortereignisse {#response-events}

`response:started` wird ausgelöst, wenn der erste Streaming-Chunk von der API eingeht.

```json
{
  "eventType": "response:started",
  "timestamp": 1741638125000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`response:completed` wird ausgelöst, wenn die vollständige Antwort eingegangen ist.

```json
{
  "eventType": "response:completed",
  "timestamp": 1741638126000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`cards:rendered` wird nach dem Rendern von Karten im DOM ausgelöst. Er wird getrennt von `response:completed` ausgelöst und zeigt den verwendeten Anzeigemodus an.

```json
{
  "eventType": "cards:rendered",
  "timestamp": 1741638126100,
  "data": {
    "element": [
      { "entity_info": { "productName": "Adobe Photoshop" } },
      { "entity_info": { "productName": "Adobe Illustrator" } }
    ],
    "displayMode": "carousel"
  }
}
```

### Feedback-Ereignisse {#feedback-events}

`feedback:submitted` Wird ausgelöst, wenn Benutzende ein Feedback-Formular ausfüllen und senden (nach einem Daumen nach oben/unten).

```json
{
  "eventType": "feedback:submitted",
  "timestamp": 1741638127000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456",
    "feedbackType": "negative",
    "selectedOptions": ["Incorrect information", "Not relevant"],
    "notes": "The response did not address my question about pricing."
  }
}
```

### Fehlerereignisse {#error-events}

`error:occurred` wird ausgelöst, wenn ein Netzwerk-, API- oder Laufzeitfehler auf dem Client auftritt.

```json
{
  "eventType": "error:occurred",
  "timestamp": 1741638128000,
  "data": {
    "errorMessage": "Something went wrong. Please try again."
  }
}
```

### Ereignisobjektstruktur {#event-object-structure}

Jedes Ereignis hat dieselbe Form auf oberster Ebene:

```typescript
interface BrandConciergeEvent {
  eventType: string;  // e.g. "query:submitted"
  timestamp: number;  // Unix epoch, milliseconds
  data: object;       // Event-specific payload
}
```

### Datentypreferenz: Element (Produktkarte) {#element-reference}

```typescript
interface Element {
  id?: string;
  type?: string;
  entity_info: {
    productName: string;
    productDescription: string;
    description: string;
    productPageURL: string;
    details: string;
    backgroundColor: string;
    learningResource: string;
    productImageURL: string;
    logo: string;
    variants?: Record<string, ElementVariant>;
    primary: ElementAction;
    secondary: ElementAction;
  };
}

interface ElementAction {
  label: string;
  url: string;
}
```

### Best Practices {#best-practices}

* **Für Analyse und Überwachung verwenden.** Verfolgen Sie Interaktionen, Abfragemuster und Produktinteressen; leiten Sie `error:occurred` an einen Fehlerverfolgungsdienst weiter; verfolgen Sie Kartenklicks für die Konversionsanalyse.
* **Halten Sie den Callback schnell.** Sie wird synchron auf dem Haupt-Thread ausgeführt. Vermeiden Sie daher das Blockieren von Netzwerkaufrufen:

```javascript
// Good — fire and forget
onEvent: (event) => {
  navigator.sendBeacon("/analytics", JSON.stringify(event));
}

// Avoid — blocking network call
onEvent: async (event) => {
  await fetch("/analytics", { body: JSON.stringify(event) });
}
```

* **Verlassen Sie sich nicht auf eine strikte Ereignisreihenfolge** für Statuscomputer. Ereignisse werden in einer logischen Sequenz ausgelöst, aber verwenden `conversationId` und `interactionId`, um verwandte Ereignisse zu korrelieren, anstatt eine Reihenfolge anzunehmen.
* **Fehler in Ihrem eigenen Callback behandeln.** Der Client isoliert und protokolliert Callback-Fehler, aber nicht behandelte Fehler innerhalb des Callbacks können weiterhin Analysedaten verlieren:

```javascript
onEvent: (event) => {
  try {
    myAnalytics.track(event);
  } catch (e) {
    console.warn("Analytics tracking failed", e);
  }
}
```

## Exportieren von Unterhaltungen mit dem Abfrage-Service von AEP {#export-conversations}

Brand Concierge schreibt Gesprächsdaten - Eingabeaufforderungen, Antworten und Feedback - in Adobe Experience Platform (AEP)-Datensätze. Sie können diese direkt mit dem Abfrage-Service (SQL) abfragen, um benutzerdefinierte Berichte zu erstellen.

### Datensatz und Tabellennamen suchen {#find-dataset}

1. Öffnen Sie Adobe Experience Platform.

1. Navigieren Sie zu **[!UICONTROL Datensätze]**.

1. Suchen Sie nach `cja_brand_concierge`, um die Datensätze aufzulisten, die mit Brand Concierge verbunden sind.

1. Öffnen Sie den benötigten Datensatz (z. B. Antworten versus andere Flüsse, wenn mehr als einer vorhanden ist).

1. Suchen Sie in der Ansicht mit den Datensatzdetails den **[!UICONTROL Tabellennamen]**, der vom Abfrage-Service verwendet wird, und überprüfen Sie die Beispiel- oder Vorschaudaten, um die Spalten (Eingabeaufforderungen, Antworten, Feedback, Zeitstempel usw.) zu bestätigen.

>[!NOTE]
>
>Tabellennamen sind an jeden Datensatz gebunden und unterscheiden sich je nach Umgebung und Sandbox. Wenn Sie mehrere Sandboxes oder Bereitstellungen haben, wiederholen Sie diese Schritte in der richtigen Sandbox, damit der Tabellenname mit dem Namen übereinstimmt, in den die Daten geschrieben werden.

### Beispielabfrage {#example-query}

```sql
SELECT *
FROM cja_brand_concierge_responses_dataset_5f5105bd_1c38_4ebc_8505_bd
WHERE timestamp >= TIMESTAMP '2026-03-16 00:00:00'
  AND timestamp <= NOW()
ORDER BY timestamp ASC;
```

>[!IMPORTANT]
>
>Der obige Tabellenname ist nur eine Illustration - programmieren Sie ihn nicht hartcodiert. Bestätigen Sie zunächst den tatsächlichen Tabellennamen für Ihren Datensatz in AEP (siehe [Suchen des Datensatzes und des Tabellennamen](#find-dataset)) und passen Sie den Zeitfilter, die Sortierreihenfolge oder andere Klauseln an, um Ihre Reporting-Anforderungen zu erfüllen. Führen Sie die Abfrage über den Abfrage-Service-Workflow Ihres Unternehmens (Benutzeroberfläche, API oder verbundener Client) aus und verwenden Sie dabei dieselbe Sandbox wie den Datensatz.

### Ausführen einer Abfrage in der Abfrage-Service-Benutzeroberfläche {#run-query-ui}

Wenn Sie einen manuellen Daten-Pull für das Reporting benötigen, bietet die Abfrage-Service-Benutzeroberfläche eine Möglichkeit, die Ergebnisse direkt auszuführen und herunterzuladen:

1. Navigieren Sie in Adobe Experience Platform zu **[!UICONTROL Abfragen]**.

1. Geben Sie die Abfrage im Editor ein und klicken Sie auf **[!UICONTROL Abfrage]**.

1. Die Ergebnisse werden auf der **[!UICONTROL Ergebnisse]** unterhalb des Editors angezeigt, sobald die Abfrage abgeschlossen ist. Dort können Sie die Ergebnisse herunterladen.

### Weitere Informationen {#further-reading}

* [Dokumentation zur Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home){target="_blank"} - Die offizielle Referenz von Adobe für das Verhalten, die Beschränkungen, die Authentifizierung und die API-Pfade des Abfrage-Service, die sich im Laufe der Zeit unabhängig von diesem Handbuch ändern.

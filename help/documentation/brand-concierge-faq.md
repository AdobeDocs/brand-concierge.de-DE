---
title: Häufig gestellte Fragen
description: Erhalten Sie Antworten auf häufig gestellte Fragen zu Adobe Brand Concierge.
role: User,Admin
level: Beginner
source-git-commit: 06911f38d17882cdae8441d5cbdbcdf786d9e6bb
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 1%

---

# Häufig gestellte Fragen

In diesem Abschnitt finden Sie Antworten auf häufig gestellte Fragen zu Brand Concierge.

## Allgemein

### Wozu dient Brand Concierge? Welches Problem löst es?

Weitere Untersuchungen finden auf externen KI-Tools (z. B. ChatGPT, Gemini) statt auf Marken-Websites. Besucher wollen zunehmend „zur Sache kommen“ - z. B. „Erzählen Sie mir von X“, „Kann ich Y tun?“ Mit Brand Concierge können Sie diese Konversation auf Ihrer Site fortsetzen: Wenn Besucher auf Ihren Seiten landen (einschließlich über einen KI-Assistenten), können sie die Konversation mit einem auf Ihren Inhalten geschulten Assistenten fortsetzen. Sie können ein konsistentes, markenbezogenes Erlebnis bereitstellen, anstatt sie an allgemeine Antworten an anderer Stelle zu verlieren.

### Wie unterscheidet sich Brand Concierge von Chatbots?

Brand Concierge unterscheidet sich von herkömmlichen Chatbots durch die Nutzung generativer KI, die speziell auf die Inhalte und Kundendaten Ihres Unternehmens trainiert ist, anstatt sich auf skriptbasierte Antworten oder allgemeine Web-Ergebnisse zu verlassen. Auf diese Weise kann der Assistent personalisierte Antworten bereitstellen, die durch das individuelle Kundenverhalten informiert sind, sich tief in Ihre Adobe-Tools und -Daten integrieren, kontinuierlich aus jeder Interaktion lernen und die Kundeninteraktion über den grundlegenden Keyword-Abgleich hinaus korrekt interpretieren.

### Kann ich Brand Concierge sowohl für B2C als auch für B2B verwenden?

Ja. Anwendungsfälle sind:

* **B2C:** Produktsuche, Einkaufshilfe, Support, personalisierte Empfehlungen.
* **B2B**: Geführte Auswertungen, Funktionsvergleiche, Besprechungsplanung, Routing von Vertriebsmitarbeitern, Beratungsbuchung.

### Welche Branchen können Brand Concierge verwenden?

Brand Concierge kann in einer Vielzahl von Branchen eingesetzt werden, einschließlich Einzelhandel und E-Commerce, Reisen und Gastgewerbe, Finanzdienstleistungen, Gesundheitswesen (mit Compliance-Kontrollen), Medien und Unterhaltung sowie Technologie und Software. Grundsätzlich kann jede Branche, die Kunden dabei unterstützt, Informationen zu finden und Entscheidungen zu treffen, von der Implementierung von Brand Concierge profitieren.

## Daten und Datenschutz

### Sind Kundendaten sicher?

Ja. Brand Concierge stellt die Sicherheit von Kundendaten sicher, indem es die DSGVO- und CCPA-Compliance einhält, Daten in der sicheren Adobe-Infrastruktur verarbeitet, Ihnen die Kontrolle über die Datennutzung bietet und Konversationen durch Verschlüsselung und Auditprotokollierung schützt.

Alle Unterhaltungen erfolgen in Ihren Eigenschaften, nicht auf Servern von Drittanbietern.

### Welche Datenquellen kann ich verbinden?

Sie können die folgenden Arten von Datenquellen mit Brand Concierge verbinden:

| Source-Datentyp | Verfügbare Quellen/Details |
|------------------|---------------------------|
| **Produkt und Inhalt** | Produktkataloge<br>Inventarsysteme<br>Wissensdatenbanken und Dokumentation<br>Website-Inhalt über CSV-URL-Upload<br>Adobe Experience Manager-Inhalt<br>Adobe Commerce-Daten |
| **Kundendaten** | Adobe Experience Platform-Profile<br>Adobe Analytics<br>VerhaltensdatenKundenattribute von Erstanbietern<br>APIs von Drittanbietern (konfiguriert) |
| **CSV-Dateiformat** | Eine Spalte mit Website-URLs<br>Brand Concierge crawlen URLs und extrahiert Inhalte automatisch<br>Statusaktualisierungen werden in Echtzeit verarbeitet<br>Für verschiedene Inhaltsbereiche können mehrere CSV-Dateien hochgeladen werden |

Alle Daten entsprechen Ihren Governance-Regeln.

### Können Kundinnen und Kunden die Personalisierung deaktivieren?

Ja. Kunden, die sich abmelden, erhalten hilfreiche Antworten ohne Verhaltens-Personalisierung. Sie konfigurieren die Handhabung von Opt-outs entsprechend Ihren Datenschutzrichtlinien.

### Gibt es Auswirkungen auf die Zustimmung oder den Datenschutz?

Ja. **Gesprächsdaten:** Wenn das Gespräch personenbezogene oder identifizierbare Informationen enthält, müssen Sammlung, Speicherung und Verwendung Ihren Einwilligungs- und Datenschutzrichtlinien entsprechen (z. B. DSGVO, CCPA). **Analytics:** Wenn der Concierge Ereignisse an Experience Platform oder Analytics sendet, können diese Ereignisse Ihrer bestehenden Zustimmung und Governance unterliegen (z. B. Einverständniszeichenfolgen, Datennutzungskennzeichnungen). Wir empfehlen, Concierge wie jedes andere digitale Erlebnis der ersten Partei zu behandeln: Stellen Sie sicher, dass das Einverständnisbanner und die Voreinstellungen Ihrer Site Gesprächs- und Chat-Daten und Analysen abdecken und Ereignisdaten an Ihre Einverständnisstrategie anpassen. Rechtliche und Compliance-Prüfungen vor der Live-Schaltung durchführen lassen.

## Profile und Personalisierung

### Verwendet der Concierge Kundenprofile (z. B. Real-Time CDP), um die Antworten anzupassen? Was passiert, wenn der Besucher gerade eine Journey durchläuft?

Im aktuellen Umfang konzentriert sich der Concierge auf anonyme Besucher: Er antwortet aus dem Gespräch und Ihrer Wissensdatenbank (Website und Katalog), nicht aus einer Live-Suche nach Identität oder Journey-Status in Real-Time CDP. Zu den Roadmap-Funktionen gehören Lead-Pflege, Übergabe an den Vertrieb und Retargeting, die sich stärker an bekannten Profilen und dem Journey-Kontext ausrichten. Anpassen der Antworten nach „Hat dieser Besucher ein Profil?“ oder „Wo sind sie in einer Journey?“ ist eine zukünftige Verbesserung. Derzeit ist das Erlebnis für anonyme Besucher konsistent.

## Rollout und Zeitleiste

### Wie lange dauert es in der Regel, bis das System live geschaltet wird?

Durch parallele Arbeit und aktive Zusammenarbeit können viele Implementierungen in etwa 6-9 Wochen live gehen. Die Staging-Umgebung kann schnell gestartet werden, sobald Ihre Eingaben (URLs, Katalog, Markenrichtlinien) fertig sind. Nach der Vereinbarungs- und Produktionseinrichtung erfolgen Qualitätsoptimierung und gesteuerter Rollout (z. B. 5 % und anschließende Skalierung auf 100 % innerhalb einer Woche).

## Konfiguration und Steuerung

### Wie kontrolliere ich die Markensprache?

Sie können Ihre Markensprache direkt in der Benutzeroberfläche steuern, indem Sie Elemente wie Ton (von formal bis beiläufig), Sprache (von einfach bis technisch) und Persönlichkeit (z. B. hilfreich, enthusiastisch oder professionell) konfigurieren. Darüber hinaus können Sie mithilfe von Vorlagen und Beispielen Antwortmuster definieren und Schutzmaßnahmen zur Durchsetzung von Compliance-Regeln und -Grenzen festlegen. Beginnen Sie mit den Referenzaufforderungen von Adobe und passen Sie diese Einstellungen an die eindeutige Identität Ihrer Marke an.

### Was passiert, wenn Brand Concierge eine Frage nicht beantworten kann?

Sie können Fallback-Verhalten konfigurieren, um zu bestimmen, wie Brand Concierge reagiert, wenn es eine Frage nicht beantworten kann. Zu den Optionen gehören die Anzeige einer anmutigen „Ich kann bei dieser Nachricht nicht helfen“-Nachricht, das Vorschlagen alternativer Fragen, das Verknüpfen mit Selbsthilfe-Ressourcen oder das automatische Eskalieren der Anfrage an einen menschlichen Agenten. Wählen Sie aus, was für Ihre Marke am besten funktioniert.

### Kann ich das visuelle Design anpassen?

Ja. Anpassen aller visuellen Elemente, einschließlich:

* Farben und Branding
* Schriftarten und Typografie
* Schaltflächenstile
* Widget-Positionierung
* Karten-Layouts
* Antwortformatierung

SDKs bieten Standardkomponenten und vollständige Anpassungsoptionen.

### Wie lange dauert die Einrichtung?

Die Dauer der Einrichtung kann von der Art der Implementierung abhängen. Die Einrichtung einer einfachen Implementierung, die einen vorhandenen Produktkatalog, standardmäßige FAQ-Inhalte und Standardeinstellungen enthält, kann etwa 3-5 Tage dauern. Andererseits kann es etwa 2-4 Wochen dauern, bis erweiterte Implementierungen mit benutzerdefinierten Integrationen, umfassender Personalisierung, komplexen Workflows und benutzerdefinierten Compliance-Regeln abgeschlossen sind.

### Wie funktioniert die Vorschau und das Testen?

Brand Concierge umfasst integrierte Test-Tools:

| Test-Tool | Funktionen |
|--------------|----------|
| **Vorschaumodus** | Kundengespräche simulieren<br> Einstellungen in Echtzeit anpassen<br> Änderungen sofort anzeigen<br> Vorschaulinks für Ihr Team freigeben |
| **Tester-Ansicht** | Antworten mit Daumen nach oben/unten bewerten<br>Strukturiertes Feedback für vier Kategorien bereitstellen<br>Detaillierte Kommentare hinzufügen<br> Feedback im Dashboard verfolgen |

Alle Tests finden vor der Bereitstellung für Kunden statt.

### Können Kunden Besprechungen mit unserem Team planen?

Ja, Kundinnen und Kunden können Meetings mit Ihrem Team über die Fähigkeit „Meeting-Buchung“ planen. Um diese Funktion zu aktivieren, aktivieren Sie die Skill-in-Skills-Konfiguration, definieren Sie Aktivierungsabsichten (wie „Sprechen Sie mit dem Vertrieb„), verbinden Sie Ihr Kalender- oder Terminsystem und legen Sie Ihre Verfügbarkeits- und Besprechungstypen fest. Nach der Konfiguration können Kundinnen und Kunden Meetings während der Gespräche anfordern. Brand Concierge erleichtert den Planungsprozess, ohne dass sie den Chat verlassen müssen.

### Wer kümmert sich um das Prompt Engineering?

Adobe-Berater kümmern sich im Hintergrund um das Prompt Engineering:

1. Konfigurationsfragen beantworten Sie auf der Seite Kenntnisse .
1. Bereitstellen von Produktwissen, Geschäftsregeln und Vermeiden von Keywords.
1. Senden Sie Ihre Eingaben.
1. Adobe-Berater verwenden Ihre Antworten, um optimierte Eingabeaufforderungen zu erstellen.
1. Änderungen werden automatisch in Ihrem Concierge reflektiert.

Dadurch wird sichergestellt, dass Ihr Concierge Best-Practice-KI-Eingabeaufforderungsmuster verwendet und gleichzeitig Ihre spezifischen Markenanforderungen erfüllt.

## Markenausdruck und -ton

### Wenn ich in Brand Expression „verspielt und begeistert“ festlege, übertreibt dann die KI dies?

Das kann es. Einige Kunden haben berichtet, dass die KI dazu neigt, die Begeisterung zu übertreiben, wenn sie auf „spielerisch und enthusiastisch“ eingestellt ist - zum Beispiel doppelte Ausrufezeichen oder starke Superlative. Für regulierte oder medizinische Zielgruppen (z. B. Pharma, frühe Ernährung) empfehlen wir, Begeisterung und Verspieltheit auszuwählen und dabei den Ton gesprächig und lässig zu halten. Verwenden Sie moderate Einstellungen und richten Sie sich nach dem Feedback. Lehnen Sie sich bei regulierten Branchen eher nach „Gespräch“ als nach „Begeisterung“ ab.

## Leistung und Analysen

### Wie kann ich den Erfolg messen?

Sie können den Erfolg mithilfe des Brand Concierge-Dashboards messen. Verwenden Sie das Dashboard, um Metriken wie die folgenden zu verfolgen:

| Metrik | Nachverfolgte Inhalte |
|--------|----------------|
| **Interaktion** | Gesprächsvolumen, Sitzungslänge |
| **Zufriedenheit** | Sentiment-Bewertungen, Feedback-Bewertungen |
| **Konversion** | Kaufraten für unterstützte und nicht unterstützte Projekte |
| **Themen** | Häufigste Fragen und Anfragen |
| **Übergabe** | Eskalationsraten und -gründe |
| **Leistung** | Reaktionsgenauigkeit, Auflösungszeit |

Sie können auch eine Integration mit Adobe Analytics vornehmen, um eine tiefere Analyse zu ermöglichen.

### Was sollte ich tun, wenn Sentiment herunterfällt?

Wenn Sie einen Rückgang beim Sentiment bemerken, untersuchen Sie die zugrunde liegenden Ursachen, indem Sie kürzlich fehlgeschlagene Abfragen durchgehen, nach Inhaltslücken suchen, negatives Feedback analysieren, den richtigen Ton testen und technische Probleme überprüfen. Sobald die Grundursachen erkannt wurden, sollten Sie diese umgehend beheben und die Verbesserung weiterhin überwachen.

## Integration und technische

### Benötige ich weitere Adobe-Produkte?

Nein, aber sie verbessern die Leistung:

| Integrationsoption | Funktionen |
|-------------------|--------------|
| **Eigenständig** | Funktioniert mit Ihrem Produktkatalog und Ihren Inhalten |
| **mit Adobe Experience Platform** | Einheitliche Kundenprofile<br>Erweiterte Personalisierung<br>Kanalübergreifende Konsistenz |
| **mit Adobe Commerce** | Echtzeit-Integration <br> Bestands-/<br> |
| **mit Adobe Experience Manager** | Content-Management<br>dynamische Aktualisierungen<br> Unterstützung mehrerer Websites |

### Was passiert, wenn meine Site nicht auf Adobe verfügbar ist?

Brand Concierge arbeitet mit jeder Plattform zusammen. JavaScript SDK lässt sich mit jeder Website integrieren, und mobile SDKs funktionieren mit jedem App-Backend.

### Wie funktioniert die Übergabe von Agenten?

Wenn die Agenten-Übergabe ausgelöst wird, überträgt Brand Concierge den gesamten Konversationsverlauf, das Kundenprofil und die ID, die identifizierte Absicht, Details zu den besprochenen Produkten und alle Lösungsversuche an den Agenten. Dadurch wird sichergestellt, dass Kundendienstmitarbeiter über den vollständigen Kontext verfügen und das Gespräch nahtlos fortsetzen können, ohne dass Kunden Informationen wiederholen müssen.

### Kann ich mehrere Sprachen unterstützen?

Ja. Konfigurieren Sie den Sprachsupport pro Assistent basierend auf Ihrem Kundenstamm. Brand Concierge erkennt die Kundensprache und reagiert entsprechend.

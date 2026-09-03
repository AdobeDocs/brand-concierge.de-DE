---
title: Analysieren der Concierge-Leistung
description: Erfahren Sie, wie Sie Concierge-Analysen durchgehen, Gesprächsprotokolle einsehen, Fragen von Besuchern zu Auswertungssets hinzufügen und Customer Journey Analytics-Berichte öffnen können.
hide: true
source-git-commit: da4b30fa292b911987aebec378af420b293ea594
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---


# Analysieren der Concierge-Leistung

**Für wen ist das?** Marketing-Experten, die das Self-Service-Erlebnis verwenden. Nach dem Einsatz des Concierge ist kein Setup erforderlich.

**Empfohlene Kadenz** Überprüfen Sie die Analyse nach Bedarf. Ein wöchentlicher Check-in ist ein vernünftiger Ausgangspunkt.

Mithilfe von Analytics können Sie verstehen, wie Besucher mit einem Live-Concierge interagieren. Nach der Bereitstellung zeigt die **Analytics**-Registerkarte automatisch Konversationsmetriken an und bietet Zugriff auf individuelle Transkripte und einen detaillierteren Customer Journey Analytics-Bericht.

## Anzeigen von Analysen

1. Öffnen Sie den Concierge und wählen Sie die Registerkarte **Analytics** aus.

1. Legen Sie den Datumsbereich für den Zeitraum fest, den Sie überprüfen möchten.

1. Filtern Sie die Ergebnisse optional nach Konversationstyp.

Auf der Registerkarte Analytics werden automatisch die folgenden Metriken angezeigt:

| Metrik | Beschreibung |
|---|---|
| Konversationen | Die Anzahl der Unterhaltungen während des ausgewählten Zeitraums. |
| Interaktive Besucher | Die Anzahl der Besucher, die mit dem Concierge interagiert haben. |
| Positive Sentiment | Die Menge an positivem Sentiment, die in Gesprächen identifiziert wurde. |
| Nachrichten pro Konversation | Die durchschnittliche Anzahl der in einer Konversation ausgetauschten Nachrichten. |

>[!NOTE]
>
>Nachdem der Concierge bereitgestellt wurde, ist keine Konfiguration erforderlich, um diese Metriken anzuzeigen.

## Gesprächstranskripte überprüfen

Mithilfe von Gesprächsprotokollen können Sie überprüfen, was Besucher gefragt haben und wie der Concierge reagiert hat.

1. Wählen Sie auf der Registerkarte Analytics eine Konversation aus.

1. Lesen Sie das vollständige Transkript.

1. Überprüfen Sie, ob Besucher für einzelne Antworten eine Daumen-Hoch- oder Daumen-Runter-Bewertung ausgewählt haben.

Jede Konversation hat eine eindeutige Konversations-ID. Verwenden Sie diese ID, um das Transkript mit Datensätzen in anderen Systemen abzugleichen, wenn Ihre Implementierung diesen Workflow unterstützt.

### Hinzufügen einer Konversation zu einem Auswertungssatz

Wenn ein Besucher eine Frage stellt, die für zukünftige Tests nützlich ist, fügen Sie sie direkt einem Auswertungssatz aus dem Transkript hinzu.

1. Öffnet das Gesprächstranskript.

1. Wählen Sie **Zu Auswertung hinzufügen** aus.

Das Hinzufügen echter Besucherfragen hilft, Auswertungssets auf den Fragen zu gründen, die Besucher tatsächlich stellen. Weitere Informationen zu Auswertungssets finden Sie unter [Einen Concierge &#x200B;](../evaluation/evaluation.md).

>[!TIP]
>
>Lesen Sie die Transkripte regelmäßig und fügen Sie repräsentative Fragen hinzu, nicht nur Fragen, die negatives Feedback erhalten haben, um einen ausgewogenen Auswertungssatz beizubehalten.

## Öffnen des Customer Journey Analytics-Berichts

Wählen Sie **Bericht anzeigen**, um ein detaillierteres Dashboard in Adobe Customer Journey Analytics (CJA) zu öffnen. Das Dashboard wird automatisch bereitgestellt und erfordert keine zusätzliche Konfiguration.

Das CJA-Dashboard umfasst:

- Wöchentliche Unterhaltungstrends.
- Wiederholte Interaktionen, einschließlich Gespräche pro Person.
- Nachrichten pro Konversation.
- Trends beim Besucher-Feedback.
- Besucherabsicht.
- Sentiment und Ton des Besuchers.
- Empfehlungen des Concierge während der Gespräche.

Verwenden Sie das Dashboard, um Trends im Zeitverlauf zu untersuchen und Änderungen bei der Besucherinteraktion, beim Feedback, bei der Absichtserklärung und beim Sentiment festzustellen.

>[!IMPORTANT]
>
>Konversations-IDs nicht als Export-Workflow behandeln. Bevor Sie dokumentieren, wie Konversationen oder Transkripte exportiert werden, benötigen Sie eine dedizierte exemplarische Vorgehensweise des Produkt- oder Engineering-Teams.

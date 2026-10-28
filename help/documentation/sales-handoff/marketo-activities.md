---
title: Brand Concierge-Daten in Marketo Engage
description: Machen Sie sich mit den Feldern der Lead-Quelle und den drei in Adobe Marketo Engage geschriebenen Typen von Concierge-Aktivitäten vertraut und erfahren Sie, wie Sie diese in Smart Lists und Smart Campaign verwenden können.
role: User, Admin
level: Beginner
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 4%
---
# Brand Concierge-Daten in Marketo Engage {#marketo-activities}

Wenn [!DNL Adobe Marketo Engage] verbunden ist, wird jeder Besucher, der ein Formular ausfüllt, ein Meeting bucht oder einen Live-Chat beginnt, zu einer Person, die in [!DNL Marketo] aufzeichnet, und seine Concierge-Interaktion wird als native Aktivitätstypen in diesen Datensatz geschrieben. Das bedeutet, dass Sie Smart Lists und Smart Campaign auf Concierge-Verhalten genau wie bei jeder anderen [!DNL Marketo]-Aktivität erstellen können.

>[!NOTE]
>
>Live-Chat und Meeting-Buchung selbst erfordern keine [!DNL Marketo Engage]. Ohne diese Daten bleiben die auf dieser Seite beschriebenen Daten in [!DNL Adobe Marketo Qualifier]. Siehe [Live-Chat und Besprechungsbuchung - Übersicht](overview.md#prerequisites).

## Lead-Erstellung und Quellattribution {#lead-creation}

Eine Person, die von einem Concierge erstellt wurde, wird getaggt, damit Sie immer wissen, woher sie stammt.

| Feld | Wert |
| --- | --- |
| **[!UICONTROL Person Source]** | `Brand Concierge` |
| **[!UICONTROL Original-Source-Typ]** | `Chat` |
| **[!UICONTROL Original Source Info]** | `Concierge` |
| **[!UICONTROL Registrierungs-Source-Typ]** | `Chat` |
| **[!UICONTROL Informationen zur Registrierung in Source]** | `Concierge` |

![Registerkarte mit Informationen zu Marketo-Personendatensätzen, auf der die auf Brand Concierge eingestellte Personen-Source sowie die Quellenfelder Chat und Concierge angezeigt werden](../assets/sales-handoff-marketo-1.png){width="800" zoomable="yes"}

## Aktivitätstypen {#activity-types}

Drei native Aktivitätstypen werden an den Personendatensatz gepusht. Alle drei sind als Trigger und Filter verfügbar.

![Marketo-Aktivitätsprotokoll für eine Person, die „Mit Concierge interagieren“ anzeigt, „Besprechung in Concierge planen“ und „Mit Live-Chat in Concierge-Einträgen interagieren“](../assets/sales-handoff-marketo-2.png){width="800" zoomable="yes"}

### Interagieren mit dem Concierge {#engage-with-concierge}

Protokolliert, wenn ein Besucher den Concierge kontaktiert.

| Attribut | Beschreibung |
| --- | --- |
| Name des Portiers | Der Concierge, mit dem sich der Besucher beschäftigte |
| Konversations-ID | Die Kennung der Konversation. In Composer verwenden, um das vollständige Transkript zu öffnen |
| „Seiten-URL“ | Die Seite, auf der die Interaktion stattfand |
| Erstellt um | Zeitpunkt der Erstellung der Konversation |
| Dauer | Wie lange das Gespräch dauerte |

>[!NOTE]
>
>Einige Attribute dieses Aktivitätstyps, einschließlich erörterter Themen, Zusammenfassung und Sprache, sind für eine künftige Version geplant.

### Besprechung in Concierge planen {#schedule-meeting}

Sie werden zweimal für eine einzelne Buchung protokolliert, wodurch Sie die Absicht vom Ergebnis trennen können.

Zunächst bei Initiierung: Der Besucher wählte die Option, ein Meeting zu planen, und das Buchungsformular erschien. Meeting-Status ist `Started`.

| Attribut | Beschreibung |
| --- | --- |
| Meeting-Status | `Started` |
| „Seiten-URL“ | Die Seite, auf der der Besucher die Buchung initiiert hat |
| Concierge-Ausweis | Der Concierge, mit dem sich der Besucher beschäftigte |
| Personen-ID | Der Datensatz für [!DNL Marketo] Personen |

Dann bei der Buchung: Der Besucher bestätigte einen Slot. Meeting-Status ist `Scheduled`.

| Attribut | Beschreibung |
| --- | --- |
| Meeting-Status | `Scheduled` |
| Name des Vertriebsmitarbeiters | Der Vertreter, bei dem das Meeting gebucht wurde |
| E-Mail an Vertriebsmitarbeiter | Die E-Mail-Adresse des Vertreters |
| Geplant für | Datum und Uhrzeit des Meetings |
| Besprechungsdauer | Die Dauer der gebuchten Besprechung |
| Routing-Typ | Der Routing-Typ, der diesen Vertreter ausgewählt hat |
| „Seiten-URL“ | Die Seite, auf der der Besucher gebucht hat |
| Concierge-Ausweis | Der Concierge, mit dem sich der Besucher beschäftigte |
| Personen-ID | Der Datensatz für [!DNL Marketo] Personen |

>[!TIP]
>
>Erstellen Sie eine Smart List von Personen, deren `Meeting Status` `Started`, aber nicht `Scheduled` ist, um alle Personen zu finden, die mit der Buchung eines Meetings begonnen und dieses aufgegeben haben. Dies ist eine vorgefertigte Zielgruppe für das Nurture-Team oder das Retargeting.

### Interagieren mit Live-Chat im Concierge {#engage-with-live-chat}

Protokolliert, nachdem ein Live-Chat beendet wurde.

| Attribut | Beschreibung |
| --- | --- |
| Unterhaltungsstatus | `Ended` ob der Chat absichtlich geschlossen wurde, `Dropped` ob der Besucher die Website verlassen hat und der Chat eine Zeitüberschreitung aufweist |
| Benachrichtigte Agenten | Die E-Mail-Adressen jedes Vertreters, der über diesen Chat benachrichtigt wurde |
| Konversationswert | Die Bewertung 0 zu 3, die der Vertreter für die Konversation angegeben hat. Siehe [Bewerten der Konversation](chat-inbox.md#conversation-score) |
| „Seiten-URL“ | Die Seite, auf der der Live-Chat gestartet wurde |
| Concierge-Ausweis | Der Concierge, mit dem sich der Besucher beschäftigte |
| Sitzungs-ID | Die Kennung der Live-Chat-Sitzung |
| Startzeit | Wann der Chat begonnen hat |

>[!TIP]
>
>Konversationswert ist hier das Attribut mit dem höchsten Wert, weil ein Mensch, der tatsächlich mit dem Besucher gesprochen hat, es festgelegt hat. Verwenden Sie ihn für Lead-Scoring, Retargeting, Personalisierung und Übergabe an Vertrieb und CRM.

## Verwenden von Concierge-Daten in einer Smart Campaign {#smart-campaign}

Suchen Sie in der **[!UICONTROL Smart List]** einer Smart-Kampagne nach `concierge`, um alle verfügbaren Informationen anzuzeigen.

![Smart List von Marketo mit den für Brand Concierge-Aktivitäten verfügbaren Concierge-Triggern und -Filtern](../assets/sales-handoff-marketo-3.png){width="800" zoomable="yes"}

| Kategorie | Verfügbare Elemente |
| --- | --- |
| **[!UICONTROL Triggers]** | Interagiert mit Concierge, Interagiert mit Live-Chat im Concierge, Termine Besprechung im Concierge |
| **[!UICONTROL Filter]** > **[!UICONTROL Aktivitätsverlauf]** | Interagiert mit Concierge, Interagiert mit Live-Chat im Concierge, Geplantes Meeting im Concierge |
| **[!UICONTROL Filter]** > **[!UICONTROL Inaktivitätsfilter]** | Nicht mit Concierge interagiert, Nicht mit Live-Chat im Concierge interagiert, Nicht geplante Besprechung im Concierge |

Ziehen Sie einen Trigger oder Filter auf die Arbeitsfläche und wählen Sie dann **[!UICONTROL Einschränkung hinzufügen]** aus, um sie einzugrenzen.

### Begrenzungen {#constraints}

| Trigger oder Filter | Begrenzungen |
| --- | --- |
| Interagiert mit dem Concierge | Concierge-Name, Seiten-URL, Erstellt am, Dauer, Datum der Aktivität |
| Terminierte Besprechung im Concierge | Name des Concierge, Name des Vertriebsmitarbeiters, Meeting-Status, Geplant für, Meeting-Dauer, Routing-Typ, Seiten-URL, Datum der Aktivität |
| Interagiert mit Live-Chat im Concierge | Name des Concierge, Name des Vertriebsmitarbeiters, Gesprächsstatus, Gesprächswert, Startzeit, akzeptierte Zeit, Endzeit, Geschlossen von, Dauer, Gesprächsthema, Seiten-URL, Sprache, Datum der Aktivität |

## Nächster Schritt {#next}

Überprüfen Sie die Leistung von Meetings und Chats in [Überwachen von Meetings und Live-Chats](monitor.md).

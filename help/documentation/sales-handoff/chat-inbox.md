---
title: Chat-Posteingang
description: Erfahren Sie, wie ein Vertriebsmitarbeiter einen Brand Concierge-Live-Chat im Adobe Marketo Qualifier-Chat-Posteingang empfängt, verarbeitet, bewertet und beendet.
role: User
level: Beginner
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%
---
# Chat-Posteingang {#chat-inbox}

Wenn ein Besucher Sie bittet, mit jemandem zu sprechen, kommt der Chat in [!DNL Adobe Marketo Qualifier] im **[!UICONTROL Chat-]** an. Diese Seite ist die Ansicht eines Vertreters von einem Live-Chat: was man sieht, wenn es ankommt, welchen Kontext man erhält und was man tun muss, bevor man es schließen kann.

Um den Chat-Posteingang zu öffnen, wählen Sie im linken Bereich unter **[!UICONTROL Aktivitäten]** die Option **[!UICONTROL Chat-Posteingang]** aus.

## Chat empfangen {#receive}

Ihr Status wird in der oberen rechten Ecke des Posteingangs angezeigt. **[!UICONTROL Verfügbar]** bedeutet, dass Sie jetzt Chats empfangen können. Ihre Live-Chat-Verfügbarkeitszeiten entscheiden, ob Sie überhaupt berechtigt sind. Siehe [Festlegen der Verfügbarkeit von Live-Chat](representative-setup.md#chat-availability).

Wie Sie von einem Chat erreicht werden, hängt vom Routing-Typ ab, der in der **[!UICONTROL Live-Chat]**-Integration festgelegt ist:

* Bei Round Robin wird jeder berechtigte Vertreter zur gleichen Zeit benachrichtigt und der erste, der das Gespräch akzeptiert.
* Bei einem direkten Agenten kommt der Chat immer zum benannten Vertreter.
* Bei benutzerdefiniertem Routing wird der Chat an die Vertreter geleitet, die der Regel mit der höchsten Priorität zugewiesen sind, mit der der Besucher übereinstimmte.

Die Unterhaltungen werden auf zwei Registerkarten organisiert:

* **[!UICONTROL Aktiv]** - Gespräche werden derzeit ausgeführt.
* **[!UICONTROL Alle]** - jede Konversation, auch die, die beendet wurde.

## Nehmen Sie die Unterhaltung auf {#pick-up}

Man fängt nie an zu kalten. Bevor Sie etwas eingeben, erhalten Sie im Posteingang alles, was der Besucher dem Concierge bereits gesagt hat.

![Chat-Posteingang, der die Zusammenfassung der Besucherunterhaltung mit einer Zusammenfassung und behandelten Themen sowie das Bedienfeld „Profildetails“ anzeigt](../assets/sales-handoff-inbox-1.png){width="800" zoomable="yes"}

| Was Sie sehen | Was es Ihnen gibt |
| --- | --- |
| **[!UICONTROL Zusammenfassung der Besuchergespräche]** | Eine **[!UICONTROL Zusammenfassung]** des Gesprächs des Besuchers mit dem Concierge und die **[!UICONTROL Themen besprochen]** |
| Gesprächstranskript | Der umfassende Austausch mit dem Concierge, über dem Punkt, wo Live-Chat gestartet wurde |
| **[!UICONTROL Formulardetails]** | Was der Besucher in das Formular vor dem Chat eingegeben hat, bevor Sie beigetreten sind, z. B. E-Mail, Produktinteresse und Firma |

Das Transkript markiert die Übergabe mit zwei Systemzeilen, `Live chat session has been initiated` und `Agent <name> has joined the chat`, sodass Sie immer erkennen können, welcher Teil des Gesprächs der Concierge war und welcher Teil Ihrer ist.

Geben Sie in das Nachrichtenfeld ein und wählen Sie **[!UICONTROL Senden]** aus, um zu antworten.

![Live-Chat zwischen dem Kundenbetreuer und dem Besucher läuft](../assets/sales-handoff-inbox-2.png){width="800" zoomable="yes"}

## Bewerten des Gesprächs {#conversation-score}

Bevor Sie einen Chat beenden, bewerten Sie, wie qualifiziert der Besucher ist. Die Punktzahl wird von Ihnen festgelegt, dem Vertreter, der tatsächlich mit dem Besucher gesprochen hat, was ihn nachgelagert vertrauenswürdig macht.

Wählen Sie **[!UICONTROL Bedienfeld]** Profildetails“ unter **[!UICONTROL Konversationswert]** eine Bewertung aus. Der Bindestrich bedeutet keine Bewertung und die Flammensymbole bewerten die Konversation von der niedrigsten zur höchsten Qualifikation.

![Tooltip für Konversationsbewertung, der erläutert, dass die Bewertungen im Lead-Datensatz als 0, 1, 2 und 3 gespeichert werden](../assets/sales-handoff-inbox-4.png){width="600" zoomable="yes"}

| Auswahl | Gespeicherter Wert | Bedeutung |
| --- | --- | --- |
| Bindestrich | 0 | Am wenigsten qualifiziert |
| Eine Flamme | 1 | Einigermaßen qualifiziert |
| Zwei Flammen | 2 | qualifiziert |
| Drei Flammen | 3 | Am besten qualifiziert |

>[!IMPORTANT]
>
>Die Bewertung ist obligatorisch. Wenn Sie versuchen, einen Chat zu schließen, ohne ihn zu bewerten, wird die `Please score the conversation before you close the chat` angezeigt und der Chat bleibt offen. Nachdem Sie die Punktzahl erreicht haben, wird eine Bestätigung angezeigt und Sie können den Chat schließen.

![Bestätigung, dass der Konversationswert gespeichert wurde](../assets/sales-handoff-inbox-3.png){width="800" zoomable="yes"}

Die Punktzahl wird in die Aktivität **[!UICONTROL Interagieren mit Live-Chat im Concierge]** in [!DNL Marketo Engage] geschrieben, wo sie als Einschränkung für Filter und Trigger verfügbar ist. Verwenden Sie ihn, um Retargeting, Lead-Bewertung, Personalisierung und CRM-Übergabe zu fördern. Siehe [Brand Concierge-Daten in Marketo Engage](marketo-activities.md).

## Beenden des Chats {#end-chat}

Wählen Sie **[!UICONTROL Chat beenden]** um die Unterhaltung zu schließen. Der Besucher kann es auch von seiner Seite aus beenden und wird aufgefordert, es zunächst zu bestätigen.

Wenn ein Chat geschlossen wird, wird sein Gesprächsstatus als einer von zwei Werten aufgezeichnet:

* **Beendet** - Die Unterhaltung wurde absichtlich von Ihnen oder dem Besucher geschlossen.
* **Abgebrochen** - Der Besucher verließ die Website und die Unterhaltung wurde durch die Inaktivität beendet.

>[!NOTE]
>
>Live-Chat-Gespräche werden 30 Tage lang aufbewahrt.

## Nächster Schritt {#next}

Sehen Sie, was all dies zurück in Ihre Marketing-Datenbank schreibt, in den Daten von [Brand Concierge in Marketo Engage](marketo-activities.md).

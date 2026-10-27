---
title: Routing von Unterhaltungen an Vertreter
description: Wählen Sie aus, wie Brand Concierge mithilfe von Round Robin, einem Direktagenten oder benutzerdefinierten Routing-Regeln entscheidet, welcher Vertriebsmitarbeiter einen Live-Chat oder eine Besprechungsbuchung erhält.
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
source-wordcount: '771'
ht-degree: 0%
---
# Routing von Konversationen an Vertreter {#routing}

Routing beantwortet eine Frage: Wenn dieser Besucher nach einer Person fragt *welche* Person bekommt er?

Sie wählen einen Routing-Typ separat für die Integration **[!UICONTROL Meeting-Buchung]** und die **[!UICONTROL Live-Chat]**-Integration, sodass ein Concierge Meetings gleichmäßig verteilen kann, während er jeden Chat an einen Spezialisten oder eine andere Kombination sendet.

## Routing-Typen {#routing-types}

| Routing-Typ | Wer bekommt das Gespräch? | Erfordert [!DNL Marketo Engage] |
| --- | --- | --- |
| **[!UICONTROL Round Robin]** | Verteilung auf alle zugelassenen Vertreter | Nein |
| **[!UICONTROL Direktagent]** | Einen von Ihnen benannten Vertreter | Nein |
| **[!UICONTROL Benutzerdefiniertes Routing]** | Die Vertreter, die der Routing-Regel mit der höchsten Priorität zugewiesen sind, für die der Besucher qualifiziert ist | Ja |

Round Robin ist standardmäßig verfügbar und muss nicht konfiguriert werden. Sie legen den Routing-Typ für die Integration selbst fest. Siehe [Aktivieren von Live-Chat und Besprechungsbuchung](configure-in-composer.md).

### Ringelschwanz {#round-robin}

Round Robin verhält sich bei Meetings anders als bei Chats, da die beiden unterschiedliche Ziele haben.

Für die Besprechungsbuchung verteilt Round Robin die Besprechungen gleichmäßig. Der erste geeignete Vertreter, der einen Kalender angeschlossen hat, wird zuerst angeboten. Sobald ein Meeting bei ihnen gebucht ist, werden sie aus dem Pool genommen und der nächste Vertreter wird angeboten. Mit fünf Vertretern gehen die ersten fünf Sitzungen an fünf verschiedene Personen. Nachdem alle Benutzer eine erhalten haben, wird der Pool zurückgesetzt und der Zyklus beginnt von vorne.

Der Pool wird auch alle 24 Stunden zurückgesetzt, sodass die täglichen Meetings gleichmäßig verteilt sind.

>[!NOTE]
>
>Das 24-Stunden-Round-Robin-Reset wird auf UTC ausgeführt, nicht in der lokalen Zeitzone des Vertreters.

Für Live-Chat gibt es keine sequenzielle Rotation. Jeder berechtigte Vertreter wird gleichzeitig über den eingehenden Chat informiert, und der erste, der den Chat akzeptiert, nimmt das Gespräch.

### Direktagent {#direct-agent}

Jedes Meeting oder Chat von diesem Concierge geht zu dem einzigen Vertreter, den Sie auswählen. Verwenden Sie diese Option für eine Campaign-Landingpage, die einem Kundenbetreuer gehört, oder für eine Region mit einem Spezialisten.

### Benutzerdefiniertes Routing {#custom-routing}

Benutzerdefiniertes Routing bewertet die in [!DNL Adobe Marketo Qualifier] erstellten Regeln anhand der [!DNL Marketo] Lead- und Unternehmensattribute des Besuchers. Verwenden Sie sie, wenn der richtige Vertreter von etwas abhängt, das Sie über den Besucher wissen, z. B.:

* Geografie: Besucher aus einer Reihe von Ländern gehen zum regionalen Team.
* Produktinteresse: Besucher, die sich für ein bestimmtes Produkt interessieren, wenden sich an die Spezialisten dieses Produkts.
* Geschäftseinheit, Unternehmensgröße oder Branche: eine beliebige Kombination aus Lead- und Firmenattributen.

>[!IMPORTANT]
>
>Benutzerdefiniertes Routing ist der Teil der Live-Chat- und Besprechungsbuchung, der [!DNL Adobe Marketo Engage] erfordert, da die Regeln auf [!DNL Marketo] Lead- und Unternehmensattributen basieren. Round Robin und Direct Agent arbeiten ohne es.

## Erstellen einer benutzerdefinierten Routingregel {#create-rule}

1. Wählen Sie [!DNL Adobe Marketo Qualifier] unter **[!UICONTROL Administration]** die Option **[!UICONTROL Routing-Regeln]** aus.

   Die Liste zeigt jede Regel in Ihrer Organisation mit Priorität, Name, Ersteller und Erstellungsdatum.

   ![Seite mit den Routing-Regeln, auf der vorhandene Regeln mit den Spalten „Priorität“, „Name“, „Erstellt von“ und „Erstellt in“ aufgelistet sind](../assets/sales-handoff-routing-1.png){width="800" zoomable="yes"}

1. Wählen **[!UICONTROL Regel erstellen]** und geben Sie der Regel einen Namen.

1. Erstellen Sie die Kriterien.

   Im linken Bedienfeld werden die verfügbaren [!DNL Marketo]-Attribute aus den Objekten **[!UICONTROL Unternehmen]** und **[!UICONTROL Lead]** (Person) aufgelistet. Suchen Sie nach einem Attribut und ziehen Sie es dann auf die Arbeitsfläche, um eine Bedingung hinzuzufügen.

1. Legen Sie für jede Bedingung einen Operator und einen Wert fest.

   Zu den Operatoren gehören **[!UICONTROL Gleich]**, **[!UICONTROL Ist nicht gleich]** und **[!UICONTROL Enthält]** unter anderem. Beispiel: `Country` **[!UICONTROL gleich]** `United States`.

1. Bedingungen zu Gruppen kombinieren.

   Fügen Sie einer Gruppe mehrere Bedingungen hinzu und verbinden Sie sie mit &quot;**[!UICONTROL &quot;]** &quot;**[!UICONTROL &quot;]**. Fügen Sie weitere Gruppen hinzu und schließen Sie sich den Gruppen **[!UICONTROL AND]** oder **[!UICONTROL OR]** an. Durch Verschachteln von Bedingungen innerhalb von Gruppen können Sie auf diese Weise komplexe Kriterien ausdrücken, z. B. *(Land ist USA ODER Kanada) UND (Produktinteresse enthält Analytics)*.

1. Weisen Sie die Regel Vertretern zu.

   Suchen Sie im Abschnitt Arbeitsauftrag nach einem Vertreter mit Namen und wählen Sie ihn aus der Liste aus. Fügen Sie beliebig viele Vertreter hinzu. Jeder von ihnen kann eine Konversation erhalten, die der Regel entspricht.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Wie Priorität angewendet wird {#priority}

Jede Routingregel hat eine Priorität. Priorität ist nur von Bedeutung, wenn sich ein Besucher für mehr als eine Regel qualifiziert.

In diesem Fall wird nur die Regel mit der höchsten Priorität angewendet und die Konversation wird an die dieser Regel zugewiesenen Vertreter weitergeleitet. Regeln, für die sich der Besucher ebenfalls qualifiziert, die jedoch niedriger eingestuft werden, werden ignoriert.

>[!NOTE]
>
>Eine niedrigere Zahl bedeutet eine höhere Priorität. Eine Regel mit Priorität 1 gewinnt gegen eine Regel mit Priorität 2. Die Person, die eine Regel erstellt, legt ihre Priorität fest.

Innerhalb der Gewinnerregel sind die ihr zugewiesenen Vertreter der geeignete Pool, und das Round-Robin-Verhalten für Meetings und das Notify-everyone-Verhalten für Chats, die beide oben beschrieben wurden, gelten für diesen Pool.

## Nächster Schritt {#next}

Nachdem Repräsentanten eingerichtet und die Routing-Entscheidung getroffen wurde, fügen Sie die Funktionen einem Concierge hinzu. Siehe [Aktivieren von Live-Chat und Besprechungsbuchung](configure-in-composer.md).

---
title: Live-Chat und Besprechungsbuchung - Übersicht
description: Erfahren Sie, wie Brand Concierge eine Besucherin oder einen Besucher an einen Menschen übergibt, entweder als Live-Chat mit einem verfügbaren Mitarbeiter oder als gebuchtes Meeting im Kalender eines Vertreters.
role: User, Admin
level: Beginner
TQID: https://experienceleague.adobe.com/vfX6M2-ts7d2-AxKGjaP1Ygkk3FGSGRl4CHslcKYSXU
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
source-wordcount: '768'
ht-degree: 1%
---
# Live-Chat und Besprechungsbuchung - Übersicht {#overview}

Der Concierge beantwortet die meisten Fragen. Einige Unterhaltungen benötigen eine Person: eine Preisaushandlung, einen Fragebogen zur Beschaffung, eine Demoanfrage. Live-Chat und Meeting-Buchung sind die beiden Möglichkeiten, mit denen Brand Concierge eine Unterhaltung an einen Menschen übergibt, ohne den Kontext zu verlieren, den der Besucher bereits geboten hat.

* Live-Chat verbindet den Besucher sofort mit einem verfügbaren Vertreter im selben Chat-Fenster.
* Die Meeting-Buchung bietet dem Besucher echte offene Slots aus dem Kalender eines Vertreters und bucht das Meeting.

Beide werden von derselben Qualifikation (Übergabe **[!UICONTROL Verkauf) angeboten]** und beide Routen über [!DNL Adobe Marketo Qualifier] (früher [!DNL Sales Qualifier]), wo Ihre Vertreter ihre Kalender verbinden, ihre Verfügbarkeit festlegen und Chats führen.

## Funktionsweise von Handoff {#how-it-works}

Vier Teile müssen sich aneinanderreihen, bevor ein Besucher eine Person erreichen kann.

| Stück | Funktion | Wo Sie es eingerichtet haben |
| --- | --- | --- |
| Repräsentatives Profil | Verbindet einen Kalender und erklärt, wann der Vertreter für Besprechungen und Chats zur Verfügung steht | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Profileinstellungen]** |
| Routing | Entscheidet *welcher* diesen Besucher erhält | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Routing-Regeln]** und der Routing-Typ bei jeder Integration |
| Integrationen | **[!UICONTROL Meeting-]** und **[!UICONTROL Live-Chat]** geben dem Concierge die Möglichkeit, die Verfügbarkeit zu überprüfen, einen Chat zu starten und einen Slot zu buchen | Composer > **[!UICONTROL Integrationen durchsuchen]** |
| Skill | **[!UICONTROL Übergabe an den Verkauf]** entscheidet *wann* je nach Absicht des Besuchers eine Übergabe anzubieten | Komponist > **[!UICONTROL Fähigkeiten durchsuchen]** |

Zur Laufzeit gibt der Besucher etwas aus, das einer der „Verwenden **[!UICONTROL -Bedingungen der Kenntnis]**. Die Qualifikation löst aus und ruft alle Integrationen auf, die damit verbunden sind. Das Routing löst dann einen Vertreter auf, und dem Besucher wird ein Chat, ein Meeting oder beides angeboten.

>[!NOTE]
>
>Fähigkeiten und Integrationen sind die Grundbausteine eines Concierge. Das zugrunde liegende Modell finden Sie unter [Skills and Integrations Framework](../skills-and-integrations.md).

## Das Besuchererlebnis {#visitor-experience}

Wenn die Fähigkeiten ausbrechen, erklärt der Concierge die Optionen und stellt sie als Schaltflächen im Gespräch dar.

![Concierge-Antwort mit Übergabe, jetzt mit einem Spezialisten chatten und unten Schaltflächen für Besprechungen planen](../assets/sales-handoff-visitor-1.png){width="800" zoomable="yes"}

### Live-Chat {#visitor-live-chat}

Wenn der Besucher chatten möchte, zeigt der Concierge einen Verbindungsstatus an, während Routing einen verfügbaren Vertreter findet.

![Concierge zeigt eine Verbindung zu einem Spezialistenstatus an, nachdem der Besucher jetzt „Mit einem Spezialisten chatten“ auswählt](../assets/sales-handoff-visitor-2.png){width="800" zoomable="yes"}

Bevor der Vertreter hinzukommt, füllt der Besucher ein kurzes Formular aus, bevor er den Chat beginnt. Diese Antworten werden zusammen mit dem Gespräch gesendet und dem Kundenbetreuer als **[!UICONTROL Formulardetails]** im Chat-Posteingang angezeigt, sodass der Besucher nichts wiederholen muss.

Der Besucher kann den Chat jederzeit beenden und wird gebeten, dies zu bestätigen.

![Bestätigungsdialog zum Beenden des Chats mit der Bitte an den Besucher, das Beenden des Chats mit dem Spezialisten zu bestätigen](../assets/sales-handoff-visitor-4.png){width="800" zoomable="yes"}

### Meeting-Buchung {#visitor-meeting-booking}

Wenn der Besucher ein Meeting bucht, zeigt der Concierge einen Kalender mit den Slots an, die tatsächlich im Kalender des Repräsentanten des Routers in der eigenen Zeitzone des Besuchers offen sind.

![Buchen Sie eine Besprechungskarte im Gespräch, die einen Monatskalender und eine Liste der verfügbaren Zeitfenster anzeigt](../assets/sales-handoff-visitor-3.png){width="800" zoomable="yes"}

Nachdem der Besucher einen Slot bestätigt hat, erhält der Besucher die Bestätigungs-E-Mail des Vertreters, die optional einen [!DNL Microsoft Teams] Link enthält. Der Gesprächskontext geht mit der Einladung an den Vertreter.

## Was Sie vor dem Start benötigen {#prerequisites}

* Zugriff auf [!DNL Adobe Marketo Qualifier], wobei Ihre Vertreter als Benutzer im [!DNL Adobe Admin Console] hinzugefügt werden.
* Mindestens ein Vertreter, der einen Kalender verbunden hat. Die **[!UICONTROL Meeting-Buchung]**-Integration kann erst aktiviert werden, nachdem sie aktiviert wurde.
* Mindestens ein Mitarbeiter, der die Verfügbarkeit von Live-Chat festgelegt hat. Die **[!UICONTROL Live-Chat]**-Integration kann erst aktiviert werden, nachdem sie aktiviert wurde.
* Ein Concierge in Composer, dem Sie Integrationen und Fähigkeiten hinzufügen können.

>[!NOTE]
>
>Live-Chat und Meeting-Buchung erfordern keine [!DNL Adobe Marketo Engage]. Ohne diese Daten bleiben Repräsentanten-, Besprechungs- und Chat-Daten in [!DNL Adobe Marketo Qualifier]. Zwei Dinge erfordern [!DNL Marketo Engage]: benutzerdefinierte Routing-Regeln, die auf [!DNL Marketo] Lead- und Unternehmensattributen basieren, und die Concierge-Aktivitätstypen, die in den Datensatz für [!DNL Marketo] Personen zurückgeschrieben werden.

## Live-Chat und Meeting-Buchung einrichten {#setup-path}

Arbeiten Sie diese in der richtigen Reihenfolge durch.

1. [Richten Sie in Adobe Marketo Qualifier Repräsentanten ein](representative-setup.md) - Verbinden Sie einen Kalender, definieren Sie die Bestätigungs-E-Mail und legen Sie einen Kalender und die Verfügbarkeit von Live-Chats fest.
1. [Konversationen an Vertreter weiterleiten](routing-rules.md) - Wählen Sie Round Robin, einen direkten Agenten oder benutzerdefinierte Regeln, die auf [!DNL Marketo] Attributen basieren.
1. [Live-Chat und Meeting-Buchung aktivieren](configure-in-composer.md) - Verbinden Sie die beiden Integrationen und aktivieren Sie die **[!UICONTROL Übergabe an den Vertrieb]**.
1. [Chat-Posteingang](chat-inbox.md) - Was Vertreter tun, sobald ein Chat eintrifft, einschließlich der Bewertung der Konversation.
1. [Brand Concierge-Daten in Marketo Engage](marketo-activities.md) - die Lead-Felder und Aktivitätstypen, die zurück in [!DNL Marketo] geschrieben wurden, und wie sie in intelligenten Kampagnen verwendet werden.
1. [Überwachen von Meetings und Live](monitor.md)Chats - die Buchungsliste und das Leistungs-Dashboard.

## Datenbeibehaltung {#retention}

Live-Chat-Gespräche werden 30 Tage lang aufbewahrt.

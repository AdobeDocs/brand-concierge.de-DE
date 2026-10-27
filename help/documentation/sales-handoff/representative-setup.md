---
title: Einrichten von Vertretungen in Adobe Marketo Qualifier
description: Verbinden Sie den Outlook- oder Google-Kalender eines Vertreters, legen Sie die E-Mail zur Besprechungsbestätigung fest, definieren Sie die Verfügbarkeit von Kalendern und Live-Chats und überprüfen Sie, wer eingerichtet ist.
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
source-git-commit: 4751ce408fb2aa6d1affae4dd7a5d81ca43ffc8a
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 1%
---
# Einrichten von Repräsentanten in Adobe Marketo Qualifier {#representative-setup}

Bevor ein Concierge ein Meeting oder einen Live-Chat anbieten kann, muss mindestens ein Vertreter in [!DNL Adobe Marketo Qualifier] eingerichtet werden. Jeder Vertreter tut dies einmal in seinem eigenen Profil.

Die Reihenfolge lautet: Ein Administrator fügt die Benutzer hinzu, dann verbindet jeder Vertreter einen Kalender, schreibt seine Bestätigungs-E-Mail und erklärt, wann sie für Meetings und für den Chat verfügbar sind.

## Hinzufügen von Benutzern zur Organisation {#add-users}

Ein Administrator fügt jeden Vertriebsmitarbeiter als Benutzer der [!DNL Adobe Admin Console] hinzu und gewährt ihm Zugriff auf [!DNL Adobe Marketo Qualifier]. Eine allgemeine Vorgehensweise finden Sie unter [Benutzer zur Organisation hinzufügen](../user-and-access-management/add-a-user-to-the-org.md) und [Benutzer zur Rolle hinzufügen](../user-and-access-management/add-a-user-to-the-role.md).

Die verbleibenden Schritte werden von den Vertretern selbst vollzogen.

## Kalender verbinden {#connect}

Die Kalenderverbindung macht die echte Verfügbarkeit für einen Concierge sichtbar. Ohne diesen ist der Vertreter nicht für die Besprechungsbuchung geeignet.

1. Melden Sie sich bei [Adobe Experience Cloud](https://experience.adobe.com/){target="_blank"} an und wählen Sie **[!UICONTROL Adobe Marketo Qualifier]** aus.

   ![Startseite von Adobe Experience Cloud mit der Adobe Marketo Qualifier-Karte](../assets/meetings-connect-1.png){width="800" zoomable="yes"}

1. Wählen Sie im linken Bedienfeld unter **[!UICONTROL Konfiguration]** die Option **[!UICONTROL Profileinstellungen]** und öffnen Sie dann die Registerkarte **[!UICONTROL Kalenderkonfiguration]**.

1. Wählen Sie den Kalender, den Sie verbinden möchten, entweder [!DNL Microsoft Outlook] oder [!DNL Google Calendar].

   ![Registerkarte Kalenderkonfiguration mit den Verbindungsoptionen für den Outlook- und Google-Kalender](../assets/meetings-connect-2.png){width="600" zoomable="yes"}

1. Melden Sie sich mit einem vorhandenen Konto an oder fügen Sie ein neues hinzu und gewähren Sie die angeforderten Berechtigungen.

   ![Microsoft-Kontoauswahl wird während der Kalenderverbindung angezeigt](../assets/meetings-connect-3.png){width="600" zoomable="yes"}

1. Überprüfen Sie die Bestätigungs-E-Mail, die an einen Besucher gesendet wird, wenn er ein Meeting mit Ihnen bucht.

   Es werden eine standardmäßige Betreffzeile und ein standardmäßiger Hauptteil für Sie festgelegt. Bearbeiten Sie eine der beiden Optionen und wählen Sie aus, ob ein [!DNL Microsoft Teams] Meeting-Link in die Einladung aufgenommen werden soll.

   ![E-Mail-Einstellungen zur Besprechungsbestätigung mit bearbeitbarer Betreffzeile und bearbeitbarem Textkörper](../assets/meetings-connect-4.png){width="600" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Speichern]** aus.

## Festlegen der Kalenderverfügbarkeit {#calendar-availability}

Das Verbinden eines Kalenders gibt [!DNL Adobe Marketo Qualifier] an, wenn Sie *beschäftigt*. Die Kalenderverfügbarkeit gibt an, wann *bereit sind* ein Meeting durchzuführen. Beide werden angewendet.

1. Öffnen **[!UICONTROL in]** Profileinstellungen“ die Registerkarte **[!UICONTROL Kalenderverfügbarkeit]**.

   ![Registerkarte Kalenderverfügbarkeit , bevor eine Verfügbarkeit festgelegt wurde](../assets/meetings-availability-1.png){width="600" zoomable="yes"}

1. Legen Sie Ihre Besprechungsregeln fest.

   | Einstellung | Was sie steuert |
   | --- | --- |
   | Besprechungsdauer | Wie lange ein gebuchtes Meeting läuft und damit die Länge jedes angebotenen Slots |
   | Pufferzeit | Die Lücke zwischen dem Ende einer Besprechung und dem Beginn der nächsten |
   | Mindestkündigungsfrist | Wie weit im Voraus muss ein Besucher buchen. Legen Sie beispielsweise vier Stunden fest, damit Besucher keinen Slot buchen können, der in zehn Minuten beginnt |
   | Zeitzone | Die Zeitzone, in der Ihre Verfügbarkeitsstunden ausgedrückt werden. Besucher sehen immer Slots, die in ihre eigene Zeitzone konvertiert wurden |

1. Legen Sie die verfügbaren Stunden für jeden Wochentag fest.

   Ein Tag kann ein durchgehender Block sein, z. B. von 8:00 bis 17:00 Uhr, oder mehrere Blöcke, z. B. von 8:00 bis 12:00 Uhr und von 14:00 bis 17:00 Uhr. Lassen Sie einen Tag leer, um an diesem Tag keine Besprechungen durchzuführen.

   >[!NOTE]
   >
   >Um einem Tag einen weiteren Zeitblock hinzuzufügen, wählen Sie das Pluszeichen (Pluszeichen![&#x200B; aus](../assets/icon-plus-sign.png).

   ![Registerkarte Kalenderverfügbarkeit mit konfigurierten Wochentagsstunden und einem aufgeteilten Zeitbereich](../assets/meetings-availability-2.png){width="600" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Speichern]** aus.

### Wie ein Slot buchbar wird {#slot-logic}

Ein Zeitfenster wird einem Besucher nur angeboten, wenn er alle drei Prüfungen übersteht:

1. Er liegt innerhalb der verfügbaren Stunden, die Sie hier festlegen.
1. Es ist noch nicht von einem Ereignis in Ihrem verbundenen Kalender belegt. Bei einem bestehenden 9:00-Uhr-Meeting wird der 9:00-Uhr-Slot entfernt.
1. Es erfüllt Ihre minimale Ankündigungszeit und Pufferzeit.

## Live-Chat-Verfügbarkeit festlegen {#chat-availability}

Die Live-Chat-Verfügbarkeit ist getrennt von der Kalenderverfügbarkeit. Ein Mitarbeiter kann für den Chat zur Verfügung stehen, aber keine Besprechungen oder umgekehrt.

1. Öffnen Sie **[!UICONTROL Profileinstellungen]** die Registerkarte **[!UICONTROL Live-Chat-Verfügbarkeit]** .

1. Legen Sie Ihre Zeitzone fest und legen Sie dann die Tage und Stunden fest, an denen Sie einen Live-Chat erhalten möchten. Wochenenden können eingeschlossen werden.

   ![Registerkarte „Live-Chat-Verfügbarkeit“ mit konfigurierten Tagen und Stunden](../assets/meetings-availability-3.png){width="600" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Speichern]** aus.

>[!NOTE]
>
>Verfügbarkeitsstunden machen Sie *berechtigt* für Chats. Ihr Live-Status im Chat-Posteingang entscheidet, ob Sie sie jetzt erhalten. Siehe [Chat-](chat-inbox.md).

## Überprüfen, wer eingerichtet ist {#manage-members}

**Nur Administratoren.** Wählen Sie **[!UICONTROL Administration]** die Option **[!UICONTROL Mitglieder verwalten]**, um den Status jedes Vertreters an einem Ort anzuzeigen: wer hat einen Kalender verbunden, wer hat die Verfügbarkeit von Live-Chat festgelegt und wer hat einen Kalender getrennt.

Verwenden Sie diese Option, bevor Sie die Integrationen in Composer aktivieren. Ein Vertreter, der hier ohne verbundenen Kalender angezeigt wird, ist nicht für die Besprechungsbuchung geeignet, und ein Vertreter ohne Verfügbarkeit von Live-Chat ist nicht für den Live-Chat geeignet.

![Mitglieder verwalten Seitenlistendaten und deren Kalender- und Live-Chat-Einrichtungsstatus](../assets/manage-members-1.png){width="800" zoomable="yes"}

## Nächster Schritt {#next}

Legen Sie bei mindestens einem eingerichteten Repräsentanten fest, wie Besucher mit Repräsentanten abgeglichen werden. Siehe [Routen von Konversationen an Vertreter](routing-rules.md).

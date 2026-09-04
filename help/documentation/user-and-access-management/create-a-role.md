---
title: Erstellen einer Rolle mit Brand Concierge-Berechtigung
description: Erfahren Sie, wie Sie eine Rolle erstellen und ihr die für den Zugriff auf Brand Concierge erforderlichen Berechtigungen erteilen.
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 1%

---


# Erstellen einer Rolle mit Brand Concierge-Berechtigung

Erstellen Sie eine Rolle in Adobe Experience Platform-Berechtigungen, um Benutzenden Zugriff auf Brand Concierge zu gewähren.

>[!PREREQUISITES]
>
>- Sie müssen über die erforderlichen Administratorberechtigungen verfügen, um Rollen und Berechtigungen zu verwalten.
>- Der Benutzer muss zunächst der Adobe Experience Platform-Organisation hinzugefügt werden. Weitere Informationen finden Sie unter [Hinzufügen eines Benutzers zur Organisation](./add-a-user-to-the-org.md).

## Erstellen der Rolle

1. Melden Sie sich bei `experienceplatform.adobe.com` an.

1. Scrollen Sie in der linken Navigation zu und wählen Sie **Berechtigungen** aus.
1. Gehen Sie zu **Rollen**, um vorhandene Rollen anzuzeigen, und wählen Sie **Neue Rolle erstellen** aus.
1. Geben Sie einen Namen für die Rolle ein, z. B. `Brand Concierge Access Users`, fügen Sie eine Beschreibung hinzu und bestätigen Sie die Erstellung.
1. Öffnen Sie die neue Rolle und weisen Sie Berechtigungen zu:

   1. Durchsuchen Sie die Berechtigungsliste nach **Brand Concierge**.
   1. Wählen Sie **Brand Concierge verwalten** aus.

   Derzeit ist **Brand Concierge verwalten** die einzige verfügbare Brand Concierge-Berechtigung. Granulare Berechtigungsebenen sind noch nicht verfügbar.

1. Wählen Sie die Sandbox oder Sandboxes aus, auf die die Rolle zugreifen kann.

   Eine Organisation kann mehrere Sandboxes enthalten, bei denen es sich um isolierte Arbeitsbereiche handelt. Wählen Sie nur die für diese Rolle geeigneten Sandboxes aus.

1. Wählen Sie **Speichern** aus.

## Nächste Schritte

Nachdem die Rolle erstellt wurde, fügen Sie ihr Benutzer hinzu. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern zur Brand Concierge-Rolle](./add-a-user-to-the-role.md).

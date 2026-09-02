---
title: Hinzufügen eines Benutzers zur Organisation
description: Erfahren Sie, wie Sie einen Benutzer zur Adobe Experience Platform-Organisation hinzufügen, bevor Sie Brand Concierge-Zugriff gewähren.
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---


# Hinzufügen eines Benutzers zur Organisation

Bevor ein Benutzer auf Brand Concierge zugreifen kann, fügen Sie den Benutzer der Adobe Experience Platform-Organisation in der Adobe Admin Console hinzu.

>[!PREREQUISITES]
>
>- Sie müssen Administratorzugriff auf das Unternehmen haben.
>- Die Benutzenden müssen einzeln oder über einen Massen-Benutzer-Upload hinzugefügt werden können.

## Benutzer hinzufügen

1. Zur **Admin Console**.
1. Wählen **Verwalten** oder gehen Sie zu **Benutzer**.
1. Fügen Sie Benutzer einzeln hinzu oder fügen Sie mehrere Benutzer über einen Massen-Upload hinzu.
1. Wenn der Benutzer noch nicht in der Organisation vorhanden ist, wählen Sie die Option aus, um den Benutzer als neuen Benutzer hinzuzufügen, wenn Sie dazu aufgefordert werden.
1. Wählen Sie das Produktprofil aus:

   - **Adobe Experience Platform**
   - Das Standardbenutzerprofil

1. Wählen Sie **Speichern** aus.

Der Benutzer erhält eine E-Mail-Einladung, die den Zugriff auf die Organisation bestätigt.

>[!IMPORTANT]
>
>Die Organisationseinladung gewährt Benutzenden Zugriff auf die Organisation, sie gewährt jedoch keinen Zugriff auf Brand Concierge. Um Zugriff auf Brand Concierge zu gewähren, erstellen Sie eine Rolle mit der Berechtigung Brand Concierge und weisen Sie sie zu, wie in [Erstellen einer Rolle mit der Berechtigung Brand Concierge](./create-a-role.md) beschrieben.

## Nächste Schritte

Nachdem der Benutzer zur Organisation hinzugefügt wurde, erstellen Sie eine Rolle mit der Berechtigung **Brand Concierge verwalten** und weisen Sie den Benutzer dieser Rolle zu.

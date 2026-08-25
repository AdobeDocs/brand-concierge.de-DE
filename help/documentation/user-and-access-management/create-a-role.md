---
title: Erstellen einer Rolle mit Brand Concierge-Berechtigung
description: Erfahren Sie, wie Sie eine Rolle erstellen und ihr die für den Zugriff auf Brand Concierge erforderlichen Berechtigungen erteilen.
source-git-commit: 591bd1600e586a0a4ce484dbff3f9fb97e24d43d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 1%

---


# Erstellen einer Rolle mit Brand Concierge-Berechtigung

Erstellen Sie eine Rolle in Adobe Experience Platform-Berechtigungen, um Benutzenden Zugriff auf Brand Concierge zu gewähren.

## Voraussetzungen

* Sie müssen über die erforderlichen Administratorberechtigungen verfügen, um Rollen und Berechtigungen zu verwalten.
* Der Benutzer muss zunächst der Adobe Experience Platform-Organisation hinzugefügt werden. Weitere Informationen finden Sie unter „Hinzufügen eines Benutzers zur Organisation“ (LINK).

## Erstellen der Rolle

1. Melden Sie sich bei `experienceplatform.adobe.com` an.

   >[!NOTE]
   >
   >Bestätigen Sie die Produktions-URL mit dem Engineering, bevor Sie dieses Verfahren veröffentlichen. Die Quellaufzeichnung verwendete eine informelle oder möglicherweise falsch transkribierte URL.

2. Scrollen Sie in der linken Navigation zu und wählen Sie **Berechtigungen** aus.
3. Wählen Sie **Rollen** aus, um vorhandene Rollen anzuzeigen, und wählen Sie dann **Neue Rolle erstellen** aus.
4. Geben Sie einen Namen für die Rolle ein, z. B. `Brand Concierge Access Users`, fügen Sie eine Beschreibung hinzu und bestätigen Sie die Erstellung.
5. Öffnen Sie die neue Rolle und weisen Sie Berechtigungen zu:

   1. Durchsuchen Sie die Berechtigungsliste nach **Brand Concierge**.
   2. Wählen Sie **Brand Concierge verwalten** aus.

   Derzeit ist **Brand Concierge verwalten** die einzige verfügbare Brand Concierge-Berechtigung. Granulare Berechtigungsebenen sind derzeit nicht verfügbar.

6. Wählen Sie die Sandbox oder Sandboxes aus, auf die die Rolle zugreifen kann.

   Eine Organisation kann mehrere Sandboxes enthalten, bei denen es sich um isolierte Arbeitsbereiche handelt. Wählen Sie nur die für diese Rolle geeigneten Sandboxes aus.

7. Wählen Sie **Speichern** aus.

## Nächste Schritte

Nachdem die Rolle erstellt wurde, fügen Sie ihr Benutzer hinzu. Weitere Informationen finden Sie unter „Hinzufügen von Benutzern zur Rolle“ (LINK).

## Verwandte Überlegungen

* Der Prozess zum Erstellen und Verwalten von Sandboxes würde den Rahmen dieses Verfahrens sprengen.
* Überprüfen Sie, ob zusätzliche granulare Brand Concierge-Berechtigungen geplant sind, bevor Sie ein langfristiges Rollenmodell definieren.

---
title: Einen Concierge entsenden
description: Erfahren Sie, wie Sie eine Brand Concierge bereitstellen, indem Sie einen Datenstrom konfigurieren, das Bereitstellungsskript installieren, Oberflächenregeln definieren und die Bereitstellung überprüfen.
hide: true
source-git-commit: da4b30fa292b911987aebec378af420b293ea594
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---


# Einen Concierge entsenden

Die Bereitstellung stellt einen Concierge für echte Website-Besucher zur Verfügung. Der Marketer konfiguriert die Bereitstellungseinstellungen, während das IT- oder Analytics-Team die Datenstrom-ID bereitstellt und das Website-Team das Bereitstellungsskript auf der Website installiert.

Die Bereitstellung ist normalerweise eine kurze, einmalige Konfiguration für jede Site. Planen Sie etwa 15 Minuten auf der Seite des Marketing-Experten ein, plus die Zeit, die das Website-Team für die Installation des Skripts benötigt.

>[!IMPORTANT]
>
>frühzeitige Einbeziehung des IT- oder Analytics-Teams und des Website-Teams. Ihre Beteiligung ist erforderlich, um die Datenstrom-ID bereitzustellen und das Skript zu installieren, sodass die Bereitstellung nicht als letzter Schritt der Implementierung behandelt werden sollte.

## Voraussetzungen

- Koordinieren Sie sich mit dem IT- oder Analytics-Team, um eine Datenstrom-ID zu erhalten.
- Identifizieren Sie das Team, das für die Website oder den Tag-Manager verantwortlich ist. Dieser Artikel bezieht sich auf diese Gruppe als das Website-Team.
- Entscheiden Sie, ob der Concierge als Komponente auf bestehenden Seiten oder als komplette, eigene Seite erscheinen soll.
- Identifizieren Sie die Domains und Seitenpfade, in denen der Concierge erscheinen soll.

## Konfigurieren des Datenstroms

Ein Datenstrom ist das Ziel für Aktivitätsdaten, die durch Besucherinteraktionen mit dem Concierge generiert werden. Beispiele für diese Interaktionen sind Klicks, Formularübermittlungen, gebuchte Meetings und Live-Chats. Der Datenstrom ermöglicht es, diese Aktivität später in Analytics anzuzeigen.

Sie müssen im Rahmen dieses Verfahrens keinen Datenstrom erstellen. Sie benötigen nur ihre ID.

### Abrufen der Datenstrom-ID

Fragen Sie das IT- oder Analytics-Team nach der Datenstrom-ID. Die ID finden Sie in Adobe Experience Platform unter **Datenerfassung** > **Datenströme**.

### Hinzufügen der Datenstromkonfiguration

1. Halten Sie die Datenstrom-ID bereit.
1. Wählen Sie im Abschnitt zur Brand Concierge-Bereitstellung **Konfiguration hinzufügen** aus.
1. Fügen Sie die Datenstrom-ID ein.
1. Speichern Sie die Konfiguration.
1. Nachdem die Konfiguration gespeichert wurde, wählen Sie die entsprechende Installationsoption aus:
   - **Komponenteninstallation:** Verwenden Sie einen Ausschnitt, den das Website-Team an einer bestimmten Position auf der Website platziert.
   - **Vollständige Seiteninstallation:** Verwenden Sie eine vollständige, hostfertige Seite für eine dedizierte Landingpage des Concierge.
1. Stellen Sie dem Website-Team das ausgewählte Skript oder die ausgewählte Seite bereit.
1. Lassen Sie das Website-Team das Skript direkt im Seiten-Code oder über einen Tag-Manager installieren.

>[!NOTE]
>
>Die Installation wird normalerweise vom Website-Team durchgeführt, ähnlich wie beim Hinzufügen eines Analytics- oder Chat-Tool-Tags.

## Konfigurieren der Oberfläche

Nachdem das Skript installiert wurde, steuert die Oberflächenkonfiguration die Seiten, auf denen der Concierge angezeigt wird. Sie können beispielsweise den Concierge so konfigurieren, dass er auf Produktseiten, aber nicht auf einer Karriereseite angezeigt wird.

### Hinzufügen einer Domain und von Seitenregeln

1. Fügen Sie eine Domain hinzu, z. B. `blog.example.com`.
1. Wählen Sie aus, wie die Pfade in der Domain übereinstimmen sollen. Zu den verfügbaren Übereinstimmungsmustern gehören:
   - Jede Seite unter der Domain.
   - Pfade, die mit einem angegebenen Wert beginnen.
   - Pfade, die mit einem angegebenen Wert enden.
   - Eine exakte Pfadübereinstimmung.
1. Kombinieren Sie mehrere Regeln, um eine präzisere Seitenabdeckung zu definieren.
1. Speichern Sie die Oberflächenkonfiguration.

## Überprüfen der Bereitstellung

Nachdem das Website-Team das Skript installiert und die Oberflächenregeln gespeichert hat, überprüfen Sie Folgendes:

- Das Skript befindet sich auf den vorgesehenen Website-Seiten.
- Der Concierge erscheint nur auf Seiten, die von den konfigurierten Regeln abgedeckt werden.
- Der Concierge erscheint nicht auf ausgeschlossenen Seiten.
- Besucherinteraktionen generieren Aktivitätsdaten für den konfigurierten Datenstrom.

>[!TIP]
>
>Testen Sie sowohl eine eingeschlossene als auch eine ausgeschlossene Seite. Dies bestätigt, dass die Oberflächenregeln wie beabsichtigt funktionieren, bevor der Concierge breit verfügbar gemacht wird.

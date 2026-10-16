---
title: Exportieren von Unterhaltungen mit Abfrage-Service und Terminal
description: Erfahren Sie, wie Sie Brand Concierge-Konversationen mithilfe des Abfrage-Services und Terminals von Experience Platform in CSV exportieren, einschließlich Anleitungen zu Anmeldeinformationen und personenbezogenen Daten.
topic: Development
role: Developer
level: Experienced
doc-type: Tutorial
duration: 260
last-substantial-update: 2026-10-15
jira: KT-22874
source-git-commit: 04c844e16a8fb13e54dfcbb29c776896674532b9
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%
---
# Exportieren von Unterhaltungen mit Abfrage-Service und Terminal

Erfahren Sie, wie Sie Adobe Brand Concierge-Konversationen mithilfe von Adobe Experience Platform Query Service und Terminal speichern und exportieren. In diesem Video erfahren Sie, wie Sie Namen von Datensatztabellen finden, den PostgreSQL-Befehlszeilen-Client konfigurieren und Konversationsdaten für einen Datumsbereich in eine CSV-Datei exportieren.

## Für wen ist dieses Video bestimmt?

* Entwickler, die Brand Concierge-Unterhaltungsdaten mithilfe von Befehlszeilen-Tools exportieren müssen

## Videoinhalt

* Suchen nach Unterhaltungsdatensätzen in Experience Platform und Kopieren ihrer Tabellennamen
* Installieren Sie den PostgreSQL-Client mit Homebrew und konfigurieren Sie dessen Befehlszeilenpfad
* Kopieren Sie den PSQL-Verbindungsbefehl von der Registerkarte Anmeldeinformationen des Abfrage-Service.
* Datensatz und Datumsbereich auswählen und Abfrageergebnisse in eine lokale CSV-Datei exportieren
* Überprüfen Sie die exportierten Ergebnisse und aktualisieren Sie bei Bedarf abgelaufene Anmeldedaten.

>[!VIDEO](https://video.tv.adobe.com/v/3504643)

```bash
psql "sslmode=require host=... password=..." --csv -o ~/brand-concierge-conversation-export/oct-1-2026-till-today-responses.csv -c "SELECT * FROM cja_brand_concierge_responses_dataset_b4c15126_bd9b_4d52_8151_26 WHERE timestamp >= TIMESTAMP '2026-10-01 00:00:00' AND timestamp <= NOW() ORDER BY timestamp ASC LIMIT 1000"
```

>[!IMPORTANT]
>
> Der PSQL-Verbindungsbefehl enthält ein Live-Kennwort. Teilen oder fügen Sie sie nicht in Chats, KI-Agenten oder E-Mails ein. Wenn die Authentifizierung nach Ablauf des Kennworts fehlschlägt, kopieren Sie einen neuen Befehl aus der Registerkarte Anmeldeinformationen für den Abfrage-Service.

>[!NOTE]
>
> Exportierte Konversationen können personenbezogene Daten (PII, Personally Identifiable Information) enthalten. Befolgen Sie beim Speichern von CSV-Dateien die Richtlinien Ihres Unternehmens für die Datenverarbeitung.

Die Dokumentation finden Sie in der [Brand Concierge-Hilfe](../documentation/overview.md).

## Verwandte Tutorials

* [Exportieren von Unterhaltungen mit Adobe CX Enterprise Coworker](exporting-conversations-using-adobe-cx-enterprise-coworker.md)

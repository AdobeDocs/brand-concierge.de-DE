---
title: Erstellen und Verwalten von Wissensquellen für Brand Concierge
description: Erfahren Sie, wie Sie AEM Sites-, Website-Links- und Produktkatalog-Wissensquellen für Brand Concierge erstellen, den Verarbeitungsstatus überwachen und crawlen Probleme beheben.
hide: true
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Erstellen und Verwalten von Wissensquellen für Brand Concierge

Eine Wissensquelle ist der Inhalt, den ein Concierge bei der Beantwortung von Besucherfragen verwenden kann. Jeder Concierge benötigt mindestens eine konfigurierte Wissensquelle. Wissensquellen werden unabhängig voneinander erstellt und können über mehrere Concierge hinweg wiederverwendet werden.

Ein Concierge beantwortet Fragen nur anhand der konfigurierten Wissensquellen. Es antwortet nicht aus dem allgemeinen Weltwissen.

>[!NOTE]
>
>Wenn ein Besucher nach Informationen außerhalb der konfigurierten Wissensquellen fragt, ist der Concierge so konzipiert, dass er angibt, dass er die Informationen nicht hat, anstatt eine nicht unterstützte Antwort zu generieren. Verwenden Sie den Bewertungsprozess, um dieses Verhalten zu überprüfen.

## Wissensquelle auswählen

Brand Concierge unterstützt die folgenden Wissens-Quelltypen:

| Wissensquelle | Verwenden Sie sie, wenn | Hauptfunktion |
| --- | --- | --- |
| AEM Sites (Content AI-Index) | Der Kunde verwendet AEM Sites as a Cloud Service mit aktivierter Content-KI. | Verwendet einen vorhandenen Content AI-Index und stellt aktualisierten AEM Sites-Inhalt ohne separaten crawlen- oder Aktualisierungsschritt zur Verfügung. |
| Website-Links | Der Kunde muss eine Website crawlen haben, unabhängig von der Plattform, mit der sie erstellt wurde. | Crawlen eine Sitemap, ausgewählte einzelne URLs oder URLs, die in einer CSV-Datei bereitgestellt werden. |
| Produktkatalog | Der Kunde verfügt über einen relativ kleinen Produkt- oder Servicekatalog und verwendet Adobe Commerce nicht. | Ermöglicht Produkt-Deep-Links und Produktkarten in Concierge-Antworten. |

>[!IMPORTANT]
>
>Kunden, die über Adobe Commerce mit einem großen Katalog verkaufen, sollten stattdessen die Commerce MCP-Integration verwenden. Details zu dieser Integration würden den Rahmen dieses Artikels sprengen.

## Erstellen einer AEM Sites-Wissensquelle

Verwenden Sie eine AEM Sites-Wissensquelle, wenn der Kunde bereits AEM Sites as a Cloud Service mit aktivierter Content-KI verwendet.

1. Wählen **Wissensdatenbank erstellen**.
1. Wählen Sie **AEM Sites** und wählen Sie **Weiter**.
1. Geben Sie einen Namen und eine Beschreibung für die Wissensquelle ein. Verwenden Sie beispielsweise `My main website` als Namen.
1. Wählen Sie einen vorhandenen Content AI-Index aus der Liste aus. Die Liste wird aus der AEM Sites as a Cloud Service-Instanz gefüllt.
1. Wählen Sie **Speichern** aus.

Diese native Integration macht aktualisierte AEM Sites-Inhalte automatisch für Brand Concierge verfügbar. Ein separater crawlen- oder Aktualisierungsschritt ist nicht erforderlich.

## Erstellen einer Wissensquelle für Website-Links

Verwenden Sie eine Website-Links-Wissensquelle für eine durchsuchbare Website. Diese Option funktioniert für Websites, die auf einer beliebigen Plattform erstellt wurden, und ist die empfohlene Option für die meisten Erstbenutzer.

1. Wählen **Wissensdatenbank erstellen**.
1. Wählen Sie **Website-Links** und wählen Sie **Weiter**.
1. Geben Sie einen Namen für die Wissensquelle ein.
1. Fügen Sie die Inhaltsquellen mit einer der folgenden Methoden hinzu:

   - **Sitemap-URL:** Fügen Sie eine URL hinzu, auf der die Sites-Seiten aufgelistet sind. Alle in der Sitemap aufgelisteten Seiten werden crawlen.
   - **Einzelne URLs:** Fügen Sie bestimmte Seiten-URLs einzeln hinzu. Nur die hinzugefügten Seiten werden crawlen.
   - **CSV-Upload** Laden Sie die Beispieldatei herunter, fügen Sie die URLs hinzu und laden Sie die fertige CSV-Datei hoch.

1. (Optional) Planen Sie eine Aktualisierungshäufigkeit, z. B. wöchentlich an einem bestimmten Tag und zu einer bestimmten Uhrzeit, um die Wissensquelle auf dem neuesten Stand zu halten, wenn sich die Website ändert.
1. Wählen Sie **Hinzufügen** oder **Erstellen** aus.

Das System crawlen die angegebenen URLs und scrapiert deren Inhalt, um die Wissensquelle zu erstellen.

>[!TIP]
>
>Eine Sitemap ist normalerweise unter `yourwebsite.com/sitemap.xml` verfügbar. Wenn die Website keine Sitemap bereitstellt, fügen Sie stattdessen einzelne Seiten-URLs hinzu.

## Erstellen einer Wissensquelle für den Produktkatalog

Verwenden Sie eine Produktkatalog-Wissensquelle für Kunden mit einer kleineren Anzahl von Produkten oder Services (ca. weniger als 100), die Adobe Commerce nicht verwenden.

Wenn eine Concierge-Antwort auf ein Produkt verweist, kann der Produktkatalog einen Deep-Link zur Produktseite bereitstellen und eine Produktkarte aktivieren. Eine Produktkarte kann ein Bild, einen Titel, eine Beschreibung und eine oder zwei Schaltflächen enthalten.

1. Wählen **Wissensdatenbank erstellen**.
1. Wählen Sie **Produktkatalog** und wählen Sie **Weiter**.
1. Geben Sie einen Namen für die Wissensquelle ein. Verwenden Sie beispielsweise `My product catalog - US region` als Namen.
1. Schema auswählen. Das Schema definiert, welche Produktfelder (z. B. Bild, Titel, Beschreibung und Schaltflächen) angezeigt werden und wo die Schaltflächen verknüpft werden.
1. Laden Sie das Beispiel-Arbeitsblatt für das ausgewählte Schema herunter.
1. Fügen Sie die Produktdaten zur Tabelle hinzu und laden Sie sie hoch.
1. Wählen Sie **Speichern** aus.

Verschiedene Schaltflächenkonfigurationen erfordern unterschiedliche Schemata.

## Überwachen des Status der Wissensquelle

Jede Wissensquelle zeigt einen Verarbeitungsstatus an.

| Status | Beschreibung |
| --- | --- |
| In Bearbeitung | Die Wissensquelle wird derzeit verarbeitet. |
| Erfolgreich | Die Wissensquelle ist vollständig verarbeitet und einsatzbereit. |
| Geplant | Die Wissensquelle wird zu einem künftigen geplanten Zeitpunkt verarbeitet. |
| Teilweiser Erfolg | Einige Seiten wurden erfolgreich verarbeitet, andere schlugen fehl. |

Die Detailseite der Wissensquelle enthält Informationen wie:

- Der Schöpfer.
- Das Erstellungsdatum
- Die Anzahl der bereitgestellten Links oder Seiten.
- Die Anzahl der Links oder Seiten, die erfolgreich waren oder fehlgeschlagen sind.
- Die Zeit der letzten Aktualisierung.
- Die für die Verarbeitung berücksichtigten URLs.

## Fehlerbehebung bei Verarbeitungsfehlern

Wenn eine Wissensquelle den Status Teilweise erfolgreich aufweist, verwenden Sie den Problembericht, um die URLs zu identifizieren, die nicht verarbeitet werden konnten.

1. Öffnen Sie die Detailseite für die Wissensquelle.
1. Wählen Sie **Probleme beheben** aus, um eine Datei mit fehlerhaften oder nicht kratzbaren URLs sowie deren Fehlerdetails herunterzuladen.
1. Korrigieren Sie die ungültigen URLs oder entfernen Sie sie aus der Quellliste.
1. Laden Sie gegebenenfalls die korrigierte URL-Liste erneut hoch.
1. Anfordern der Neuverarbeitung, damit der korrigierte Inhalt zur Wissensquelle hinzugefügt wird.

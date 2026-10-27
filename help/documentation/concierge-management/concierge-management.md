---
title: Einen Concierge verwalten
description: Erfahren Sie, wie Sie eine Brand Concierge von einer Website aus erstellen, ihre Integrationen, Fertigkeiten, Anweisungen, den Ton und den visuellen Stil konfigurieren und sie vor der Bereitstellung testen können.
toc: true
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
source-git-commit: 91cbec8d6f4e4800e3bdc8c8f60bfe9ed168a963
workflow-type: tm+mt
source-wordcount: '1702'
ht-degree: 1%
---

# Einen Concierge verwalten

Ein Concierge wird auf einer Markenwebsite erstellt und kann mit Integrationen, Fähigkeiten, Anweisungen, Ton- und Spracheinstellungen, visuellen Stilen und Chat-Komponenten verfeinert werden. Verwenden Sie die Vorschau, um Änderungen zu testen, bevor Sie den Concierge absichtlich für Besucher bereitstellen.

## Übersicht

| Element | Details |
|---|---|
| Primärer Anwender | Marketer mit Self-Service-Konfiguration |
| Zusätzliche Unterstützung | Commerce- und B2B-Integrationen erfordern möglicherweise Codes, Schlüssel oder die Einrichtung durch ein IT-, Commerce- oder Vertriebs-Team |
| Typische Zeit | Ca. 5 Minuten, um einen Baseline-Concierge zu erstellen. Für Verfeinerung und Tests ist eine kontinuierliche Zeit erforderlich |
| Bereitstellung | Getrennt von der Erstellung; die Schaffung eines Concierge macht es nicht für Website-Besucher sichtbar |

>[!NOTE]
>
>Eine Sandbox kann mehrere Concierge enthalten. Jeder Concierge hat seine eigene Konfiguration und Concierge kann aus der Concierge-Liste gelöscht werden.

## Einen Concierge einrichten

Die Erstellung eines Concierge über eine einzelne Website-URL ist der empfohlene Ausgangspunkt für einen Erstnutzer. Das System erstellt eine Arbeitsbasislinie, ohne dass eine manuelle Konfiguration erforderlich ist.

1. Geben Sie die Website-URL der Marke ein und wählen Sie **Erstellen**.

1. Überprüfen Sie den generierten Markenausdruck. Das System analysiert den Ton der Website und schlägt Attribute wie Formalität, Wärme, Verspieltheit und Energie vor. Passen Sie die Werte nach Bedarf an und wählen Sie **Weiter**.

1. Überprüfen Sie das generierte Markenprofil. Das Profil kann das Markenziel, Produkte und Services, die Zielgruppe, Markenwerte, die wichtigsten Unterscheidungsmerkmale und gängige Anwendungsfälle enthalten. Bearbeiten Sie das Profil nach Bedarf und wählen Sie **Weiter** aus.

1. Überprüfen Sie die generierten Startanweisungen, Leitplanken und Vorschläge. Leitplanken können beispielsweise rechtliche Themen, Compliance-Themen oder Wettbewerbsdiskussionen ausschließen, während Vorschläge sofort einsetzbare Ideen liefern können. Bearbeiten Sie den Inhalt nach Bedarf und wählen Sie **Speichern** aus.

1. Warten Sie, bis das System die Basiskonfiguration angewendet hat. Das System erstellt außerdem einen visuellen Standardstil mit Farben und Schriftarten, die von der Website stammen, und aktiviert grundlegende Fähigkeiten und Integrationen, z. B. eine allgemeine Frage-und-Antwort-Fähigkeit im Zusammenhang mit Website-Inhalten.

1. Testen Sie den Concierge in der Vorschau. Desktop- und Mobilansichten sind verfügbar. Wählen Sie **Neu**, um eine Testunterhaltung neu zu starten.

>[!IMPORTANT]
>
>Ein Concierge ist für die Besucher nicht sichtbar. Die Bereitstellung ist ein separater, absichtlicher Schritt. Sie können die Konfiguration jederzeit vor der Bereitstellung überarbeiten.

## Wissenswertes zur automatischen Konfiguration

Die folgenden Elemente werden automatisch konfiguriert, wenn Sie einen Concierge erstellen:

| Element | Konfiguration |
|---|---|
| Wissensdatenbankinhalt | Erstellt von den Top-Seiten der Site durch einen Hintergrund-crawlen, der automatisch gestartet wird |
| Integration der Wissensdatenbanksuche | verweist automatisch auf den crawlen Inhalt |
| Site Advisory-Kenntnisse | Standardmäßig aktiv, damit der Concierge allgemeine Fragen sofort beantworten kann |

## Kenntnisse und Integrationen verstehen

Composer, die Schnittstelle zum Erstellen und Konfigurieren eines Concierge, verwendet zwei verwandte Konzepte:

- **Integration:** Eine Verbindung zu einer Datenquelle, z. B. Website-Inhalt oder Live-Produktkatalog. Eine Integration ruft Informationen ab, trifft jedoch keine eigenen Entscheidungen.
- **Geschicklichkeit:** ein Verhalten, das bestimmt, was der Concierge tut, wann er es tut und welche Integrationen er verwenden kann.

Eine Integration kann mehrere Fertigkeiten vermitteln, und eine Fertigkeit kann mehrere Integrationen verwenden. Beispielsweise kann eine einzelne Produktkatalogverbindung mehrere produktbezogene Anwendungsfälle unterstützen, ohne dass für jede Kenntnis ein Neuaufbau durchgeführt wird.

## Integrationen konfigurieren

Wählen Sie **Integrationen durchsuchen**, um den verfügbaren Integrationskatalog anzuzeigen.

| Integration | Zweck | Anmerkungen |
|---|---|---|
| Wissensdatenbanksuche | Durchsucht Website-Inhalte | Wird automatisch konfiguriert, wenn der Concierge erstellt wird |
| Content-KI-Suchen | Durchsucht AEM Sites-Inhalte | Relevant für Kunden von AEM Sites as a Cloud Service |
| Entitätsverknüpfung | Löst ein Produkt oder Markenerwähnung in einer Besuchernachricht in bestimmte Katalogentitäten auf. | Unterstützende Integration, die normalerweise zusammen mit einer Suchintegration und nicht allein verwendet wird |
| COMMERCE MCP | Stellt eine Verbindung zu einem Live-Adobe Commerce-Katalog her, um Produktsuche, Produktdetails und Vergleiche zu ermöglichen | Standardmäßig nicht aktiviert; erfordert Codes oder Schlüssel vom Commerce- oder IT-Team |
| Meeting-Buchung | Ermöglicht Besuchern die Buchung eines Meetings mit einem Vertriebsmitarbeiter | Erfordert die Einrichtung mit dem Kalender eines Vertriebsmitarbeiters. Siehe [Live-Chat und Meeting-Buchung](../sales-handoff/overview.md). |
| Live-Chat | Verbindet Besucher mit einem Live-Vertriebsmitarbeiter | Erfordert die Einrichtung durch einen Vertriebsmitarbeiter. Siehe [Live-Chat und Meeting-Buchung](../sales-handoff/overview.md). |

### Integration aktivieren und konfigurieren

1. Öffnen Sie die Integrationskachel und wählen Sie **Bearbeiten** aus.

1. Wählen **unter „Wissensdatenbanksuche** die zu durchsuchende Wissensquelle aus. Sie können die Verbindung umbenennen, z. B. `Website content`.

1. Geben Sie für **Commerce MCP** die folgenden Werte ein, die vom Adobe Commerce- oder IT-Team bereitgestellt werden, und verbinden Sie sich:
   - Umgebungs-ID
   - Website-Code
   - Code speichern
   - Code der Speicheransicht
   - API-Schlüssel

1. Wählen Sie **Speichern** aus. Die Integration wird als verbunden angezeigt und kann in der Vorschau angezeigt, bearbeitet oder entfernt werden.

Sie können mehr als eine Instanz derselben Integration hinzufügen, z. B. Instanzen, die auf verschiedene Wissensquellen verweisen. Kenntnisse können so konfiguriert werden, dass sie eine bestimmte Integrationsinstanz verwenden.

## Configure Skills

Fähigkeiten bestimmen, was ein Concierge für Besucher tun kann. Wählen Sie **Kenntnisse durchsuchen**, um den verfügbaren Kompetenzkatalog anzuzeigen.

| Skill | Zweck | Erforderliche Integration oder Konfiguration |
|---|---|---|
| Site-Beratung | Antworten auf allgemeine Markenfragen, einschließlich häufig gestellter Fragen (FAQs), Richtlinien, Preise, Anleitungen und Support-Themen | Website-Inhalt; standardmäßig aktiv |
| Produktberatung | Hilft Besuchern, Produkte anhand von namensbasierten Produktkarten zu entdecken und zu recherchieren und Produktfragen zu prosieren | Knowledge Base-Suche, Entitätsverknüpfung |
| Adobe Commerce-Katalogerkennung | Sucht, durchsucht, filtert und ruft Details zu Produkten aus einem Live-Katalog ab | Commerce MCP-Integration |
| Adobe Commerce - Produktvergleich | Bietet einen direkten Vergleich benannter Produkte | Commerce MCP-Integration |
| Übergabe an den Verkauf | Schlägt einen Live-Chat mit einem Vertriebsmitarbeiter oder eine Besprechungsbuchung vor und erleichtert diesen. | Live-Chat-Integration, Integration der Besprechungsbuchung |

### Kenntnisse aktivieren und konfigurieren

1. Öffnen Sie die Kachel Kenntnisse und wählen Sie **Ändern** aus.

1. Legen Sie den Namen, die Beschreibung und die Absichten der Kenntnis fest. Intents sind die Ausdrücke oder Themen, mit denen die Kenntnisse Trigger werden sollen, z. B. `pricing` oder `compare products`. Sie können mehrere Absichten hinzufügen.

1. Wenn für die Kenntnis eine Integration erforderlich ist, fügen Sie die erforderliche Integration hinzu. Für eine Commerce-Kenntnisse ist beispielsweise Commerce MCP erforderlich. Wählen Sie alternativ **Verwenden Sie empfohlen** aus, damit Composer automatisch eine entsprechende Integration auswählen kann.

1. Überprüfen und bearbeiten Sie bei Bedarf die Startanweisungen für die Kenntnisse.

1. Wählen **Speichern** und testen Sie die Änderung in der Live-Vorschau.

>[!TIP]
>
>Wenn zwei Fähigkeiten auf dieselbe Frage antworten könnten, kann das Routing inkonsistent werden. Behalten Sie die Trigger für Kenntnisse im Einzelnen und spezifisch bei, anstatt sich überschneidende Absichten zu verwenden.

## Concierge-Instruktionen hinzufügen

Verwenden Sie das Feld Concierge-Anweisungen , um die Antworten an die Markenrichtlinien anzupassen. Anweisungen können Folgendes definieren:

- Markennutzung
- Reaktionsstruktur
- Zu vermeidende Themen

Geben Sie Anweisungen direkt in das Textfeld ein. Wenn Sie die Anweisungen speichern, aktualisiert der Concierge automatisch sein Verhalten. Testen Sie das Ergebnis sofort in der Live-Vorschau.

Derselbe Bereich umfasst auch die folgenden bearbeitbaren Inhalte:

- **Leitplanken:** Verhaltensweisen oder Themen, die der Concierge vermeiden sollte.
- **Vorschläge:** Ideen, die nach einer Antwort angezeigt werden können.

## Ton und Stimme konfigurieren

Ton- und Spracheinstellungen steuern die Länge der Antwort und die Tonattribute, einschließlich:

- Formell oder gelegentlich
- Warm oder neutral
- Verspielt oder ernst

Die Auswahl wird automatisch gespeichert. Testen Sie das Ergebnis in der Live-Vorschau, nachdem Sie Änderungen vorgenommen haben.

## Konfigurieren des visuellen Stils

Visuelle Stileinstellungen steuern das Erscheinungsbild des Concierges, unter anderem:

- Farben
- Schriftarten
- Willkommenstext
- Text des Haftungsausschlusses
- Kartenfarben

Bearbeiten Sie die Einstellungen in der Benutzeroberfläche und verwenden Sie die Live-Vorschau, um Änderungen anzuzeigen. Wählen Sie **Speichern**, um die Änderungen dauerhaft zu machen.

## Konfigurieren von Chat-Komponenten

Chatkomponenten steuern die einzelnen Elemente, die Besucherinnen und Besucher im Chatfenster sehen. Wählen Sie eine Komponente in der Benutzeroberfläche aus, um ihre Einstellungen in einem Seitenbereich zu öffnen.

| Komponente | Was sie steuert |
|---|---|
| Chat-Blase | Das Erscheinungsbild von Besuchernachrichten und Concierge-Nachrichten |
| Start prompt oder prompt Tabletten | Vorgeschlagene Eröffnungsfragen, insbesondere auf Mobilgeräten |
| Vorschläge für Folgemaßnahmen | Empfohlene nächste Fragen nach einer Antwort |
| Eingabeleiste | Das Meldungsfeld, das Besucher verwenden, um eine Frage einzugeben |
| Zitate | Ob und wie Quellverweise in einer Antwort angezeigt werden |
| Feedback | Die Bewertung „Daumen hoch“ oder „Daumen runter“, die nach jeder Antwort angezeigt wird |
| Produktkarte | Layout und Stil von Produktkarten, einschließlich Farben und Schaltflächen |

## Konfigurieren der Besprechungsbuchung und des Live-Chats

Mit der Meeting-Buchung und dem Live-Chat können Besucher Meetings mit Vertriebsmitarbeitern buchen oder einen Live-Chat mit einem Vertreter starten. Diese Funktionen basieren auf einem Begleitprodukt namens [!DNL Adobe Marketo Qualifier] und werden Besuchern durch die Kenntnisse **[!UICONTROL Übergabe an den Verkauf]** angeboten.

### Rollen und Verantwortlichkeiten

- **Marketer:** Konfiguriert die Kenntnisse und Integrationen in Brand Concierge.
- **Vertriebsmitarbeiter:** verbindet den eigenen Kalender und konfiguriert die Verfügbarkeit in [!DNL Adobe Marketo Qualifier].

### Einrichten der Besprechungsbuchung oder des Live-Chats

Das vollständige Verfahren finden Sie unter [Live-Chat und Besprechungsbuchung](../sales-handoff/overview.md). Das Setup besteht aus vier Teilen:

1. [Richten Sie in Adobe Marketo Qualifier Repräsentanten ein](../sales-handoff/representative-setup.md) - Verbinden Sie einen Kalender, definieren Sie die Bestätigungs-E-Mail und legen Sie einen Kalender und die Verfügbarkeit von Live-Chats fest.

1. [Konversationen an Vertreter weiterleiten](../sales-handoff/routing-rules.md) - Wählen Sie Round Robin, einen direkten Agenten oder benutzerdefinierte Routing-Regeln.

1. [Live-Chat und Besprechungsbuchung aktivieren](../sales-handoff/configure-in-composer.md) - Verbinden Sie die Integrationen **[!UICONTROL Besprechungsbuchung]** und **[!UICONTROL Live-Chat]** und aktivieren Sie dann die **[!UICONTROL Übergabe an den Verkauf]**.

1. Wählen Sie **Simulieren** aus, um das End-to-End-Erlebnis zu testen. Geben Sie eine Beispielfrage ein und bestätigen Sie, dass sie an den richtigen Qualifikations- und Interaktionsfluss weitergeleitet wird.

### Verhalten nach der Bereitstellung

Wenn die Funktionen verfügbar sind:

- Eingehende Live-Chats werden verfügbaren Repräsentanten in Echtzeit im [Chat-Posteingang](../sales-handoff/chat-inbox.md) angezeigt.
- Gebuchte Meetings werden in einer Meetings -Ansicht angezeigt und in Analytics ist ein Meeting-Leistungsbericht verfügbar. Siehe [Überwachen von Meetings und Live-Chats](../sales-handoff/monitor.md).
- Meeting- und Chat-Interaktionen werden zusammen mit vorhandenen Aktivitätsdaten als Aktivitäten an Marketo gesendet. Siehe [Brand Concierge-Daten in Marketo Engage](../sales-handoff/marketo-activities.md).

## Vorschau-Link freigeben

Über einen freigebbaren Vorschau-Link können die Verantwortlichen einen Concierge überprüfen und mit ihm interagieren, ohne auf Composer zugreifen und den Concierge nicht auf einer Live-Website bereitstellen zu müssen.

1. Generieren Sie auf dem Bildschirm „Concierge-Vorschau“ einen freigabefähigen Vorschau-Link.

1. Freigeben des Links für Prüfer.

1. Reviewer können mit dem Concierge über den Link interagieren, ohne sich bei Composer anzumelden.

## Vor der Bereitstellung testen

Verwenden Sie das Vorschau- oder Simulationserlebnis nach jeder wichtigen Konfigurationsänderung. Überprüfen Sie mindestens Folgendes:

- Der Concierge beantwortet allgemeine Fragen zu den Inhalten der Website.
- Jede Qualifikation entspricht nur den beabsichtigten Triggern.
- Erforderliche Integrationen sind verbunden und verweisen auf die richtige Datenquelle.
- Produktsuchen und -vergleiche verwenden die beabsichtigte Commerce-MCP- oder Produktkataloginstanz.
- Meeting-Buchung und Live-Chat zu den vorgesehenen Vertretern.
- Ton, Stimme, Anweisungen, Leitplanken und Vorschläge bringen die erwarteten Reaktionen hervor.
- Visuelle Stile und Chatkomponenten werden auf Desktop- und Mobilansichten korrekt angezeigt.
- Stakeholder können das Erlebnis über den freigabefähigen Vorschau-Link überprüfen, falls einer verwendet wird.

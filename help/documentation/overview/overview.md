---
title: Übersicht über Brand Concierge
description: Erfahren Sie, was Brand Concierge ist, wie die Hauptkomponenten zusammenpassen und welches Glossar Sie in der Composer-Benutzeroberfläche finden.
source-git-commit: 60835c7971d86341194d773f9cf487c4cb6f171a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 2%

---

# Übersicht über Brand Concierge

Brand Concierge ist eine Agentenplattform, mit der Unternehmen und Marken personalisierte Konversationserlebnisse auf ihren kundenorientierten Oberflächen starten können: Websites, mobile Apps und andere digitale Eigenschaften. Jedes Gespräch basiert auf dem eigenen Inhalt und den Leitplanken der Marke, und durch Integrationen können Einblicke aus diesen Gesprächen in das übrige Ökosystem der Marke wie Marketo Engage einfließen.

## Hauptkomponenten

Eine Brand Concierge-Bereitstellung umfasst zwei Hauptkomponenten:

| Stück | Was es ist |
|---|---|
| **Besuchererlebnis** | Die markenorientierte Oberfläche, z. B. eine Website oder eine mobile App, auf der Besucher mit dem Concierge interagieren und in Echtzeit Antworten erhalten. |
| **Composer** | Die Benutzeroberfläche des Praktikers, die zum Entwerfen von Concierge-Erlebnissen und zum Verwalten von Concierge-Erlebnissen, Integrationen, Konfigurationen, Auswertungen, Bereitstellung und Analysen verwendet wird. |

## Composer-Module

Innerhalb von Composer sind die wichtigsten Module:

- [Benutzer- und Zugriffsverwaltung](../user-and-access-management/add-a-user-to-the-org.md)
- [Erstellung und Verwaltung von Wissensquellen](../knowledge-sources/knowledge-sources.md), die von allen Concierges gemeinsam genutzt werden
- [Concierge-](../concierge-management/concierge-management.md): Integrationen, Fähigkeiten, Concierge-Anweisungen, Ton und Stimme, visueller Stil und Chat-Komponenten
- [Auswertung](../evaluation/evaluation.md)
- [Bereitstellung](../deployment/deployment.md)
- [Go-Live-Checkliste](../go-live-checklist/go-live-checklist.md)
- [Analytics](../analytics/analytics.md)

## Verbindung der Teile

Eine Wissensquelle (Inhalt) wird von einer Integration (Verbindung) abgefragt, die von einer Fähigkeit (Verhalten) aufgerufen wird, die alle in einen Concierge (das Gesamterlebnis) eingeschlossen sind, mit dem die Besucher interagieren.

## Glossar

Diese Begriffe erscheinen auf der gesamten Benutzeroberfläche des Komponisten.

| Begriff | Definition |
|---|---|
| **Concierge** | Das KI-Chat-Erlebnis selbst: eines pro Marke, Website oder Anwendungsfall. Ein Konto kann mehrere Konten haben. |
| **Composer** | Die Benutzeroberfläche, die zum Erstellen und Verwalten von Concierges verwendet wird, die sich von dem unterscheiden, was Website-Besucherinnen und -Besucher sehen. |
| **Wissensquelle** | Die Inhalte, die ein Concierge bei der Beantwortung von Fragen verwenden darf, wie z. B. Webseiten oder Produktlisten. Ohne eine solche Frage hat der Concierge dem Gast keine Antwort zu erteilen. |
| **Integration** | Eine Verbindung zu einem System, das Informationen wie Website-Inhalte oder einen Live-Produktkatalog abrufen kann. |
| **SKILL** | Eine spezifische Funktion, die der Concierge ausführen kann, z. B. Antworten auf allgemeine Fragen, Produktvergleiche oder die Buchung eines Meetings. Eine Qualifikation verwendet eine oder mehrere Integrationen, um ihre Funktion auszuführen. |
| **Schutzmechanismen** | Regeln, die definieren, was der Concierge nicht tun oder besprechen sollte, wie Wettbewerber oder Rechtsberatung. |
| **Evaluierung** | Ein strukturierter Test, bestehend aus Beispielfragen, gepaart mit erwarteten Antworten, der zur Beurteilung der Leistung des Concierge verwendet wird. |
| **Datenstrom-ID** | Eine technische Kennung, die angibt, wohin Besucheraktivitätsdaten in Adobe-Systemen gesendet werden. Es wird vom IT- oder Analytics-Team bereitgestellt. |
| **Sandbox** | Ein isolierter Arbeitsbereich innerhalb einer Organisation. Eine Organisation kann mehr als einen haben; jeder kann mehrere Concierge aufnehmen. |
| **IMS-Organisation** | Adobes Begriff für das Gesamtkonto eines Unternehmens. |
| **MCP** (z. B. Commerce MCP) | Ein von Adobe verwalteter Connector für ein bestimmtes System, z. B. einen Live-Produktkatalog, der mithilfe von Codes oder Schlüsseln konfiguriert wird, die von IT oder dem Commerce-Team bereitgestellt werden. |
| **CJA (Customer Journey Analytics)** | Analytics-Produkt von Adobe. Brand Concierge stellt hier automatisch ein Starter-Dashboard bereit, ohne dass eine zusätzliche Einrichtung erforderlich ist. |

>[!NOTE]
>
>Marketing-Experten können in der Regel [Benutzer- und Zugriffsverwaltung](../user-and-access-management/add-a-user-to-the-org.md) vollständig überspringen (jemand in der IT schließt sie einmal ab) und mit [Wissensquellen](../knowledge-sources/knowledge-sources.md) beginnen. Kehren Sie nur bei der Einrichtung neuer Teammitglieder zur Benutzer- und Zugriffsverwaltung zurück.

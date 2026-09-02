---
title: Bewerten eines Concierge
description: Erfahren Sie, wie Sie Bewertungssets erstellen und funktionale, außer dem Umfang liegende und sichere Bewertungen durchführen, um die Genauigkeit und Sicherheit der Antworten eines Concierge zu bewerten.
hide: true
source-git-commit: fc22eb8e724437483e5d87283f46fb629a4e507c
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---


# Bewerten eines Concierge

**Für wen ist das?** Marketing-Experten, die das Self-Service-Erlebnis verwenden. Es ist keine IT-Unterstützung erforderlich.

**Erforderliche Zeit:** Sie einige Minuten, um einen Auswertungssatz zu erstellen. Die Ausführung einer Auswertung dauert je nach Größe des Sets länger.

Auswertungen helfen Ihnen dabei, das Vertrauen zu schaffen, dass die Antworten eines Concierges korrekt sind, bevor der Concierge von jemandem außerhalb Ihres unmittelbaren Teams geprüft wird. Im Gegensatz zu Ad-hoc-Tests im Vorschauerlebnis bieten Auswertungen eine wiederholbare Möglichkeit, Antworten mit erwarteten Antworten zu messen.

## Auswertungstypen

Die Bewertungen lassen sich in drei Kategorien einteilen:

| Typ | Zweck |
|---|---|
| funktionell | Prüft Antworten auf normale, relevante Fragen zu Ihren Produkten oder Dienstleistungen. |
| Außerhalb des Geltungsbereichs | Überprüft, wie der Concierge mit Fragen umgeht, die er nicht beantworten sollte, die aber nicht schädlich sind, z. B. Fragen zu einem Mitbewerber oder einem anderen Thema. |
| Schutzmaßnahme | Überprüft, wie der Concierge mit schädlichen oder gegnerischen Eingaben umgeht, einschließlich Trickfragen, Obszönitäten und Versuchen, sie zu manipulieren. |

## Erstellen eines Auswertungssets

Ein Auswertungssatz, auch als &quot;*Datensatz“ oder**Grundwahrheit* bezeichnet, ist eine Liste von Beispielfragen, die zusammen mit den als korrekt erachteten Antworten gestellt werden. Die tatsächlichen Antworten des Concierge werden während einer Bewertung mit den erwarteten Antworten verglichen.

### Erstellen eines Auswertungssets

1. Benennen Sie das Auswertungsset. Beispiel: `About my products`.

1. Legen Sie fest, wie das Set erstellt werden soll:

   * **KI-generiert:** Composer liest die Wissensquelle und entwirft eine Liste wahrscheinlicher Fragen und erwarteter Antworten zur Überprüfung.
   * **Manueller oder Tabellen-Upload:** Stellen Sie eine Liste mit Fragen und Antworten direkt zur Verfügung.

1. Wenn Sie einen KI-generierten Satz erstellen, stellen Sie sicher, dass die Wissensquelle vollständig konfiguriert ist, bevor Sie den Satz generieren. Der Komponist verwendet die Wissensquelle, um die Fragen und Antworten zu entwerfen.

1. Überprüfen Sie jedes generierte Frage-Antwort-Paar:

   * Bearbeiten Sie eine Antwort, um ihre Formulierungen anzupassen.
   * Eine Frage löschen, die nicht relevant ist.

1. Optional können Sie das Set als Arbeitsblatt zur Überprüfung durch einen Kollegen herunterladen. Laden Sie nach der Überprüfung die Tabelle erneut hoch.

>[!TIP]
>
>KI-generierte Auswertungssätze sind Entwürfe, die auf der Wissensquelle basieren. Überprüfen und korrigieren Sie sie auf dieselbe Weise wie das Markenprofil und die Anweisungen während der Concierge-Erstellung.

## Ausführen einer Evaluierung

1. Wählen Sie **Test ausführen** aus.

1. Wählen Sie den auszuführenden Auswertungssatz und dann **Ausführen** aus.

1. Warten Sie, während dem Concierge alle Fragen im Set gestellt werden. Die tatsächlichen Antworten des Portiers werden mit den erwarteten Antworten verglichen.

   Die Verarbeitungszeit steigt mit der Anzahl der Fragen im Satz. Der Fortschritt wird als Prozentsatz angezeigt.

1. Überprüfen Sie nach Abschluss der Verarbeitung die Gesamtpunktzahl und die Anzahl der markierten Antworten.

Markierte Antworten sind potenziell problematische Antworten, die möglicherweise einer zusätzlichen Überprüfung bedürfen.

## Überprüfen der Bewertungsergebnisse

**Auswertungsergebnisse** zeigt jeden vergangenen Durchlauf für einen Auswertungssatz an, damit Sie die Ergebnisse im Zeitverlauf verfolgen können.

So überprüfen Sie einen Durchlauf:

1. Öffnen Sie einen Auswertungsdurchgang über **Auswertungsergebnisse**.

1. Besprechen Sie jede Frage zusammen mit der tatsächlichen Antwort des Concierges und der erwarteten Antwort.

1. Überprüfen Sie die jedem Ergebnis zugewiesene Bewertung. Die Ergebnisse erhalten eine **hoch**, **mittel** oder **niedrig** Bewertung und enthalten einen Hinweis zur Erläuterung der Begründung. Beispielsweise kann ein Ergebnis mit einem Grund für **Bewertung als** Aufmerksamkeit erforderlich“ gekennzeichnet werden.

1. Überprüfen Sie markierte Antworten direkt, um sich auf potenziell problematische Ergebnisse zu konzentrieren, ohne jedes Ergebnis im Durchlauf zu lesen.

## Best Practices

* Konfigurieren Sie die Wissensquelle vollständig, bevor Sie einen KI-basierten Auswertungssatz generieren. Vollständigere Quellinhalte erzeugen bessere Fragenentwürfe.
* Erstellen Sie für jeden Auswertungstyp mindestens ein kleines Auswertungsset: „Funktionell“, „Außerhalb des Bereichs“ und „Sichern“. Jeder Typ erfasst eine andere Problemklasse.
* Führen Sie Bewertungen nach jeder sinnvollen Konfigurationsänderung erneut aus, einschließlich Änderungen an Anweisungen, Leitplanken, Fähigkeiten oder Integrationen. Behandeln Sie Auswertungen als fortlaufende Praxis und nicht als einmalige Bewertung.
* Fügen Sie echte Besucherfragen aus Analytics zu einem Auswertungssatz hinzu, wenn sich eine Lücke ergibt, die es wert ist, getestet zu werden.

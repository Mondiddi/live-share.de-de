---
title: Übersicht | Microsoft-Dokumentation
description: Eine Übersicht über Visual Studio Live Share und dessen Funktionen.
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: fd6c028729c6b376e48995a01c8f625b96d06f85
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870776"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Live Share von Features und Konzepten 

Live Share wird mithilfe von revolutionärer Architektur und Konzepten erstellt, die als leistungsstarke Features für unsere Benutzer stehen. Im folgenden finden Sie alle untergeordneten Features von Live Share und damit eine führende Rolle im Zusammenarbeits Bereich. 

### <a name="collaboration-sessions"></a>Zusammenarbeitssitzungen

Alle Zusammenarbeitsaktivitäten in Visual Studio Live Share umfassen einen einzigen **Zusammenarbeitssitzungs-Gastgeber** und einen oder mehrere **Gäste**. Der Host ist die Person, die die Zusammenarbeits Sitzung gestartet hat, und jeder, der Joins ist ein Gast.

Zusammenarbeitssitzungs-Gastgeber können alle ihre Tools und Dienste nutzen, während Gästen Zugriff auf nur die Dinge gewährt wird, die der Gastgeber speziell für sie freigegeben hat. Dazu gehören Code, das Ausführen von Servern, Debugsitzungen, Terminals und vieles mehr. Derzeit werden sämtliche freigegebenen Inhalte auf dem Computer des Gastgebers gespeichert und nicht mit der Cloud oder dem Computer des Gasts synchronisiert. Dies ermöglicht _Sofortzugriff_ und _erhöhte Sicherheit_. Der Vorteil besteht darin, dass die gesamte Lösung sofort zur Verfügung steht, wenn ein Gast beitritt, und sofort, wenn ein Gast die Zusammenarbeitssitzung beendet, nicht mehr verfügbar ist. Außerdem werden temporäre Dateien, die durch IDE/Editor zur Leistungsverbesserung für den Gast erstellt wurden, am Ende der Sitzung automatisch bereinigt.

#### <a name="sharing"></a>Freigabe

Wenn Sie etwas als Gastgeber „freigeben“, starten Sie eine Zusammenarbeitssitzung, in der die Inhalte eines Projekts, einer Lösung oder eines Ordners freigegeben sind. Gäste erhalten über den Einladungslink, den Sie ihnen senden, Zugriff auf diesen Inhalt. Während „Freigabe“ eine Kurzform für „Freigabe eines Projekts“ ist, öffnet sie auch die Tür zur Freigabe anderer Funktionen wie dem Debuggen.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

#### <a name="joining"></a>Verknüpfen

Wenn Sie auf einen Einladungslink klicken, der Ihnen von einem Gastgeber gesendet wurde, können Sie einer Zusammenarbeitssitzung als Gast „beitreten“ und auf alle Inhalte oder Funktionen zugreifen, die der Gastgeber durch Aktivierung für Sie freigegeben hat. Der Weblink bietet eine schnelle Möglichkeit, in eine Zusammenarbeitssitzung zu springen, wenn Sie die Erweiterung bereits installiert haben, und – wenn nicht – eine schnelle Möglichkeit zum Einrichten von Informationen.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#join-a-collaboration-session) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#join-a-collaboration-session)

### <a name="features"></a>Features

#### <a name="co-editing"></a>Gemeinsame Bearbeitung

Wenn Sie dieselbe Datei als ein weiterer Projektmitarbeiter öffnen, können Sie deren Inhalte sofort „gemeinsam bearbeiten“. Sie können die Bearbeitungen jedes Mitarbeiters, deren Cursor und Auswahlen und vieles mehr sehen. Noch besser: Sie sind nicht gezwungen, jederzeit dieselbe Datei zu bearbeiten. So können Sie gegebenenfalls zusammenarbeiten und ganz nach Wunsch unabhängig agieren.

> [!NOTE]
> Bei der gemeinsamen Bearbeitung gibt es ein paar Einschränkungen. Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-editing) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Folgen und sich konzentrieren

Manchmal müssen Sie ein Problem erläutern oder etwas entwerfen, dass sich über mehrere Dateien oder Stellen im Code erstreckt. In diesen Fällen kann es hilfreich sein, einem Kollegen vorübergehend zu folgen, während er sich bei der gemeinsamen Bearbeitung durch das gesamte Projekt bewegt. Aus diesem Grund „folgen“ Sie als Gast beim Beitritt zu einer Zusammenarbeitssitzung automatisch der Bearbeitungsstelle des Gastgebers. Gastgeber und Gäste können mit einem einfachen Mausklick aufeinander folgend hinein- und hinausspringen. Außerdem möchten Sie vielleicht alle Teilnehmer bitten, Ihnen zu folgen. In Live Share können Sie mit einer Benachrichtigung anfordern, dass jeder seine Aufmerksamkeit auf Sie „konzentriert“. Dies erleichtert es den Teilnehmern, Ihnen ebenfalls zu folgen.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#following) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#following)

#### <a name="co-debugging"></a>Gemeinsames Debuggen

Wenn Sie schwierige Codierungsprobleme oder Fehler debuggen, kann es sehr hilfreich sein, dass sich eine weitere Person dies anschaut. Dem Gastgeber ermöglicht Live Share automatisch „gemeinsames Debuggen“, indem er die Debugsitzung für alle Gäste freigibt. Jeder Gast erhält Features für gemeinsame Bearbeitung zusammen mit der Möglichkeit zur unabhängigen Untersuchung während des gemeinsamen Durchlaufs.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Freigeben eines Servers / Freigeben eines Ports

Beim gemeinsamen Debuggen kann es sehr hilfreich sein, Zugriff auf verschiedene Teile der Anwendung zu erhalten, die den Gästen vom Gastgeber für die Debugsitzung „serviert“ werden. Vielleicht möchten Sie auf die App in einem Browser zugreifen, auf eine lokale Datenbank zugreifen oder über Ihre Tools einen REST-Endpunkt erreichen. Live Share ermöglicht Ihnen die „Freigabe eines Servers“, wodurch ein lokaler Port auf dem Computer des Gastgebers genau demselben Port auf dem Computer jedes Gasts zugeordnet wird. Als Gast können Sie dann mit der Anwendung genauso interagieren, als wenn sie auf Ihrem Computer lokal ausgeführt würde (beispielsweise können sowohl Gastgeber als auch Gast auf eine Web-App zugreifen, die auf dem http://localhost:3000) ausgeführt wird).

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

#### <a name="share-terminals"></a>Freigeben von Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise ermöglicht Live Share es Ihnen als Gastgeber, für Gäste optional „ein Terminal freizugeben“. Das freigegebene Terminal kann schreibgeschützt oder vollständig für Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Als Gastgeber behalten Sie immer die Kontrolle und können entscheiden, ob andere Projektmitarbeiter Befehle selber ausführen oder nur die Befehlsausgabe anzeigen können. Tatsächlich können Sie alles, was Sie für sich behalten möchten, in einem nicht freigegebenen Terminal ausführen.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Zugriffssteuerung

Visual Studio Live Share bietet Teilnehmern zahlreiche tolle Möglichkeiten für die Zusammenarbeit. Allerdings möchten Sie angesichts der Anzahl der Optionen und der Flexibilität, die Gäste für die Interaktion mit Gastgebern erhalten, beitretende Gäste möglicherweise explizit genehmigen oder den Zugriff auf bestimmte Dateien oder Ordner sperren. In Live Share gibt es eine Reihe von Einstellungen, die Ihnen dabei helfen, darunter Schreibschutz und die Anforderung der Akzeptanz von Gästen.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../reference/security.md) [ ![ vs](../media/vs-icon-15x15.png)](../reference/security.md)

#### <a name="flexible-connection-modes"></a>Flexible Verbindungsmodi

Um eine optimale Leistung sicherzustellen, unterstützt Visual Studio Live Share zwei grundlegende „Verbindungsmodi“: „direkt“ und „Relay“. Im direkten Modus werden Gäste ohne den Umweg über das Web direkt verbunden. Der Relaymodus ermöglicht es Gästen, die sich in einem völlig anderen Netzwerk befinden, sich mit dem Gastgeber über ein Internet-Relay zu verbinden. In allen Fällen werden Verbindungen SSH- oder SSL-verschlüsselt, um sicherzustellen, dass nur Projektmitarbeiter Zugriff auf das erhalten, was gerade übertragen wird. Live Share befindet sich standardmäßig im Modus „Automatisch“, bei dem zuerst eine direkte Verbindung versucht und dann ein Failover zum Relay ausgeführt wird. Wenn es Ihnen aber lieber ist, können Sie in einen einzelnen Modus sperren.

**Weitere Informationen:** [ ![ vs Code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [ ![ vs](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode)

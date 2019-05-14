---
title: Übersicht – Visual Studio Live Share | Microsoft-Dokumentation
description: Eine Übersicht über Visual Studio Live Share und dessen Funktionen.
ms.custom: ''
ms.date: 05/01/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6097d94b83f3c2370c87f1d27ba9fd51f24c9896
ms.sourcegitcommit: cab8df5c29f9d91e702ef514def53944ee7701ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "64987173"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Was ist Visual Studio Live Share?

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können Ihr aktuelles Projekt sofort und sicher freigeben und anschließend nach Bedarf Debugsitzungen, Terminalinstanzen, Localhost-Web-Apps, Sprachanrufe und vieles mehr freigeben!

Im Gegensatz zur herkömmlichen Paarprogrammierung ermöglicht es Visual Studio Live Share Entwicklern außerdem zusammenzuarbeiten, gleichzeitig aber ihre persönlichen Editoreinstellungen (z.B. Design, Tastenzuordnungen) und ihren eigenen Cursor beizubehalten. Dies ermöglicht Ihnen einen nahtlosen Übergang zwischen „einander folgen“ und Ideen/Aufgaben alleine erkunden können. In der Praxis bietet diese Möglichkeit, zusammenzuarbeiten _und_ unabhängig zu sein, eine Erfahrung der Zusammenarbeit, die bei vielen gängigen Anwendungsfällen eventuell natürlicher ist.

Sind Sie bereit? In diesem Artikel führen wir Sie durch einige Konzepte und die Schritte zum Installieren der erforderlichen Erweiterungen. Wenn Sie nach einer verkürzten Version suchen, lesen Sie die Schnellstarts zu [Freigabe](quickstart/share.md) und [Beitritt](quickstart/join.md).

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

## <a name="install-visual-studio-live-share"></a>Installieren von Visual Studio Live Share

Bevor Sie beginnen, müssen Sie eine Version von Visual Studio oder Visual Studio Code installiert haben, die grundlegende Anforderungen von Live Share erfüllt.

- **Visual Studio Code 1.22.0 oder höher** – Windows 7, 8.1 oder 10, macOS *(nur Sierra 10.12 und höher)*, 64-Bit-Linux *(64-Bit-Ubuntu Desktop 16.04+, Fedora 27+ wird empfohlen – [siehe die Details](use/vscode.md#installation))*.
- **Visual Studio 2019** (beliebige Edition) – Windows 7, 8.1 oder 10.
- **Visual Studio 2017 15.6 oder höher** (beliebige Edition) – Windows 7, 8.1 oder 10.

Danach ist das Herunterladen und Installieren der Visual Studio Live Share-Erweiterung kinderleicht:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Installieren Sie <a href="https://code.visualstudio.com/">Visual Studio Code</a> für Windows (7, 8.1 oder 10), macOS <b>(Sierra+)</b>, 64-Bit-Linux <b> (<a href="use/vscode.md#installation">Details</a>)</b><br />
        2. Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter, und installieren Sie sie. <br />
        3. Laden Sie sie erneut, und warten Sie, dass die Abhängigkeiten heruntergeladen und installiert werden (siehe die Statusleiste).<br />
        4. <strong>Linux</strong>: Wenn Sie aufgefordert werden, <a href="reference/linux.md#install-linux-prerequisites">Bibliotheken zu installieren</a>, klicken Sie auf „Installieren“, geben Sie das Kennwort ein, und starten Sie abschließend VS Code erneut.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019</strong><br />
        1.Installieren Sie <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Installieren Sie eine <a href="reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++, Python und/oder Node.js)<br />
        3. Visual Studio Live Share wird mit diesen Workloads standardmäßig installiert. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 oder höher</strong><br />
        1. Installieren Sie die neueste Version von <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6+) unter Windows (7, 8.1 oder 10).<br/>
        2. Installieren Sie eine <a href="reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)<br />
        3. Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter, und installieren Sie sie. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](troubleshooting.md).

Das ist schon alles! Jetzt sollten Sie in VS Code in der Statusleiste unten links ein Zeichen sehen und in Visual Studio oben rechts eine Freigabeschaltfläche. Schauen Sie in der restlichen Dokumentation nach, was als Nächstes zu tun ist!

## <a name="concepts-and-features"></a>Konzepte und Features

Wie jedes Produkt bietet Visual Studio Live Share eine Reihe von leistungsstarken Features, die aus einigen grundlegenden Konzepten erstellt wurden. Dieser Abschnitt enthält einige Konzepte und eine kurze Einführung in die Features.

### <a name="collaboration-sessions"></a>Zusammenarbeitssitzungen

Alle Zusammenarbeitsaktivitäten in Visual Studio Live Share umfassen einen einzigen **Zusammenarbeitssitzungs-Gastgeber** und einen oder mehrere **Gäste**. Der Gastgeber ist die Person, die die Zusammenarbeitssitzung gestartet hat, und jede Person, die ihr beitritt, ist ein Gast.

Zusammenarbeitssitzungs-Gastgeber können alle ihre Tools und Dienste nutzen, während Gästen Zugriff auf nur die Dinge gewährt wird, die der Gastgeber speziell für sie freigegeben hat. Dazu gehören Code, das Ausführen von Servern, Debugsitzungen, Terminals und vieles mehr. Derzeit werden sämtliche freigegebenen Inhalte auf dem Computer des Gastgebers gespeichert und nicht mit der Cloud oder dem Computer des Gasts synchronisiert. Dies ermöglicht _Sofortzugriff_ und _erhöhte Sicherheit_. Der Vorteil besteht darin, dass die gesamte Lösung sofort zur Verfügung steht, wenn ein Gast beitritt, und sofort, wenn ein Gast die Zusammenarbeitssitzung beendet, nicht mehr verfügbar ist. Außerdem werden temporäre Dateien, die durch IDE/Editor zur Leistungsverbesserung für den Gast erstellt wurden, am Ende der Sitzung automatisch bereinigt.

#### <a name="sharing"></a>Freigabe

Wenn Sie etwas als Gastgeber „freigeben“, starten Sie eine Zusammenarbeitssitzung, in der die Inhalte eines Projekts, einer Lösung oder eines Ordners freigegeben sind. Gäste erhalten über den Einladungslink, den Sie ihnen senden, Zugriff auf diesen Inhalt. Während „Freigabe“ eine Kurzform für „Freigabe eines Projekts“ ist, öffnet sie auch die Tür zur Freigabe anderer Funktionen wie dem Debuggen.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>Verknüpfen

Wenn Sie auf einen Einladungslink klicken, der Ihnen von einem Gastgeber gesendet wurde, können Sie einer Zusammenarbeitssitzung als Gast „beitreten“ und auf alle Inhalte oder Funktionen zugreifen, die der Gastgeber durch Aktivierung für Sie freigegeben hat. Der Weblink bietet eine schnelle Möglichkeit, in eine Zusammenarbeitssitzung zu springen, wenn Sie die Erweiterung bereits installiert haben, und – wenn nicht – eine schnelle Möglichkeit zum Einrichten von Informationen.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>Features

#### <a name="co-editing"></a>Gemeinsame Bearbeitung

Wenn Sie dieselbe Datei als ein weiterer Projektmitarbeiter öffnen, können Sie deren Inhalte sofort „gemeinsam bearbeiten“. Sie können die Bearbeitungen jedes Mitarbeiters, deren Cursor und Auswahlen und vieles mehr sehen. Noch besser: Sie sind nicht gezwungen, jederzeit dieselbe Datei zu bearbeiten. So können Sie gegebenenfalls zusammenarbeiten und ganz nach Wunsch unabhängig agieren.

> [!NOTE]
> Bei der gemeinsamen Bearbeitung gibt es ein paar Einschränkungen. Lesen Sie [Plattformunterstützung](reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Folgen und sich konzentrieren

Manchmal müssen Sie ein Problem erläutern oder etwas entwerfen, dass sich über mehrere Dateien oder Stellen im Code erstreckt. In diesen Fällen kann es hilfreich sein, einem Kollegen vorübergehend zu folgen, während er sich bei der gemeinsamen Bearbeitung durch das gesamte Projekt bewegt. Aus diesem Grund „folgen“ Sie als Gast beim Beitritt zu einer Zusammenarbeitssitzung automatisch der Bearbeitungsstelle des Gastgebers. Gastgeber und Gäste können mit einem einfachen Mausklick aufeinander folgend hinein- und hinausspringen. Außerdem möchten Sie vielleicht alle Teilnehmer bitten, Ihnen zu folgen. In Live Share können Sie mit einer Benachrichtigung anfordern, dass jeder seine Aufmerksamkeit auf Sie „konzentriert“. Dies erleichtert es den Teilnehmern, Ihnen ebenfalls zu folgen.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>Gemeinsames Debuggen

Wenn Sie schwierige Codierungsprobleme oder Fehler debuggen, kann es sehr hilfreich sein, dass sich eine weitere Person dies anschaut. Dem Gastgeber ermöglicht Live Share automatisch „gemeinsames Debuggen“, indem er die Debugsitzung für alle Gäste freigibt. Jeder Gast erhält Features für gemeinsame Bearbeitung zusammen mit der Möglichkeit zur unabhängigen Untersuchung während des gemeinsamen Durchlaufs.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Freigeben eines Servers / Freigeben eines Ports

Beim gemeinsamen Debuggen kann es sehr hilfreich sein, Zugriff auf verschiedene Teile der Anwendung zu erhalten, die den Gästen vom Gastgeber für die Debugsitzung „serviert“ werden. Vielleicht möchten Sie auf die App in einem Browser zugreifen, auf eine lokale Datenbank zugreifen oder über Ihre Tools einen REST-Endpunkt erreichen. Live Share ermöglicht Ihnen die „Freigabe eines Servers“, wodurch ein lokaler Port auf dem Computer des Gastgebers genau demselben Port auf dem Computer jedes Gasts zugeordnet wird. Als Gast können Sie dann mit der Anwendung genauso interagieren, als wenn sie auf Ihrem Computer lokal ausgeführt würde (beispielsweise können sowohl Gastgeber als auch Gast auf eine Web-App zugreifen, die auf dem http://localhost:3000) ausgeführt wird).

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>Freigeben von Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise ermöglicht Live Share es Ihnen als Gastgeber, für Gäste optional „ein Terminal freizugeben“. Das freigegebene Terminal kann schreibgeschützt oder vollständig für Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Als Gastgeber behalten Sie immer die Kontrolle und können entscheiden, ob andere Projektmitarbeiter Befehle selber ausführen oder nur die Befehlsausgabe anzeigen können. Tatsächlich können Sie alles, was Sie für sich behalten möchten, in einem nicht freigegebenen Terminal ausführen.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Zugriffssteuerungen

Visual Studio Live Share bietet Teilnehmern zahlreiche tolle Möglichkeiten für die Zusammenarbeit. Allerdings möchten Sie angesichts der Anzahl der Optionen und der Flexibilität, die Gäste für die Interaktion mit Gastgebern erhalten, beitretende Gäste möglicherweise explizit genehmigen oder den Zugriff auf bestimmte Dateien oder Ordner sperren. In Live Share gibt es eine Reihe von Einstellungen, die Ihnen dabei helfen, darunter Schreibschutz und die Anforderung der Akzeptanz von Gästen.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>Flexible Verbindungsmodi

Um eine optimale Leistung sicherzustellen, unterstützt Visual Studio Live Share zwei grundlegende „Verbindungsmodi“: „direkt“ und „Relay“. Im direkten Modus werden Gäste ohne den Umweg über das Web direkt verbunden. Der Relaymodus ermöglicht es Gästen, die sich in einem völlig anderen Netzwerk befinden, sich mit dem Gastgeber über ein Internet-Relay zu verbinden. In allen Fällen werden Verbindungen SSH- oder SSL-verschlüsselt, um sicherzustellen, dass nur Projektmitarbeiter Zugriff auf das erhalten, was gerade übertragen wird. Live Share befindet sich standardmäßig im Modus „Automatisch“, bei dem zuerst eine direkte Verbindung versucht und dann ein Failover zum Relay ausgeführt wird. Wenn es Ihnen aber lieber ist, können Sie in einen einzelnen Modus sperren.

**Weitere Informationen:** [![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Freigeben Ihres ersten Projekts](quickstart/share.md)
- [Beitreten zu Ihrer ersten Sitzung](quickstart/join.md)

Gewusst wie

- [Zusammenarbeiten mithilfe von Visual Studio Code](use/vscode.md)
- [Zusammenarbeiten mithilfe von Visual Studio](use/vs.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Unterstützung für Erweiterung](reference/extensions.md)
- [Anmerkungen zu dieser Version](https://aka.ms/vsls-releases)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

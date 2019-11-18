---
title: Übersicht – Visual Studio Live Share | Microsoft-Dokumentation
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
ms.openlocfilehash: 3f6ad9fd00984abeca2b826addee54271eb1191a
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019748"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Was ist Visual Studio Live Share?

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können Ihr aktuelles Projekt sofort und sicher freigeben, eine gemeinsame Debugsitzung starten Terminalinstanzen freigeben, Localhost-Web-Apps weiterleiten, Sprachanrufe tätigen und vieles mehr!

 Im Gegensatz zur herkömmlichen Paarprogrammierung ermöglicht es Visual Studio Live Share Entwicklern außerdem zusammenzuarbeiten, gleichzeitig aber ihre persönlichen Editoreinstellungen (z. B. Design, Tastenzuordnungen) und ihren eigenen Cursor beizubehalten. Dies ermöglicht Ihnen einen nahtlosen Übergang zwischen „einander folgen“ und Ideen/Aufgaben alleine erkunden können. Die Möglichkeit, zusammenzuarbeiten und auch unabhängig voneinander zu arbeiten, schafft eine Erfahrung, die sich wie eine _persönliche_ Zusammenarbeit anfühlt.

Sind Sie bereit? In diesem Artikel führen wir Sie durch einige Konzepte und die Schritte zum Installieren der erforderlichen Erweiterungen. Wenn Sie nach einer verkürzten Version suchen, lesen Sie die Schnellstarts zu [Freigabe](quickstart/share.md) und [Beitritt](quickstart/join.md).

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

## <a name="install-visual-studio-live-share"></a>Installieren von Visual Studio Live Share

Bevor Sie beginnen, müssen Sie eine Version von Visual Studio oder Visual Studio Code installiert haben, die grundlegende Anforderungen von Live Share erfüllt.

- **Visual Studio Code 1.22.0 oder höher** – Windows 7, 8.1 oder 10, macOS *(nur Sierra 10.12 und höher)* , 64-Bit-Linux *(64-Bit-Ubuntu Desktop 16.04+, Fedora 27+ wird empfohlen – [siehe die Details](use/vscode.md#installation))* .
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


## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Freigeben Ihres ersten Projekts](quickstart/share.md)
- [Beitreten zu Ihrer ersten Sitzung](quickstart/join.md)

Gewusst wie

- [Zusammenarbeiten mithilfe von Visual Studio Code](use/vscode.md)
- [Zusammenarbeiten mithilfe von Visual Studio](use/vs.md)

Verweis

- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Unterstützung für Erweiterung](reference/extensions.md)
- [Anmerkungen zu dieser Version](https://aka.ms/vsls-releases)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

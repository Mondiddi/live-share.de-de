---
title: 'Freigeben von Visual Studio Live Share-schnellstartanleitung: | Microsoft-Dokumentation'
description: Eine gekürzte Exemplarische Vorgehensweise für das Freigeben Ihres ersten Projekts mithilfe einer zusammenarbeitssitzung für Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255846"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Schnellstart: Freigeben Sie Ihres ersten Projekts

> **Hinweis: Visual Studio Live Share ist derzeit als Vorschauversion verfügbar. Benutzeroberfläche und Features sind nicht endgültig.**

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können Ihr aktuelles Projekt sofort und sicher freigeben und anschließend nach Bedarf Debugsitzungen, Terminalinstanzen, Localhost-Web-Apps, Sprachanrufe und vieles mehr freigeben!

Sind Sie bereit?  Zusammenarbeit im Team muss also schnell und natürlicher, wird es schwieriger nicht dafür! Aus diesem Grund vereinfacht Visual Studio Live Share zu den ersten Schritten, damit Sie problemlos Freigeben Ihrer Arbeit und Ideen beginnen können.

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar in beiden Instanzen die gleiche Identität verwenden. Probieren Sie es aus!

Befolgen Sie die folgenden Schritte aus, um freizugeben.

## <a name="1-install-the-extension"></a>1. Installieren der Erweiterung

Die Installation der Erweiterung ist einfach. Halten Sie die folgenden Schritte aus:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Installieren Sie <a href="https://code.visualstudio.com/">Visual Studio Code</a> für Windows (7, 8.1 oder 10), macOS <b>(Sierra+)</b>, 64-Bit-Linux <b> (<a href="../use/vscode.md#installation">Details</a>)</b><br />
        2. Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter, und installieren Sie sie. <br />
        3. Laden Sie sie erneut, und warten Sie, dass die Abhängigkeiten heruntergeladen und installiert werden (siehe die Statusleiste).<br />
        4. <strong>Linux</strong>: Wenn Sie aufgefordert werden, <a href="../reference/linux.md#install-linux-prerequisites">Bibliotheken zu installieren</a>, klicken Sie auf „Installieren“, geben Sie das Kennwort ein, und starten Sie abschließend VS Code erneut.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 oder höher</strong><br />
        1. Installieren Sie die neueste Version von <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6+) unter Windows (7, 8.1 oder 10).<br/>
        2. Installieren Sie eine <a href="../reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)<br />
        3. Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter, und installieren Sie sie. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019</strong><br />
        1. Installieren Sie die neueste Vorschauversion von <a href="https://aka.ms/vs-preview">Visual Studio 2019</a>.<br/>
        2. Installieren Sie eine <a href="../reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)<br />
        3. Visual Studio Live Share wird mit diesen Workloads standardmäßig installiert. <br />
    </td>
</tr>
</table>

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

## <a name="2-sign-in"></a>2. Anmelden

Nach der Installation der Erweiterung Live Share sowie Neustarten und Warten von Abhängigkeiten, um die Installation (VS Code) abzuschließen, sollten Sie zur Anmeldung bei anderen Teilnehmer, die Informationen abrufen können. Klicken Sie einfach auf den Status "Live Share" (VS Code) Element / "Anmelden" die Schaltfläche (VS), um zu beginnen.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

In **VS Code**, Ihr Browser wird gestartet, während eine Benachrichtigung, starten Sie aufgefordert werden, melden Sie sich bei angezeigt wird. Schließen Sie des Anmeldevorgangs in Ihrem Browser ab, und dann schließen Sie einfach den Browser, wenn fertig.

![Toast-Benachrichtigung, die für die Anmeldung mit einem Webbrowser aufgefordert](../media/vscode-sign-in-toast.png)

> **Linux-Benutzer:** Sie möglicherweise aufgefordert, einen Benutzercode eingeben, wenn Sie eine ältere Version von Live Share verwenden (v0.3.295 oder niedriger). Aktualisieren Sie auf die neueste Version der Erweiterung, oder klicken Sie auf der "nicht schreiben?" Verknüpfen Sie nach dem anmelden, um den Code anzuzeigen. Finden Sie unter [hier, um Informationen](../use/vscode.md#sign-in-using-a-user-code).

In **Visual Studio**, verwendet Sie automatisch Live Share Ihr [personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Daher können Sie einfach melden Sie sich wie gewohnt. Wenn Sie eine andere Anmeldung als Ihr personalisierungskonto Visual Studio verwenden lieber, jedoch gehen Sie zu **Tools &gt; Optionen &gt; Live Share &gt; Benutzerkonto** , und wählen Sie andere Anmeldeinformationen.

Finden Sie unter [Problembehandlung](../troubleshooting.md#sign-in) Wenn weiterhin Probleme auftritt.

## <a name="3-open-a-folder-project-or-solution"></a>3. Öffnen Sie einen Ordner, Projekt oder Projektmappe

Verwenden Sie Ihren normalen Workflow um zu öffnen, einen Ordner, Projekt oder Projektmappe, die Sie in Visual Studio oder Visual Studio Code freigeben möchten.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Optional] Update ausgeblendet oder ausgeschlossenen Dateien

Standardmäßig werden Live Share **blendet** Dateien/Ordner, die in der gitignore-Dateien in die freigegebenen Ordner daran, Gäste. **Ausblenden von** eine Datei verhindert, dass es in der Dateistruktur des Gasts angezeigt werden. **Ausschließen von** wendet eine strengere Regel, die verhindert, dass Live Share öffnen, für den Gast in solchen Situationen Gehe zu Definition oder wenn Sie die Datei beim Debuggen oder gefolgt wird. "" schrittweise an eine Datei. Wenn Sie möchten die ausblenden/verschiedene Dateien ausschließen einer **. vsls.json** Datei kann dem Projekt mit diesen Einstellungen hinzugefügt werden. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

## <a name="5-start-a-collaboration-session"></a>5. Starten Sie eine zusammenarbeitssitzung

Als Nächstes klicken Sie einfach auf "Live Share" in Ihr Tool, und ein Link zur freigabeeinladung wird automatisch in die Zwischenablage kopiert.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Möglicherweise von Ihrem desktop-Firewall-Software werden Sie aufgefordert, ob der Live-Freigabe-Agent einen Port erstmalig öffnen, die Sie freigeben. Ist völlig optional, jedoch ermöglicht eine sichere "direct-Modus" akzeptieren diese zur Verbesserung der Leistung, wenn die Person, die mit dem Sie arbeiten im selben Netzwerk befindet, wie Sie sind. Finden Sie unter [Ändern des Verbindungsmodus](../reference/connectivity.md#changing-the-connection-mode) Details.

## <a name="6-optional-enable-read-only-mode"></a>6. [Optional] aktivieren nur-Lese Modus

Sobald Sie Ihre zusammenarbeitssitzung starten, können Sie die Sitzung, um zu verhindern, dass Gäste Bearbeitungen an den freigegebenen Code schreibgeschützt sein festlegen.

Nach der Freigabe erhalten Sie eine Benachrichtigung, dass der Link zur freigabeeinladung in die Zwischenablage kopiert wurde. Sie können dann die Option aus, um die Sitzung schreibgeschützt machen auswählen.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

In **VS Code**, Sie können auch eine nur-Lese Sitzung starten, von der Registerkarte "Live Share Viewlet".

![Toast-Benachrichtigung, die für die Anmeldung mit einem Webbrowser aufgefordert](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Senden Sie an andere Benutzer den Link zur freigabeeinladung

Senden den Link per E-mail, Slack, Skype usw., die Sie einladen möchten. Öffnen den Link in einem Browser, können sie der zusammenarbeitssitzung verknüpfen, die Freigabe wird der Inhalt der Ordner, Projekt oder Projektmappe, die Sie geöffnet. Beachten Sie, das mit der Ebene der Live-Freigabe zugreifen können Sitzungen für Gäste, bieten **sollten nur Freigabe für Personen, die Sie als vertrauenswürdig einstufen** und stellen Sie sich über die folgen, was Sie freigegeben haben.

> **Security Tip:** Möchten Sie die Auswirkungen auf die Sicherheit einiger Live Share-Funktionen zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

Wenn der Gast, Sie eingeladen Fragen haben, hat die [Schnellstart: Verknüpfen Sie Ihre erste Sitzung](join.md) Artikel enthält einige weitere Informationen zum Einrichten und Ausführen als Gast.

## <a name="8-optional-approve-the-guest"></a>8. [Optional] Genehmigen der Gast

Standardmäßig Gäste automatisch Ihre zusammenarbeitssitzung verknüpfen, und Sie werden benachrichtigt, wenn sie bereit sind, mit Ihnen zusammenarbeiten.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Sie können sich entscheiden, dass eine explizite "Genehmigung" für alle Benutzer stattdessen verknüpfen müssen. Wenn Sie diese Einstellung aktiviert haben, werden Sie von eine Benachrichtigung aufgefordert, das Gastbetriebssystem zu genehmigen, wenn sie versuchen, die die Sitzung beitreten.

Finden Sie unter [eine Gast-Genehmigung](../reference/security.md#requiring-guest-approval) ausführliche Informationen zu diesem Feature zu aktivieren.

## <a name="9-collaborate"></a>9. Arbeiten Sie zusammen!

Das ist alles! Hier sind einige Dinge zu testen, sobald ein Gastbetriebssystem, die Sie hinzugefügt wurde:

1. Bewegen Sie sich unabhängig voneinander in verschiedenen Dateien im Projekt, und nehmen Sie einige Änderungen vor
1. Führen Sie den Gast und beobachten Sie, wie sie einen Bildlauf durchführen, bearbeiten und navigieren Sie zu anderen Dateien
1. Starten Sie mit ihnen gemeinsam Debugsitzung
1. Freigeben von einem Server können Sie beispielsweise eine Web-app auf ihrem Computer ausgeführt wird überprüft
1. Teilen Sie einen Terminal, und führen Sie einige Befehle

Sehen Sie sich die [Visual Studio Code](../use/vscode.md) und [Visual Studio](../use/vs.md) Extension-Dokumentation Informationen dazu, wie Sie diese Aktionen und vieles mehr.

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich folgenden Artikel Weitere Informationen.

- [Schnellstart: Verknüpfen Sie Ihre erste zusammenarbeitssitzung](join.md)
- [Gewusst wie: Zusammenarbeiten Sie mithilfe von Visual Studio Code](../use/vscode.md)
- [Gewusst wie: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)

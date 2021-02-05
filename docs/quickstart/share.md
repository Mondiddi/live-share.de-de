---
title: Schnellstart zu „Freigeben“ | Microsoft-Dokumentation
description: Eine verkürzte Vorgehensweise zum Freigeben Ihres ersten Projekts in einer Visual Studio Live Share-Zusammenarbeitssitzung.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6422168bcb3d73a660ac90a415388ef1f29459d4
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870819"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Schnellstart: Freigeben Ihres ersten Projekts

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können Ihr aktuelles Projekt sofort und sicher freigeben und anschließend nach Bedarf Debugsitzungen, Terminalinstanzen, Localhost-Web-Apps, Sprachanrufe und vieles mehr freigeben!

Sind Sie bereit?  Die Zusammenarbeit im Team sollte so schnell und natürlich sein, dass es schwieriger wird, nicht so zu arbeiten! Deshalb erleichtert Visual Studio Live Share die ersten Schritte, damit Sie problemlos damit beginnen können, Ihre Arbeit und Ideen freizugeben.

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität in beiden Instanzen verwenden. Probieren Sie es aus!

Führen Sie einfach die folgenden Schritte aus, um mit der Freigabe zu beginnen.
<!--
Change the instructions to Install extension for VS Code and in-tool for VS?
-->
## <a name="1-install-the-extension"></a>1. Die Erweiterung installieren

Die Installation der Erweiterung ist einfach. Führen Sie folgende Schritte aus:

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019</strong><br />
        1.Installieren Sie <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Installieren Sie eine <a href="../reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++, Python und/oder Node.js)<br />
        3. Visual Studio Live Share wird mit diesen Workloads standardmäßig installiert. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 oder höher</strong><br />
        1. Installieren Sie die neueste Version von <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6+) unter Windows (7, 8.1 oder 10).<br/>
        2. Installieren Sie eine <a href="../reference/platform-support.md">unterstützte Workload</a>. (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)<br />
        3. Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter, und installieren Sie sie. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

## <a name="2-sign-in"></a>2. Anmelden

<!--
Re-write the grammar here- run on sentence does not make sense. Change screen shots. There is another way of signing in as well- what if a user goes directly to the start collaboration. 
-->
Nachdem Sie die Live Share-Erweiterung installiert, neu gestartet und gewartet haben, bis die Installation von Abhängigkeiten beendet ist (VS Code), möchten Sie sich nun anmelden, damit andere Teilnehmer wissen, wer Sie sind. Klicken Sie zuerst einfach auf das Statusleistenelement „Live Share“ (VS Code) / Schaltfläche „Anmelden“ (VS).

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

In **VS Code** wird Ihr Browser gestartet, während Sie eine eingeblendete Benachrichtigung zur Anmeldung auffordert. Schließen Sie den Anmeldevorgang in Ihrem Browser ab. Wenn Sie fertig sind, schließen Sie einfach den Browser.

![Popupbenachrichtigung mit der Aufforderung, sich über einen Webbrowser anzumelden](../media/vscode-sign-in-toast.png)

> **Linux-Benutzer:** Wenn Sie eine ältere Version von Live Share (v0.3.295 oder darunter) verwenden, werden Sie möglicherweise aufgefordert, einen Benutzercode einzugeben. Aktualisieren Sie auf die neueste Version der Erweiterung, oder klicken Sie nach Ihrer Anmeldung auf den Link „Gibt es Probleme?“, um den Code anzuzeigen. Lesen Sie [hier die Details dazu](../use/vscode.md#sign-in-using-a-user-code).

In **Visual Studio** verwendet Live Share automatisch Ihr [Personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Deshalb können Sie sich einfach wie gewohnt anmelden. Wenn Sie aber lieber eine andere Anmeldung als Ihr Visual Studio-Personalisierungskonto verwenden möchten, wechseln Sie zu **Tools &gt; Optionen &gt; Live Share &gt; Benutzerkonto**, und wählen Sie andere Anmeldeinformationen aus.

Sollten weiterhin Probleme auftreten, lesen Sie [Problembehandlung](../troubleshooting.md#sign-in).

## <a name="3-open-a-folder-project-or-solution"></a>3. Einen Ordner, ein Projekt oder eine Projektmappe öffnen

Verwenden Sie Ihren normalen Workflow zum Öffnen eines Ordners, eines Projekts oder einer Projektmappe, den/das/die Sie in Visual Studio oder Visual Studio Code freigeben möchten.

## <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Optional] Update ausgeblendet oder ausgeschlossene Dateien

In Live Share werden Dateien/Ordner, auf die in GITIGNORE-Dateien in Ihren freigegebenen Ordnern verwiesen wird, vor Gästen standardmäßig **ausgeblendet**. Durch **Ausblenden** einer Datei wird verhindert, dass sie in der Dateistruktur des Gasts angezeigt wird. Durch **Ausschließen** einer Datei wird eine striktere Regel angewendet. Sie verhindert, dass Live Share die Datei für den Gast öffnet – in Situationen wie „Gehe zu Definition“ oder wenn Sie während des Debuggens oder beim „gefolgt werden“ die Datei schrittweise ausführen. Wenn Sie unterschiedliche Dateien ausblenden/ausschließen möchten, kann eine **.vsls.json**-Datei Ihrem Projekt mit diesen Einstellungen hinzugefügt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

## <a name="5-start-a-collaboration-session"></a>5. Eine Zusammenarbeitssitzung starten

<!--
-->
Klicken Sie als Nächstes in Ihrem Tool einfach auf „Live Share“. Dann wird ein Einladungslink automatisch in Ihre Zwischenablage kopiert.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button-new.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Möglicherweise werden Sie von der Firewallsoftware Ihres Desktops gefragt, ob Sie zulassen möchten, dass der Live Share-Agent bei Ihrer ersten Freigabe einen Port öffnet. Dies zuzulassen, ist Ihnen völlig freigestellt, ermöglicht aber einen gesicherten „direkten Modus“ zur Leistungsverbesserung, wenn sich die Person, mit der Sie zusammenarbeiten, in demselben Netzwerk wie Sie befindet. Details dazu finden Sie unter [Ändern des Verbindungsmodus](../reference/connectivity.md#changing-the-connection-mode).

## <a name="6-optional-enable-read-only-mode"></a>6. [Optional] Den schreibgeschützten Modus aktivieren

Sobald Sie Ihre Zusammenarbeitssitzung gestartet haben, können Sie sie als schreibgeschützt festlegen und so verhindern, dass Gäste Änderungen am freigegebenen Code vornehmen.

Nach der Freigabe erhalten Sie eine Benachrichtigung mit der Information, dass der Einladungslink in Ihre Zwischenablage kopiert wurde. Dann können Sie die Option auswählen, dass die Sitzung schreibgeschützt werden soll.

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

Außerdem können Sie in **VS Code** eine schreibgeschützte Sitzung über die Viewlet-Registerkarte „Live Share“ starten.

![Popupbenachrichtigung mit der Aufforderung, sich über einen Webbrowser anzumelden](../media/vscode-read-only-viewlet.png)

## <a name="7-send-someone-the-invite-link"></a>7. Anderen Personen den Einladungslink senden

Senden Sie den Link per E-Mail, Slack, Skype usw. an die Personen, die Sie einladen möchten. Wenn die Empfänger den Link in einem Browser öffnen, können sie der Zusammenarbeitssitzung beitreten. Dort sind die Inhalte des Ordners, des Projekts oder der Projektmappe freigegeben, den/das/die Sie geöffnet haben. Bitte beachten Sie: Angesichts der Zugriffsebene, die Live Share-Sitzungen Gästen bereitstellen können, **sollten Sie Inhalte nur für vertrauenswürdige Personen freigeben** und die Folgen Ihrer Freigabe durchdenken.

> **Sicherheitstipp:** Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

Wenn der von Ihnen eingeladene Gast Fragen hat, enthält der Artikel [Schnellstart: Beitreten zu Ihrer ersten Sitzung](join.md) einige weitere Informationen zum Einrichten und Ausführen als Gast.

## <a name="8-optional-approve-the-guest"></a>8. [Optional] Den Gast genehmigen

Standardmäßig treten Gäste Ihrer Zusammenarbeitssitzung automatisch bei, und Sie werden benachrichtigt, wenn sie zur Zusammenarbeit mit Ihnen bereit sind.

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

Sie können auswählen, dass bei jeder beitretenden Person eine explizite „Genehmigung“ angefordert wird. Sollten Sie diese Einstellung aktiviert haben, werden Sie mit einer Benachrichtigung aufgefordert, den Gast zu genehmigen, wenn er Ihrer Sitzung beizutreten versucht.

Details dazu, wie dieses Feature aktiviert wird, finden Sie unter [Anfordern einer Gastgenehmigung](../reference/security.md#requiring-guest-approval).

## <a name="9-collaborate"></a>9. Arbeiten Sie zusammen!

Das ist alles! Hier sind ein paar Dinge zum Ausprobieren, sobald ein Gast Ihrer Sitzung beigetreten ist:

1. Wechseln Sie unabhängig voneinander zu verschiedenen Dateien im Projekt, und nehmen Sie einige Änderungen daran vor.
1. Folgen Sie dem Gast, und beobachten Sie, wie er scrollt, Änderungen vornimmt und zu verschiedenen Dateien navigiert.
1. Starten Sie eine gemeinsame Debugsitzung mit ihm.
1. Geben Sie einen Server frei, damit Sie etwas überprüfen können, z.B. eine Web-App, die auf dem Computer des Gasts ausgeführt wird.
1. Geben Sie ein Terminal frei, und führen Sie einige Befehle aus.

Informationen, wie diese Aktionen ausgeführt werden, und vieles mehr finden Sie in der Erweiterungsdokumentation zu [Visual Studio Code](../use/vscode.md) und [Visual Studio](../use/vs.md).

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie weitere Informationen benötigen, sehen Sie sich diese zusätzlichen Artikel an.

- [Schnellstart: Beitreten zu Ihrer ersten Zusammenarbeitssitzung](join.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)

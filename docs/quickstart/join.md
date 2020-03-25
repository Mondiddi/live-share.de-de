---
title: Schnellstart zu „Beitreten“ – Visual Studio Live Share | Microsoft-Dokumentation
description: Eine verkürzte Vorgehensweise zum Beitreten zu Ihrer ersten Visual Studio Live Share-Zusammenarbeitssitzung.
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
ms.openlocfilehash: 7b8b3d9b566231f4b4205b559232ef1752fd9441
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79508571"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->


# <a name="quickstart-join-your-first-collaboration-session"></a>Schnellstart: Beitreten zu Ihrer ersten Zusammenarbeitssitzung

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. So können Sie dem aktuellen Projekt eines Teamkollegen sofort und sicher beitreten und anschließend nach Bedarf an Debugsitzungen teilnehmen, Terminalinstanzen anzeigen und bearbeiten, Localhost-Web-Apps anzeigen, an Sprachanrufen teilnehmen und vieles mehr!

Sind Sie bereit? Die Zusammenarbeit im Team sollte so schnell und natürlich sein, dass es schwieriger wird, nicht so zu arbeiten! Deshalb erleichtert Visual Studio Live Share die ersten Schritte, damit Sie problemlos damit beginnen können, Ihre Arbeit und Ideen freizugeben.

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

Führen Sie die folgenden Schritte aus, um einer Zusammenarbeitssitzung beizutreten.

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [Optional] In VS Code schreibgeschützt beitreten

In VS Code können Sie nach Installation der Live Share-Erweiterung, dem Neustart und dem Warten, bis die Installation beendet ist, gleich loslegen und einer Zusammenarbeitssitzung schreibgeschützt beitreten.

> [!NOTE]
> Wenn Sie an dem Code, dem Sie folgen, Änderungen vornehmen möchten, müssen Sie sich anmelden.

Öffnen Sie den Einladungslink in einem Browser (oder öffnen Sie ihn erneut darin). Dann erhalten Sie eine Benachrichtigung, dass der Browser VS Code starten möchte. Lassen Sie den Start zu, und er beginnt, Sie mit der Zusammenarbeitssitzung zu verbinden.

Beim Starten von VS Code wird eine Popupbenachrichtigung angezeigt, die Sie zur Anmeldung auffordert. Wählen Sie „Schreibgeschützt weiter“ aus, um der Sitzung beizutreten.

![Popup „Einer Sitzung schreibgeschützt beitreten“](../media/vscode-read-only-guest.png)

Sie werden zur Eingabe eines Anzeigenamens aufgefordert, damit Teilnehmer an der Sitzung Sie identifizieren können.

![Schreibgeschützter Name](../media/vscode-read-only-guest-name.png)

Danach erfolgt Ihr schreibgeschützter Beitritt zur Sitzung. Sie können den Code anzeigen und darin navigieren, ihn gemeinsam debuggen sowie freigegebene Server und Terminals (schreibgeschützt) anzeigen.

> [!NOTE]
> Wenn Sie später Lese-/Schreibzugriff auf den Code erhalten möchten, können Sie sich anmelden. Klicken Sie in der Statusleiste auf Ihren Anzeigenamen, und wählen Sie die Option „Anmelden“ aus.
![Schreibgeschützte Anmeldung](../media/vscode-read-only-guest-signin.png) Damit wird Ihr Browser gestartet, und Sie können für Ihre Anmeldung ein Microsoft- oder GitHub-Konto auswählen.

## <a name="3-sign-in"></a>3. Anmelden

Nachdem Sie die Live Share-Erweiterung installiert, neu gestartet und gewartet haben, bis die Installation von Abhängigkeiten beendet ist (VS Code), möchten Sie sich nun anmelden, damit andere Teilnehmer wissen, wer Sie sind. Wenn Sie diesen Schritt überspringen, werden Sie während des Beitrittsprozesses zur Anmeldung aufgefordert, oder Sie können der Sitzung schreibgeschützt beitreten. Klicken Sie zunächst auf das Statusleistenelement „Live Share“ (VS Code) > Schaltfläche „Anmelden“ (VS).

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item" />
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

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Den Einladungslink in einem Browser öffnen/erneut öffnen

Öffnen Sie jetzt den Einladungslink in einem Browser (oder öffnen Sie ihn erneut darin).

> **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, werden Ihnen Links zum Extension Marketplace angezeigt. Installieren Sie die Erweiterung, starten Sie ihr Tool neu, und wiederholen Sie den Vorgang.

Sie sollten benachrichtigt werden, dass der Browser ein Live Share-fähiges Tool starten möchte. Wenn Sie zulassen, dass er Ihr ausgewähltes Tool startet, werden Sie gleich nach dem Start mit der Zusammenarbeitssitzung verbunden.

![Seite „Beitreten“](../media/join-page.png)

Wenn der Gastgeber offline ist, werden Sie an diesem Punkt entsprechend benachrichtigt. Dann können Sie Kontakt mit dem Gastgeber aufnehmen und ihn um erneute Freigabe bitten.

> **Tipp zur Problembehandlung:** Sorgen Sie bei Verwendung von VS Code dafür, dass Sie **das Tool mindestens einmal gestartet haben**, nachdem Sie die Erweiterung installiert und gewartet haben, bis die Installation von Abhängigkeiten beendet ist (siehe die Statusleiste), bevor Sie die Seite „Einladen“ öffnen/erneut öffnen. Noch immer Probleme? Details finden Sie unter [Manuelles Beitreten](../reference/manual-join.md).

## <a name="5-collaborate"></a>5. Arbeiten Sie zusammen!

Das ist alles! Innerhalb kurzer Zeit werden Sie mit der Zusammenarbeitssitzung Ihres Kollegen verbunden. Standardmäßig akzeptiert der Gastgeber automatisch Personen, die beitreten. Wenn er aber [Gastgenehmigung erforderlich](../reference/security.md#requiring-guest-approval) eingerichtet hat, wird Ihnen in der Statusleiste/im Dialogfeld „Beitreten“ angezeigt, dass Live Share darauf wartet, dass der Gastgeber Ihre Beitrittsanforderung genehmigt.

> **Sicherheitstipp:** Als Gast, der einer Zusammenarbeitssitzung beitritt, ist es wichtig zu verstehen, dass Gastgeber Ihren Zugriff auf bestimmte Dateien oder Features einschränken können. Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features und -Einstellungen verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

Hier sind ein paar Dinge zum Ausprobieren:

1. Wechseln Sie unabhängig voneinander durch das Projekt, und nehmen Sie einige Änderungen daran vor.
2. Sehen Sie sich IntelliSense für JavaScript, TypeScript und/oder C#-Code bei der Arbeit an.
3. Bearbeiten Sie etwas zusammen mit dem Gastgeber.
4. Folgen Sie dem Gastgeber und bewegen Sie sich mit ihm, während er navigiert und Änderungen in verschiedenen Dateien vornimmt.
5. Starten Sie eine gemeinsame Debugsitzung mit dem Gastgeber.
6. Bitten Sie den Gastgeber um die Freigabe eines Servers, damit Sie etwas überprüfen können, z.B. eine Web-App, die auf dessen Computer ausgeführt wird.
7. Bitten Sie den Gastgeber um die Freigabe eines Terminals, und führen Sie einige Befehle aus.

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie weitere Informationen benötigen, sehen Sie sich diese zusätzlichen Artikel an.

- [Schnellstart: Freigeben Ihres ersten Projekts](share.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)

---
title: Join-Schnellstart – Visual Studio Live Share | Microsoft-Dokumentation
description: Eine gekürzte Exemplarische Vorgehensweise zum Verknüpfen Ihre erste Visual Studio Live Share zusammenarbeitssitzung.
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
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256069"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Schnellstart: Verknüpfen Sie Ihre erste zusammenarbeitssitzung

> **Hinweis: Visual Studio Live Share ist derzeit als Vorschauversion verfügbar. Benutzeroberfläche und Features sind nicht endgültig.**

Willkommen bei Visual Studio Live Share! Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können Sie sofort und sicherer Beitritt einem Teamkollegen des aktuellen Projekts, und zeigen Sie dann bei Bedarf geben Sie in Debugsitzungen erhalten, und bearbeiten die terminal-Instanzen finden Sie unter "localhost"-Web-apps, Join-Sprachanrufe und mehr!

Sind Sie bereit? Zusammenarbeit im Team muss also schnell und natürlicher, wird es schwieriger nicht dafür! Aus diesem Grund vereinfacht Visual Studio Live Share zu den ersten Schritten, damit Sie problemlos Freigeben Ihrer Arbeit und Ideen beginnen können.

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

Befolgen Sie diese Schritte aus, um eine zusammenarbeitssitzung zu verknüpfen.

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [Optional] Join als nur-Lese Gast in Visual Studio Code

In VS Code nach der Installation der Erweiterung Live Share sowie Neustarten und Warten von Abhängigkeiten, vollständig installiert wird können Sie richtig einsteigen und beitreten zu einer zusammenarbeitssitzung als nur-Lese Gast.

> [!NOTE]
> Wenn Sie Änderungen am Code vorzunehmen sind Sie verknüpfen möchten, müssen Sie zum [Anmeldung](../quickstart/join.md#3-Sign-in).

Der Link zur freigabeeinladung in einem Browser öffnen (oder erneut zu öffnen), und Sie erhalten eine Benachrichtigung, dass möchte, dass der Browser Starten von VS Code. Lassen Sie ihn starten, und beginnen sie mit der zusammenarbeitssitzung.

Wenn Visual Studio Code gestartet wird, erhalten Sie eine Toast-Benachrichtigung, die zur Anmeldung aufgefordert. Wählen Sie "Weiter als nur-Lese Gast", die der Sitzung beizutreten.

![Verknüpfen Sie als Sitzung als ein nur-Lese Gast-Popup](../media/vscode-read-only-guest.png)

Sie werden aufgefordert, geben Sie einen Anzeigenamen ein, die Teilnehmer, die Sie in der Sitzung identifiziert werden können.

![Nur-Lese Gastname](../media/vscode-read-only-guest-name.png)

Sie werden anschließend in die Sitzung im schreibgeschützten Modus angehören. Sie werden zum Anzeigen und den Code, Co Debuggen, und Server anzeigen, die freigegeben und Terminals (schreibgeschützt) navigieren.

> [!NOTE]
> Wenn Sie Lese-/Schreibzugriff auf den Code später abrufen möchten, können Sie sich anmelden. Klicken Sie auf Ihren Anzeigenamen des Status, Balken, und wählen Sie die Option "Anmelden".
![Melden Sie sich nur-Lese Gast](../media/vscode-read-only-guest-signin.png) Hierdurch wird Ihr Browser, und Sie können eine Microsoft- oder GitHub-Konto für die Anmeldung auswählen.

## <a name="3-sign-in"></a>3. Anmelden

Nach der Installation der Erweiterung Live Share sowie Neustarten und Warten von Abhängigkeiten, um die Installation (VS Code) abzuschließen, sollten Sie zur Anmeldung bei anderen Teilnehmer, die Informationen abrufen können. Wenn Sie diesen Schritt überspringen, Sie werden aufgefordert, für die Anmeldung bei der Verknüpfung oder können die Sitzung als nur-Lese Gast verknüpfen. Klicken Sie auf den Status "Share" (VS Code) Element / "Anmelden" die Schaltfläche (VS), um zu beginnen.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

In **VS Code**, Ihr Browser wird gestartet, während eine Benachrichtigung, starten Sie aufgefordert werden, melden Sie sich bei angezeigt wird. Schließen Sie des Anmeldevorgangs in Ihrem Browser ab, und dann schließen Sie einfach den Browser, wenn fertig.

![Toast-Benachrichtigung, die für die Anmeldung mit einem Webbrowser aufgefordert](../media/vscode-sign-in-toast.png)

> **Linux-Benutzer:** Sie möglicherweise aufgefordert, einen Benutzercode eingeben, wenn Sie eine ältere Version von Live Share verwenden (v0.3.295 oder niedriger). Aktualisieren Sie auf die neueste Version der Erweiterung, oder klicken Sie auf der "nicht schreiben?" Verknüpfen Sie nach dem anmelden, um den Code anzuzeigen. Finden Sie unter [hier, um Informationen](../use/vscode.md#sign-in-using-a-user-code).

In **Visual Studio**, verwendet Sie automatisch Live Share Ihr [personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Daher können Sie einfach melden Sie sich wie gewohnt. Wenn Sie eine andere Anmeldung als Ihr personalisierungskonto Visual Studio verwenden möchten, jedoch gehen Sie zu **Tools &gt; Optionen &gt; Live Share &gt; Benutzerkonto** , und wählen Sie andere Anmeldeinformationen.

Finden Sie unter [Problembehandlung](../troubleshooting.md#sign-in) Wenn weiterhin Probleme auftritt.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Open/erneute-open die INVITE-Nachricht in einem Browser zu verknüpfen.

Der Link zur freigabeeinladung in einem Browser, öffnen Sie einfach (oder erneut zu öffnen Sie).

> **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, wird mit Links zu den Extension Marketplace angezeigt. Installieren Sie die Erweiterung, und starten Sie das Tool, und wiederholen Sie.

Sie sollten eine Benachrichtigung über möchte, dass der Browser eine aktivierte Freigabe für die Live-Tool zu starten. Wenn Sie es in das ausgewählte Tool starten können, müssen Sie mit der zusammenarbeitssitzung Start verbunden sein.

![Verknüpfen Sie die Seite](../media/join-page.png)

Wenn der Host offline ist, werden Sie an diesem Punkt stattdessen benachrichtigt werden. Sie können dann wenden Sie sich an den Host und bitten Sie ihn erneut freigeben.

> **Problembehandlungstipp:** Wenn Sie Visual Studio Code verwenden, werden Sie sicher, dass Sie haben **das Tool mindestens einmal gestartet** nach Installation der Erweiterung und für die Abhängigkeiten der Installation gewartet hat (Siehe Statusleiste) vor der öffnenden/erneute-opening der Seite "einladen". Immer noch Probleme? Finden Sie unter [Manuelles Verknüpfen von](../reference/manual-join.md) Details.

## <a name="5-collaborate"></a>5. Arbeiten Sie zusammen!

Das ist alles! In einigen Augenblicken werden Sie mit Ihres Kollegen zusammenarbeitssitzung verbunden sein. In der Standardeinstellung der Host automatisch akzeptiert Personen, die verknüpfen, aber wenn der Host bis zu festgelegt ist, [Gast Genehmigung](../reference/security.md#requiring-guest-approval) Sie finden Sie in der Statusleiste / join Dialogfeld muss erwähnt werden, die darauf Live Share auf dem Host warten hinzufügen und Sie genehmigt werden.

> **Security Tip:** Als Gast beitreten zu einer zusammenarbeitssitzung ist es wichtig zu verstehen, dass die Hosts den Zugriff auf bestimmte Dateien oder Funktionen beschränkt werden können. Möchten Sie die Auswirkungen auf die Sicherheit einiger Features und Einstellungen Live Share zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

Es gibt einige Dinge zum Testen zur Verfügung:

1. Das Projekt wird verschieben Sie unabhängig voneinander, und nehmen Sie einige Änderungen vor
2. Sehen Sie sich funktionierende Intellisense für JavaScript, TypeScript, und/oder C# Code
3. Bearbeiten Sie etwas zusammen mit dem host
4. Führen Sie den Host aus, und verschieben mit ihnen navigieren und bearbeiten Sie in verschiedenen Dateien
5. Einrichten einer Co-debugging-Sitzung mit dem Host starten
6. Bitten Sie den Host auf einen Server freigeben, können Sie beispielsweise eine Web-app auf ihrem Computer ausgeführt wird überprüft
7. Bitten Sie den Host Teilen einen Terminal, und führen einige Befehle

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich folgenden Artikel Weitere Informationen.

- [Schnellstart: Freigeben Sie Ihres ersten Projekts](share.md)
- [Gewusst wie: Zusammenarbeiten Sie mithilfe von Visual Studio Code](../use/vscode.md)
- [Gewusst wie: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)

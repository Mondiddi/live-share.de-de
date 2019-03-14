---
title: Zusammenarbeiten mithilfe von Visual Studio Code – Visual Studio Live Share | Microsoft-Dokumentation
description: Ein Satz von Zusammenarbeit-Vorgehensweisen für Visual Studio Code und Live Share.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255965"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Gewusst wie: Zusammenarbeiten Sie mithilfe von Visual Studio Code

Möchten Sie mit Live Share in Visual Studio Code zusammenarbeiten zu erhalten?  Wenn dies der Fall ist, können Sie in die richtige Stelle. In diesem Artikel werden Sie einige der spezifischen Funktionen in Visual Studio Live Share-Erweiterung für Visual Studio Code zu verwenden wie erläutert.

Beachten Sie, dass alle hier beschriebene Aktivitäten in der Zusammenarbeit eine einzelne umfassen **Zusammenarbeit Sitzungshost** und einem oder mehreren **Gäste**. Der Gastgeber ist die Person, die die Zusammenarbeitssitzung gestartet hat, und jede Person, die ihr beitritt, ist ein Gast.

*Suchen Sie eine Zusammenfassung der gekürzte? Sehen Sie sich die [freigeben](../quickstart/share.md) oder [Join](../quickstart/join.md) Schnellstarts stattdessen.*

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar in beiden Instanzen die gleiche Identität verwenden. Probieren Sie es aus!

## <a name="installation"></a>Installation

Bevor Sie beginnen, müssen Sie unbedingt haben Sie eine Version von Visual Studio Code installiert, die Live Share-Core-Anforderungen erfüllt. Sie müssen **Visual Studio Code (1.22.0 oder höher)** unter:

- **Windows**: 7, 8.1 oder 10

- **macOS**: Sierra (10.12) und höher nur.
    - _El Capitan (10.11) und im folgenden werden derzeit nicht unterstützt aufgrund von [.NET Core 2.0-Anforderungen](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux**: 64-bit Ubuntu Desktop 16.04+, Fedora Workstation 27+, CentOS 7

    - Livefreigabe erfordert eine Reihe von [Linux-Voraussetzungen](#linux-install-steps) Sie möglicherweise aufgefordert, zu installieren.
    - _32-Bit-Linux wird nicht unterstützt, da [.NET Core 2.0-Anforderungen](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM wird auch derzeit nicht unterstützt.
    - Finden Sie unter den [Linux Installationsdetails](../reference/linux.md) finden Sie Details zur Verwendung von Nachgeschalteter und anderen Distributionen.

Danach ist das Herunterladen und Installieren der Visual Studio Live Share-Erweiterung kinderleicht:

1. Installieren Sie <a href="https://code.visualstudio.com/">Visual Studio-Code</a>
2. [Herunterladen](https://aka.ms/vsls-dl/vscode) und Installieren der Visual Studio Live Share-Erweiterung über den Marketplace.
3. Laden Sie Visual Studio-Code
4. Warten Sie Abhängigkeiten herunterladen und installieren (Siehe Statusleiste) aus.<br/>
    ![Abschließen der Installation](../media/vscode-finishing-install.png)
5. **Linux**: Wenn Sie eine Benachrichtigung zum Installieren der fehlenden Bibliotheken finden Sie unter:
    1. Klicken Sie auf "Installieren", in der Benachrichtigung.
    2. Geben Sie nach Aufforderung Ihr Administratorkennwort ("sudo").
    3. Starten Sie Vscode anschließend neu.

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

[![Herunterladen](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Schritte für Linux-Installation

Linux kann ist eine stark variieren und mit der schieren Anzahl von desktop-Umgebungen und Verteilungen schwierig zu arbeiten. Wenn Sie an die unterstützten Versionen von halte **Ubuntu Desktop** (16.04 und höher) oder **Fedora Arbeitsstation** (27 und höher), **CentOS 7** nur **offizielle Distributionen von Visual Studio Code**, sollten Sie den Prozess einfach finden. Jedoch den Fall, dass Sie eine nicht standardmäßige Konfiguration oder ein downstream-Verteilung verwenden, können oder nicht einige Unterbrechungen auftreten können. Finden Sie unter [Details zur Installation von Linux](../reference/linux.md) für Weitere Informationen.

#### <a name="install-linux-prerequisites"></a>Installieren des Linux-Voraussetzungen

Einige Linux-Distributionen fehlen Bibliotheken, die Live Share benötigt. Live Share versucht standardmäßig, erkennen und Linux-Voraussetzungen für die Sie installieren. Sie sehen eine Toast-Benachrichtigung, wenn es sich bei Live Share ein Problem auftritt, die aus fehlenden Bibliotheken stellen Ihnen die Berechtigung, diese zu installieren stammen können.

![Toast-Benachrichtigung mit der Nachricht, die diese Linux-Voraussetzungen fehlen.](../media/vscode-linux-prereq-missing.png)

Wenn Sie auf "Installieren" klicken, wird ein terminal-Fenster angezeigt, in dem Sie Ihr Administratorkennwort ("sudo"), um den Vorgang fortzusetzen, geben Sie ein müssen. Vorausgesetzt, dass der Vorgang erfolgreich abgeschlossen wurde, neu starten Sie, Visual Studio-Code, die Sie für alle festgelegt werden soll. Sie sollten außerdem sehen Sie sich **[Tipps, die von der Verteilung von](../reference/linux.md#tips-by-distribution)** für andere Tipps und problemumgehungen, sofern vorhanden.

Wenn Sie sehen eine Meldung an, das Skript nicht Ihre Distribution unterstützt, finden Sie unter **[Tipps für die Community unterstützt Verteilungen](../reference/linux.md#tips-for-community-supported-distros)** Informationen die Community hat für uns freigegeben.

Wenn Sie **bevorzugen Sie nicht möchten, dass Visual Studio Code, führen Sie den Befehl für Sie**, Sie können auch entscheiden, um die neueste Version dieses Skripts zu einem beliebigen Zeitpunkt manuell erneut ausführen, indem den folgenden Befehl in einem Terminalfenster ausführen:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Linux-Browser-integration

Freigeben von Visual Studio Live in der Regel **erfordert keine zusätzliche Installationsschritte** Browserintegration unter Linux zu aktivieren.

Zeit, die häufig in bestimmten Distributionen Sie **möglicherweise benachrichtigt, dass Ihr Administratorkennwort ("sudo") erforderlich ist** um die Installation abzuschließen. Ein terminal-Fenster wird angezeigt, in dem das Browser-Startprogramm installiert wird angezeigt. Geben Sie einfach nach Aufforderung Ihr Kennwort ein, und drücken Sie die EINGABETASTE nach Abschluss der Installation, um die terminal-Fenster zu schließen.

Erhalten Sie weitere Informationen zu warum dies erforderlich ist und das Weiterleiten von Live werden Dateien abgelegt  **[hier](../reference/linux.md#linux-browser-integration)**. Beachten Sie, auch wenn Sie nicht damit Browser Integration funktioniert Sie können weiterhin  **[Manuelles Verknüpfen von zusammenarbeitssitzungen](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Anmelden

Um zusammenarbeiten können, müssen Sie Visual Studio Live Share anmelden, damit jeder weiß, wer Sie sind. Dies ist nur eine Sicherheitsmaßnahme und **nicht** vorschaubuilds, dass Sie alle Marketing oder andere Research-Aktivitäten. Sie können mit einem persönlichen Microsoft-Konto anmelden (z. B. @outlook.com), Microsoft gestützte Geschäfts- oder schulkonto (AAD) oder ein GitHub-Konto. Anmeldung ist einfach.

**Klicken Sie auf** auf die "Share" Statusleiste Element, oder drücken Sie **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** , und wählen Sie die "Live-Freigabe: Melden Sie sich mit Browser"-Befehl.

![VS Code-Anmeldung auf die Schaltfläche](../media/vscode-sign-in-button.png)

Eine Benachrichtigung werden Sie aufgefordert werden, melden Sie sich mit Ihrem Webbrowser angezeigt. Klicken Sie auf "Start anmelden" öffnet einen Browser für die Sie verwenden, um die Anmeldung abzuschließen. Schließen Sie einfach den Browser, wenn fertig.

![Toast-Benachrichtigung, die für die Anmeldung mit einem Webbrowser aufgefordert](../media/vscode-sign-in-toast.png)

> **Linux-Benutzer:** Sie möglicherweise aufgefordert, einen Benutzercode eingeben, wenn Sie eine ältere Version von Live Share verwenden (v0.3.295 oder niedriger). Aktualisieren Sie auf die neueste Version der Erweiterung, oder klicken Sie auf der "nicht schreiben?" Verknüpfen Sie nach dem anmelden, um den Code anzuzeigen. Finden Sie unter [unten Details](#sign-in-using-a-user-code).

Wenn Visual Studio Code nach dem Durcharbeiten der Anmeldevorgang im Browser nicht um Ihre Anmeldung übernommen werden, finden Sie unter [melden Sie sich mit einem Benutzercode](#sign-in-using-a-user-code). Sehen Sie sich andernfalls [Problembehandlung](../troubleshooting.md#sign-in) Weitere Tipps.

### <a name="sign-in-using-a-user-code"></a>Melden Sie sich mit einem Benutzercode

Wenn Sie Probleme mit Visual Studio Code ausführen, nicht um eine vollständige Anmeldung auswählen, können Sie stattdessen einen "User Code" eingeben.

1. Drücken Sie **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** , und führen Sie die "Live-Freigabe: Melden Sie sich mit den Benutzercode"-Befehl.

2. Ein Browser sollte angezeigt werden, für die Sie verwenden, um die Anmeldung abzuschließen.

    > [!NOTE]
    > Wenn ein Browser nicht automatisch angezeigt wird, öffnen Sie [hier](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) in einen Browser, und melden Sie sich.

3. Sobald Sie fertig sind, klicken Sie auf "Probleme? Klicken Sie hier, um Anweisungen für Benutzer-Code"den Benutzercode angezeigt.

    ![Bild des Benutzercodes im browser](../media/vscode-user-code-browser.png)

4. Kopieren Sie den Benutzercode.

5. Abschließend fügen Sie den Benutzercode, in das Eingabefeld ein, das angezeigt wurden, wenn Sie den Befehl ausgeführt, und drücken Sie die EINGABETASTE, um die Anmeldung abzuschließen.

    ![Bild des Eingabefelds für Benutzer-code](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Verwenden die Live Share viewlet

Nach der Installation von Visual Studio Live Share, wird der Aktivitätsleiste von VS Code eine benutzerdefinierte Registerkarte hinzugefügt werden. Auf dieser Registerkarte können Sie die alle Live Share-Funktionen für die Zusammenarbeit zugreifen. Wenn Sie freigeben oder beitreten zu einer zusammenarbeitssitzung, wird eine Ansicht darüber hinaus auch auf der Registerkarte "Explorer" für all diese Funktionen den Zugriff auf angezeigt.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Mit diesen Ansichten können Sie den Teilnehmer im freigegebenen Code sehen, klicken Sie auf einen Teilnehmer zu befolgen, Teilnehmer zu konzentrieren, Zugriff auf gemeinsam genutzte Server Terminals und vieles mehr.

## <a name="using-the-scoped-command-menu"></a>Verwenden das Befehlsmenü für diesen Bereich

Darüber hinaus sind alle Funktionen von Visual Studio Live Share verfügbar ist, aus der Visual Studio Code "Befehlspalette", auf die zugegriffen werden kann, durch Drücken von STRG + UMSCHALT + P / Cmd + UMSCHALT + P oder F1. Sie finden eine vollständige Liste der Befehle, geben Sie "live Share".

Da diese Liste lang werden kann, finden Sie es möglicherweise einfacher, eine Bereichsbezogene Befehlsmenü zur Verfügung, in der Statusleiste zu nutzen. Klicken auf der Anmeldeseite / Sitzung Statussymbol auf der Statusleiste daraufhin sofort eine kontextabhängige Liste der Befehle, die für die Verwendung verfügbar sind.

![Symbol für Visual Studio Code-Sitzung-Status](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Projekt freigeben

Nach dem Herunterladen und Installieren von Visual Studio Live Share, befolgen Sie diese Schritte zum Starten einer zusammenarbeitssitzung und einladen von Kollegen mit Ihnen zusammenarbeiten.

1. **Anmelden**

    Nach dem Live Share-Erweiterung installieren, das erneute Laden, und Warten von Abhängigkeiten, um die Installation abzuschließen, sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Öffnen Sie einen Ordner**

    Verwenden Sie Ihren normalen Workflow um zu öffnen, einen Ordner, Projekt oder Projektmappe, die Sie für die Gäste freigeben möchten.

3. **[Optional] Ausgeblendete oder ausgeschlossene Dateien aktualisieren**

    Standardmäßig werden Live Share **blendet** Dateien/Ordner, die in der gitignore-Dateien in die freigegebenen Ordner daran, Gäste. **Ausblenden von** eine Datei verhindert, dass es in der Dateistruktur des Gasts angezeigt werden. **Ausschließen von** wendet eine strengere Regel, die verhindern Live Share öffnen es für den Gast in Situationen, wie für die Definition einer wechseln oder wenn Sie die Datei beim Debuggen oder gefolgt wird. "" schrittweise an eine Datei. Wenn Sie möchten die ausblenden/verschiedene Dateien ausschließen einer **. vsls.json** Datei kann dem Projekt mit diesen Einstellungen hinzugefügt werden. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

4. **Starten Sie eine zusammenarbeitssitzung**

    Jetzt einfach **klicken Sie auf** die "Share" Statusleiste Element oder Treffer **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** , und wählen Sie "-Livefreigabe: Starten Sie eine zusammenarbeitssitzung (Freigabe) ".

    ![Schaltfläche "freigeben"](../media/vscode-share-button.png)

    > [!NOTE]
    > Möglicherweise von Ihrem desktop-Firewall-Software werden Sie aufgefordert, ob der Live-Freigabe-Agent einen Port erstmalig öffnen, die Sie freigeben. Ist völlig optional, jedoch ermöglicht eine sichere "direct-Modus" akzeptieren diese zur Verbesserung der Leistung, wenn die Person, die mit dem Sie arbeiten im selben Netzwerk befindet, wie Sie sind. Finden Sie unter [ändern den Verbindungsmodus](../reference/connectivity.md#changing-the-connection-mode) Details.

    Ein Link zur freigabeeinladung werden automatisch in die Zwischenablage kopiert werden. Wenn in einem Browser geöffnet wird, können in diesen Link, andere Benutzer, eine neue zusammenarbeitssitzung beizutreten, die Inhalte dieser Ordner für sie freigegeben hat.

    Den Übergang "Share" Status-Leiste Element zur Darstellung des Sitzungszustands wird ebenfalls angezeigt. Finden Sie unter [Sitzungszustand](#session-states) Informationen weiter unten aus, wie dies aussieht.

    Beachten Sie, dass, wenn Sie den Link zur freigabeeinladung abrufen müssen erneut, nachdem Sie begonnen haben, Freigabe, Sie erneut darauf zugreifen durch Klicken auf das Statusleistensymbol für Sitzung Zustand und wählen Sie "Einladen (Link kopieren)".

5. **[Optional] Nur-Lese Modus aktivieren**

    Sobald Sie Ihre zusammenarbeitssitzung starten, können Sie die Sitzung, um zu verhindern, dass Gäste Bearbeitungen an den freigegebenen Code schreibgeschützt sein festlegen.

    Nach der Freigabe erhalten Sie eine Benachrichtigung, dass der Link zur freigabeeinladung in die Zwischenablage kopiert wurde. Sie können dann die Option aus, um die Sitzung schreibgeschützt machen auswählen.

    ![VS Code nur-Lese Modus](../media/vscode-read-only-toast.png)

6. **Senden Sie an andere Benutzer den link**

    Senden den Link per E-mail, Slack, Skype usw., die Sie einladen möchten. Beachten Sie, das mit der Ebene der Live-Freigabe zugreifen können Sitzungen für Gäste, bieten **sollten nur Freigabe für Personen, die Sie als vertrauenswürdig einstufen** und stellen Sie sich über die folgen, was Sie freigegeben haben.

    > **Security Tip:** Möchten Sie die Auswirkungen auf die Sicherheit einiger Live Share-Funktionen zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

    Wenn der Gast, Sie eingeladen Fragen haben, wurde die "[Schnellstart: Verknüpfen Sie Ihre erste Sitzung](../quickstart/join.md)"Artikel enthält einige weitere Informationen zu einrichten und als Gast ausgeführt wird.

7. **[Optional] Den Gast genehmigen**

    Standardmäßig Gäste werden automatisch Ihre zusammenarbeitssitzung verknüpfen, und Sie werden benachrichtigt, wenn sie bereit sind, mit Ihnen zusammenarbeiten. Während dieser Benachrichtigung Sie sie aus der Sitzung entfernen kann, können Sie auch entscheiden, dass stattdessen eine explizite "Genehmigung" für alle Benutzer verknüpfen müssen.

    Um dieses Feature zu aktivieren, fügen Sie einfach Folgendes auf "Settings.JSON":

         "liveshare.guestApprovalRequired": true

    Nachdem Sie diese Einstellung aktiviert haben, fordert eine Benachrichtigung Sie auf den Gast zu genehmigen, bevor sie hinzugefügt werden können.

    ![Visual Studio Code-Join-genehmigungsanforderung](../media/vscode-join-approval.png)

    Finden Sie unter [Einladungen und Join-Zugriff](../reference/security.md#invitations-and-join-access) Weitere Informationen zu Überlegungen zur Sicherheit der Einladung.

Das wars!!

### <a name="stop-the-collaboration-session"></a>Beenden Sie die zusammenarbeitssitzung

Als Host und können vollständig Freigabe beenden und der zusammenarbeitssitzung zu einem beliebigen Zeitpunkt von der Live Share-Ansicht wird geöffnet, in der Explorer oder in der benutzerdefinierten Live Share-Registerkarte, und wählen das Symbol "Beenden zusammenarbeitssitzung" enden.

![Beenden der zusammenarbeitssitzung](../media/vscode-end-collaboration-viewlet.png)

Alle Gäste werden benachrichtigt, dass die Sitzung beendet wurde.  Sobald die Sitzung beendet wurde, Gäste werden nicht mehr auf die Inhalte zugreifen, und alle temporären Dateien werden automatisch bereinigt.

Probleme mit dem Freigeben? Sehen Sie sich [Problembehandlung](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Beitreten Sie zu einer zusammenarbeitssitzung

Nach dem Herunterladen und Installieren von Visual Studio Live Share, müssen Gäste nur einige der Schritte zum Verknüpfen einer gehosteten zusammenarbeitssitzung in Anspruch nehmen. Es gibt zwei Möglichkeiten, um zu verknüpfen: [über den Browser](#join-via-the-browser) und [manuell](#join-manually).

> **Security Tip:** Als Gast beitreten zu einer zusammenarbeitssitzung ist es wichtig zu verstehen, dass die Hosts den Zugriff auf bestimmte Dateien oder Funktionen beschränkt werden können. Möchten Sie die Auswirkungen auf die Sicherheit einiger Features und Einstellungen Live Share zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

### <a name="join-via-the-browser"></a>Verknüpfen Sie über den browser

Die einfachste Möglichkeit zum Verknüpfen einer zusammenarbeitssitzung ist auf den Link zur freigabeeinladung einfach in einem Webbrowser zu öffnen. Hier ist, was Sie erwarten können, wenn Sie diesen Flow ausführen.

1. **Anmelden**

    Nach dem Live Share-Erweiterung installieren, das erneute Laden, und Warten von Abhängigkeiten, um die Installation abzuschließen, sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Klicken Sie auf den Link zur freigabeeinladung / die INVITE-Nachricht in Ihrem Browser geöffnet.**

    Der Link zur freigabeeinladung in einem Browser, öffnen Sie einfach (oder erneut zu öffnen Sie).

    > **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, wird mit Links zu den Extension Marketplace angezeigt. Installieren Sie die Erweiterung, und starten Sie das Tool, und wiederholen Sie.

    Sie sollten eine Benachrichtigung über möchte, dass der Browser eine aktivierte Freigabe für die Live-Tool zu starten. Wenn Sie es in das ausgewählte Tool starten können, müssen Sie mit der zusammenarbeitssitzung Start verbunden sein.

    ![Verknüpfen Sie die Seite](../media/join-page.png)

    Wenn der Host offline ist, werden Sie an diesem Punkt stattdessen benachrichtigt werden. Sie können dann wenden Sie sich an den Host und bitten Sie ihn erneut freigeben.

    > [!NOTE]
    > Achten Sie darauf haben Sie **das Tool mindestens einmal gestartet** nach Installation der Visual Studio Live Share-Erweiterung und die Installation vor der öffnenden/erneute-opening der Seite "einladen" zulässig. Immer noch Probleme? Finden Sie unter [Manuelles Verknüpfen von](#join-manually).

3. **Zusammenarbeit**

    Das ist alles! Nach wenigen Augenblicken es wird eine Verbindung, und Sie können beginnen, zusammenarbeiten.

    Sie sehen, dass der Übergang "Share" Schaltfläche "Sitzungszustand" übermitteln. Finden Sie unter [Sitzungszustand](#session-states) Informationen weiter unten aus, wie dies aussieht.

    Sie werden dann automatisch in die Datei weitergeleitet, die der Host derzeit bearbeitet wird, sobald die Verknüpfung abgeschlossen ist.

### <a name="join-manually"></a>Manuelles Verknüpfen von

Sie können auch manuell verknüpfen, ohne einen Webbrowser, der in Situationen nützlich sein kann, in dem das Tool, das Sie verwenden möchten wird bereits ausgeführt, Sie ein anderes Tool verwenden, als Sie in der Regel nicht, oder wenn Sie Probleme haben sollten einladen Probleme bei der Links aus irgendeinem Grund arbeiten möchten. Der Prozess ist einfach:

1. **Anmelden**

    Nach dem Live Share-Erweiterung installieren, das erneute Laden, und Warten von Abhängigkeiten, um die Installation abzuschließen, sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Verwenden Sie den joinbefehl**

    Öffnen Sie die benutzerdefinierte Live Share-Registerkarte in der Aktivitätsleiste von VS Code, und wählen Sie die "Join zusammenarbeitssitzung..." Symbol "oder der Eintrag.

    ![Symbol "Viewlet" verknüpfen](../media/vscode-join-viewlet.png)

3. **Fügen Sie den Link für die INVITE-Nachricht**

    Fügen Sie die URL des INVITE-Nachricht gesendet und erreicht wurden die EINGABETASTE, um zu bestätigen.

4. **Arbeiten Sie zusammen!**

    Das ist alles! Sie sollten mit der zusammenarbeitssitzung vorübergehend verbunden werden.

    Sie sehen, dass der Übergang "Share" Schaltfläche "Sitzungszustand" übermitteln. Finden Sie unter [Sitzungszustand](#session-states) Informationen weiter unten aus, wie dies aussieht.

    Sie werden dann automatisch in die Datei weitergeleitet, die der Host derzeit bearbeitet wird, sobald die Verknüpfung abgeschlossen ist.

### <a name="leave-the-collaboration-session"></a>Lassen Sie die zusammenarbeitssitzung

Als Gast können Sie der zusammenarbeitssitzung lassen, ohne es für andere Benutzer einfach schließen Sie VS Code-Fenster zu beenden. Wenn Sie das Fenster geöffnet bleibt lieber, können Sie öffnen Sie die Live-Freigabe-Explorer-Ansicht oder der Registerkarte "benutzerdefinierte Live Share" und wählen Sie das Symbol "Zusammenarbeitssitzung verlassen".

![Symbol für / / Blätter-Sitzung](../media/vscode-leave-session-viewlet.png)

Alle temporären Dateien werden automatisch bereinigt, sodass keine weitere Aktion erforderlich ist.

Probleme mit dem Verknüpfen? Sehen Sie sich [Problembehandlung](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Gemeinsame Bearbeitung

Sobald ein Gast eine zusammenarbeitssitzung verknüpft ist, werden alle Mitarbeiter sofort gegenseitig Bearbeitungen und Auswahl in Echtzeit sehen können. Alles, was Sie tun müssen ist, wählen Sie eine Datei im Datei-Explorer, und mit der Bearbeitung beginnen. Sowohl Hosts und -Gäste sehen die Änderungen machen und sich somit leicht durchlaufen, und um die nach-unten-Lösungen schnell fixieren beitragen können.

> [!NOTE]
> Beitreten zu einer zusammenarbeitssitzung nur-Lese werden Gäste daran gehindert, werden Änderungen an Dateien vornehmen können. Ein Host kann [nur-Lese Modus zu aktivieren, bei der Freigabe](#share-a-project). Als Gast, können Sie feststellen, ob Sie eine nur-Lese Sitzung beigetreten sind, anhand Ihrer [Sitzungszustand](#session-states).

![Screenshot mit gemeinsam bearbeiten](../media/vscode-coedit.png)

> [!NOTE]
> Gleichzeitig bearbeiten, gelten Einschränkungen für bestimmte Sprachen. Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

Cursor und Änderungen werden die ausgewählten Optionen, die Sie vornehmen, auch an alle Teilnehmer in der gleichen Datei angezeigt. Dies erleichtert das hervorheben, in dem Probleme vorhanden sind oder Ideen vermitteln können.

![Screenshot mit Hervorhebung](../media/vscode-highlight.png)

Besser noch, können Sie und andere Teilnehmer für jede Datei im freigegebenen Projekt navigieren. Sie können entweder bearbeiten, unabhängig voneinander oder zusammen, was bedeutet, dass Sie nahtlos zwischen Untersuchung, wodurch kleine Anpassungen und vollständige gemeinsamen Bearbeitens wechseln können.

Die daraus resultierenden Bearbeitungen werden auf dem Computer des Hosts auf beibehalten, speichern Sie es ist nicht erforderlich, synchronisieren, mithilfe von Push übertragen oder Dateien zu senden, sobald Sie fertig sind bearbeiten. Die Änderungen treten "nur."

> **Security Tip:** Bei allen Teilnehmern können unabhängig voneinander navigieren und Bearbeiten von Dateien, als Host, sollten Sie einschränken, welche Dateien in Ihrem Projekt über Zugriff auf Gäste sind eine. vsls.json-Datei. Als Gast ist es auch wichtig zu wissen, dass Sie bestimmte Dateien durch diese Einstellungen nicht sehen können. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

### <a name="changing-participant-flag-behaviors"></a>Ändern die Teilnehmer Flag-Verhalten

In der Standardeinstellung zeigt Visual Studio Live Share automatisch ein "Flag" neben den Teilnehmer-Cursor, wenn darauf gezeigt wird, oder wenn sie bearbeiten möchten, markieren Sie oder bewegen Sie ihren Cursor. In einigen Fällen empfiehlt es sich, dieses Verhalten ändern.

Einfach **bearbeiten "Settings.JSON"** (Datei > Voreinstellungen > Einstellungen), fügen Sie einen der folgenden Zeilen hinzu, und starten Sie VS Code neu:

| Einstellung | Verhalten |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | Das Flag wird nur angezeigt, wenn Sie über den Cursor bewegen. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Dies ist die Standardeinstellung. Das Flag wird angezeigt, wenn darauf gezeigt wird oder wenn der Teilnehmer bearbeitet, hebt hervor, oder verschiebt den Cursor. |
| ``"liveshare.nameTagVisibility":"Always"`` | Das Flag ist immer sichtbar. |

## <a name="following"></a>Folgende

Manchmal müssen Sie ein Problem erläutern oder etwas entwerfen, dass sich über mehrere Dateien oder Stellen im Code erstreckt. In diesen Fällen kann es hilfreich sein, ein Kollege vorübergehend zu folgen, wie er im gesamten Projekt verschieben. Aus diesem Grund nach dem Eintritt in einer zusammenarbeitssitzung führen Sie die automatisch"Host". Wenn jemand befolgen, bleibt mit ihrer aktuell geöffneten Datei, und scrollen Sie Position synchron Ihrem Editor.

> [!NOTE]
> In der Standardeinstellung geöffnet Live Share-Freigaben auf den freigegebenen Ordner auch externe Dateien. Wenn Sie diese Funktion deaktivieren möchten, aktualisieren Sie `liveshare.shareExternalFiles` Live Share zu `false` in "Settings.JSON".

Um nach einem Teilnehmer (entweder als Host oder Gast) zu starten, klicken Sie auf ihren Namen aus der Teilnehmer in der Live-Freigabe-Explorer-Ansicht oder die Registerkarte "Benutzerdefiniert". Der Kreis neben dem Namen werden ausgefüllt, um anzugeben, dass Sie diese folgen.

![Führen Sie Visual Studio Code viewlet](../media/vscode-follow-multiple-viewlet.png)

Alternativ können Sie das Symbol in der oberen Ecke des Editor-Gruppe oder drücken Sie zum Anheften klicken **Strg + Alt + F / Cmd + Alt + F**.

![VS Code-pin](../media/vscode-pin.png)

> [!NOTE]
> Ist mehr als eine andere Person in der zusammenarbeitssitzung, werden Sie aufgefordert, wählen Sie den Teilnehmer, die, den Sie ausführen möchten.
>
>![Screenshot zeigt die Liste der Mitarbeiter](../media/vscode-list-collaborators.png)

Da Folgendes mit einer Editor-Verwaltungsgruppe verbunden ist, können Sie geteilte Ansicht (oder ein Rasterlayout!) für eine Gruppe, die einen Teilnehmer folgt und eine Gruppe aus, die nicht ist. Dadurch können Sie Passiv jemand führen bei der Arbeit auch auf ein beliebiges Objekt unabhängig voneinander. Mit einer Editor-Gruppe ausgewählt haben können Sie einen Teilnehmer in der Liste der Teilnehmer an diese Gruppe links auswählen.

![VS Code-Pin in der geteilten Ansicht](../media/vscode-follow-split.png)

Um erleichtern Ihnen die Out-of "führen Sie im Modus" wechseln, und starten die Bearbeitung auf Ihren eigenen, werden Sie automatisch beendet, folgenden, wenn diese auftreten:

1. Sie starten die aktive Datei bearbeiten
1. Öffnen Sie eine andere Datei
1. Sie schließen die aktive Datei

Darüber hinaus Sie können explizit beendet werden nach einer Person durch erneutes Klicken auf das Symbol zum Anheften oder an diese stoßen **Strg + Alt + F / Cmd + Alt + F**.

## <a name="listing-participants"></a>Auflisten von Teilnehmern

Eine schnelle Möglichkeit, die der zusammenarbeitssitzung steht in ist die Liste der Teilnehmer in der Live-Freigabe-Explorer-Ansicht oder die Registerkarte "Benutzerdefiniert" ansehen. Die Ansichten, werden alle Teilnehmer in der Sitzung angezeigt.

![Screenshot mit Benutzer-Statusleistensymbol](../media/vscode-explorer-view.png)

Alle Teilnehmer in der Liste auf, wird sie in Ihrer aktiven Editor-Gruppe folgen.

Drücken Sie alternativ **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** , und wählen Sie die "Live-Freigabe: Liste von Teilnehmern"-Befehl oder **klicken Sie auf** auf das Element die Status mit dem zeigt die Anzahl der Teilnehmer in der Sitzung.

![Screenshot mit Benutzer-Statusleistensymbol](../media/vscode-user-status.png)

Eine Liste mit allen Teilnehmern in der Sitzung wird dann angezeigt. Im Gegensatz zu der Sie auf das Symbol zum Anheften klicken, wird diese Liste angezeigt, auch wenn es nur eine andere Person in der Sitzung mit der Sie Sie immer schnell sehen, in einer anderen Person befindet. Aus Gründen der Einfachheit halber wie das Symbol zum Anheften können Sie dann einen der Teilnehmer zu folgen in der Liste auswählen. Drücken Sie ESC, wenn Sie stattdessen beenden möchten.

## <a name="focusing"></a>Konzentrieren

Gelegentlich sollten Sie alle Benutzer in einer zusammenarbeitssitzung und sehen Sie sich etwas, das Sie ausführen. Live Share können Sie Fragen sich, dass jeder "ihre Aufmerksamkeit auf Sie eine Benachrichtigung, die Sie Sie wieder folgen erleichtert konzentrieren".

Öffnen Sie die benutzerdefinierte Live Share-Registerkarte in der Aktivitätsleiste von VS Code oder in der Live-Freigabe-Explorer-Ansicht, und wählen Sie das Symbol "Fokus Teilnehmer".

![Symbol "Fokus Viewlet"](../media/vscode-focus-viewlet.png)

Nachdem Sie den Befehl ausführen, erhalten alle Benutzer in der zusammenarbeitssitzung eine Benachrichtigung, dass Sie ihre Aufmerksamkeit angefordert wurden.

![Fokus Toast-Benachrichtigung](../media/vscode-focus-toast.png)

Sie können nur "Folgen" direkt über die Benachrichtigung klicken, wenn sie den Fokus auf die Sie speichern möchten.

## <a name="co-debugging"></a>Gemeinsames Debuggen

Visual Studio Live Share Zusammenarbeit debugging-Funktion ist eine leistungsstarke und eindeutige Möglichkeit, ein Problem debuggen können. Nach der Aktivierung einer Oberfläche zur Zusammenarbeit, um Probleme zu beheben, können es auch Sie und anderen Teilnehmern in der Sitzung, die die Möglichkeit, untersuchen Sie Probleme bei bestimmten Umgebung sein durch Bereitstellen einer gemeinsam genutzten debugging-Sitzungs auf dem Computer des Hosts.

> **Security Tip:** Bei allen Teilnehmern können unabhängig voneinander navigieren und Bearbeiten von Dateien, als Host, sollten Sie einschränken, welche Dateien in Ihrem Projekt über Zugriff auf Gäste sind eine. vsls.json-Datei. Sie sollten außerdem beachten, dass der Konsole/REPL-Zugriff bedeutet, dass die Teilnehmer Befehle auf Ihrem Computer ausführen können, sodass Sie nur mit diesen gemeinsam beheben sollten, denen, die Sie vertrauen. Als Gast ist es auch wichtig zu wissen, dass Sie möglicherweise nicht den Debugger Befolgen der Schritte in bestimmte beschränkte Dateien-Dateien durch diese Einstellungen können. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

Verwenden es einfach aus.

1. Achten Sie darauf, dass der Host und alle Gäste der entsprechenden Erweiterung installiert haben. (Technisch gesehen ist dies nicht immer erforderlich, aber es ist im Allgemeinen eine gute Idee.)

2. Als Host fungiert, falls er noch nicht für das Projekt eingerichtet haben, sollten Sie [konfigurieren Sie die Datei "Launch.JSON"](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) zum Debuggen von der Anwendung aus Visual Studio Code, wie gewohnt. Es ist keine spezielle Einrichtung erforderlich.

3. Als Nächstes kann der Host Debuggen mithilfe der Schaltfläche in der Registerkarte "Debuggen", wie gewohnt.

    ![Visual Studio Code – Schaltfläche "Debuggen"](../media/vscode-debug-button.png)

    > [!TIP]
    > Sie können auch Visual Studio-debugging-Sitzungen von Visual Studio Code und umgekehrt teilnehmen! Sehen Sie sich die [Visual Studio-Anweisungen](vs.md#co-debugging) gemeinsam Debugging für Weitere Informationen.

Nachdem der Debugger aufseiten des Hosts angefügt wurde, werden alle Gäste auch automatisch angefügt. Obwohl eine Debuggen "Sitzung", die auf dem Computer des Hosts ausgeführt wird, werden alle Teilnehmer verbunden sind und verfügen über eigene Ansicht.

![VS Code-Debugger angefügt](../media/vscode-debugger.png)

Alle Benutzer kann des Debugprozesses schrittweise dadurch nahtlosen Wechsel zwischen Mitarbeitern, ohne zum Aushandeln der Kontrolle.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

Jede Projektmitarbeiter kann verschiedene Variablen zu untersuchen, fahren Sie mit anderen Dateien in der Aufrufliste, untersuchen Sie Variablen, und auch hinzufügen oder entfernen Haltepunkte. Co-Bearbeitungsfeatures können dann jeder Teilnehmer Redner zu verfolgen, wo sich die anderen die einzigartige Möglichkeit, problemlos Wechseln zwischen gleichzeitig untersuchen verschiedene Aspekte des Problems und Debuggen gemeinsam zu befinden.

> [!NOTE]
> In einer zusammenarbeitssitzung nur-Lese werden Gast nicht des Debugprozesses schrittweise können. Sie können jedoch immer noch hinzufügen oder entfernen Haltepunkte, und untersuchen Sie Variablen.

![Animation der gleichzeitigen Debuggen](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Ändern Sie bei Visual Studio Code-Joins Debugsitzungen

Standardmäßig werden als Gast Sie automatisch angefügt werden, Debugsitzungen erhalten, wenn sie von dem Host gemeinsam verwendet werden. Allerdings können in einigen Fällen Sie dieses Verhalten störend finden. Glücklicherweise können Sie sie wie folgt ändern:

Einfach **bearbeiten "Settings.JSON"** (Datei > Voreinstellungen > Einstellungen), fügen Sie einen der folgenden Zeilen hinzu, und starten Sie VS Code neu:

| Einstellung | Verhalten |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | Der Standardwert. Als Gast werden Sie automatisch alle freigegebenen Debugsitzung verknüpfen, wenn der Host gestartet wird. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Als Gast werden Sie aufgefordert, eine freigegebene Debugsitzung zu verknüpfen, wenn sie vom Host gestartet wird, werden sollen. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Als Gast müssen Sie manuell alle Debugsitzungen zu verknüpfen. Finden Sie unter [trennen und erneutes Anfügen](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Trennen und erneutes Anfügen

Als Gast möchten Sie möglicherweise Beenden des Debuggens vorübergehend. Glücklicherweise können Sie einfach das Symbol "Beenden", in der Debug-Symbolleiste, um den Debugger zu trennen, ohne Auswirkungen auf den Host oder andere Gäste klicken.

![Schaltfläche "Stopp" VS Code-debugger](../media/vscode-debug-stop.png)

Wenn Sie Einstellungen aktualisiert haben, sodass Sie nicht mehr das automatische Anhängen, oder wenn Sie einfach einem späteren Zeitpunkt erneut anfügen möchten, erreichen Sie dies durch Drücken von **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** oder **auf** auf das Sitzungselement Status Status Leiste und Auswählen von "Anfügen, eine freigegebene Debugsitzung".

![Visual Studio Code den Debugger Anfügen](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Gemeinsame Nutzung der ausgeführten Anwendung in einem browser

Visual Studio Code muss nicht das Konzept einer bekannten "Web Application Port" wie Visual Studio für Projekttypen wie z. B. ASP.NET. Jedoch wenn Sie eine zusammenarbeitssitzung von einem Host für Visual Studio verknüpfen, möglicherweise automatisch Ihrem Standard-Webbrowser angezeigt werden, wenn der ausgeführte Anwendungen des Hosts verbundene, und klicken Sie dann automatisch starten des Debuggens angezeigt. Finden Sie unter [Features von Visual Studio](vs.md#automatic-web-app-sharing) Weitere Details.

Als Host und können Sie etwas Ähnliches erreichen, indem Sie manuell freigeben, die Anwendung oder anderen Endpunkte wie RESTful-Dienste mithilfe der Funktion "Freigabe lokaler Server". Visual Studio und Visual Studio Code-Gäste können, öffnen Sie dann einen Browser auf den gleichen Localhost-Port für die ausgeführte Anwendung anzuzeigen.  Finden Sie unter [freigeben ein Servers](#share-a-server) Weitere Details.

## <a name="share-a-server"></a>Freigeben eines Servers

Von Zeit zu Zeit, als Sitzungshost für eine Zusammenarbeit, stellen Sie möglicherweise fest, dass Sie eine Webanwendung oder anderen lokal ausführen von Servern oder Diensten mit Gäste freigeben möchten. Diese reichen von anderen RESTful-Endpunkte auf Datenbanken und anderen Servern. Visual Studio Live gemeinsam nutzen, können Sie eine lokale Portnummer angeben, geben sie optional einen Namen und dann für alle Gäste freigeben.

Gäste werden auf den Server zugreifen, die, den Sie an diesem Port auf ihren eigenen lokalen Computer auf dem genau gleichen Port freigegeben. Z. B., wenn Sie einen Webserver freigegeben **an Port 3000**, der Gast kann auf dem gleichen ausgeführten Webserver zugreifen, auf deren **eigenen Computer** am http://localhost:3000! Dies ist über einen sicheren SSH oder SSL-Tunnel zwischen den Hosts und Gästen umgesetzt und über den Dienst authentifiziert werden, damit Sie sicher sein können, dass nur die in der zusammenarbeitssitzung zugreifen können.

> **Security Tip:** Als Host sollten Sie sehr selektiv an die Ports können, die Sie für Gäste freigeben, und bleiben Sie auf die Anwendung Ports (anstatt eines System-Ports). Für Gäste freigegebener Anschlüsse verhält sich genau so, wie sie würden, wenn der Server-Dienst auf ihrem eigenen Computer ausgeführt wurde. Dies ist sehr nützlich, aber wenn, dass Sie der falsche Port freigegeben ist kann auch riskant sein.

Aus Gründen der Sicherheit stehen nur Server, die Ports, die Sie angeben, unter anderer Gäste berücksichtigt. Glücklicherweise ist es einfach, als der zusammenarbeitssitzung hinzuzufügen **Host**. Gehen Sie dabei folgendermaßen vor:

1. Öffnen Sie die benutzerdefinierte Live Share-Registerkarte in der Aktivitätsleiste von VS Code oder in der Live-Freigabe-Explorer-Ansicht, und wählen Sie "Freigabe Server..." Eintrag oder klicken Sie auf das Symbol.

    ![VS Code-Freigabe lokaler server](../media/vscode-share-local-server-viewlet.png)<br />

1. Geben Sie die Portnummer an, auf die der Server ausgeführt wird, und optional einen Namen ein.

    ![Screenshot des Port-Number-Eingabeaufforderung](../media/vscode-enter-port.png)<br />

Das ist alles! Der Server, auf dem Port, den Sie angegeben haben wird nun des Gasts "localhost" auf dem gleichen Port zugeordnet werden (es sei denn, die diesen Port bereits belegt wurde).

Wenn der Port bereits verwendet, auf das Gastbetriebssystem-Computer ist, wird eine andere automatisch ausgewählt. Zum Glück als Gast, sehen Sie eine Liste der derzeit freigegebener Anschlüsse (nach Namen, falls angegeben) in der Live Share-Explorer-Ansicht oder eine benutzerdefinierte Registerkarte in der Aktivitätsleiste von VS Code, und klicken Sie auf der Liste der freigegebenen. Sie einen Eintrag auswählen, wird dieser Server in Ihrem Browser geöffnet. Sie können auch mit der rechten Maustaste und wählen Sie die Option auf den Link an den Server in die Zwischenablage zu kopieren.

![VS Code Zugriff lokalen server](../media/vscode-access-shared-server-viewlet.png)<br />

Beachten Sie, dass *Gäste können nicht* steuern, welche Ports auf dem Computer des Hosts aus Sicherheitsgründen gemeinsam genutzt werden.

Um **beenden** Freigeben von einem lokalen Server als Host fungiert, zeigen Sie auf den Servereintrag, in der Liste der gemeinsam genutzte Server in der Live-Freigabe-Explorer-Ansicht oder die Registerkarte "Benutzerdefiniert", und klicken Sie auf das Symbol "Server Freigabe aufheben".

![VS Code beenden Sie die Server Freigabe](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Teilen Sie einen terminal

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise können Live-Freigabe, die Sie als ein Host, um optional "einen Terminal für Gäste freigeben". Freigegebene Terminal kann nur-Lese oder vollständig Zusammenarbeit sein, damit sowohl Sie als auch die Gäste können, führen Sie Befehle aus, und die Ergebnisse anzuzeigen. Sie können terminalausgabe Gäste Sichtbarkeit gewähren oder erhalten praktische und Ausführen von Tests, Builds oder sogar "Selektierung" umgebungsspezifische Problemen, die nur auf dem Computer auftreten können.

Terminale sind jedoch **nicht** standardmäßig freigegeben werden, da die Gäste bieten mindestens über Lesezugriff auf die Ausgabe der Befehle, die Sie ausführen (sofern nicht die Möglichkeit zum Ausführen von Befehlen selbst). Auf diese Weise können Sie kostenlos Befehle ausführen, lokalen stellte Terminals bereit, ohne das Risiko und nur dann freigeben, wenn tatsächlich müssen dies tun. Darüber hinaus können nur Hosts starten, freigegebener Terminals, um zu verhindern, dass Gäste aus einen Startvorgang und Aktionen, die Sie nicht erwartet oder überwacht werden.

Als Host können Sie einen Terminal freigeben, indem Sie die benutzerdefinierte Live-Freigabe-Registerkarte in der Aktivitätsleiste von VS Code oder in der Live-Freigabe-Explorer-Ansicht öffnen und den Server auswählen, "Freigabe..." Eintrag oder auf das Symbol klicken.

![Terminal von VS Code-Freigabe](../media/vscode-share-terminal-viewlet.png)<br />

An diesem Punkt können Sie wählen, einen schreibgeschützten oder Lese-/Schreibzugriff Terminal aus dem Menü. Wenn Terminal Lese-/Schreibzugriff ist, kann jeder Geben Sie im Terminal auch der Host, der sodass sie mühelos eingreifen, wenn der Gast zu maßgeblich zu verbessern, die Ihnen nicht gefallen. Merken Sie sich, Sie sollten jedoch **gewähren Sie Lese-/Schreibzugriff nur für Gäste, wenn Sie wissen sie tatsächlich benötigen** und bleiben Sie mit nur-Lese Terminals für Szenarien, in dem Sie einfach den Gast die Ausgabe von Befehlen finden Sie unter ausführen.

> [!NOTE]
> Wenn der zusammenarbeitssitzung im schreibgeschützten Modus ist, können nur schreibgeschützte Terminals vom Host freigegeben werden.

![Leseberechtigungen oder Lese-/Schreibzugriff-Auswahl](../media/vscode-share-terminal-ro-rw.png)<br />

Nachdem Sie die Art der freigegebenes Terminal, die Sie starten möchten ausgewählt haben, wird ein neues freigegebenes Terminal auf Visual Studio Code Terminals Registerkarte angezeigt.

![Freigegebene terminal ausführen](../media/vscode-share-terminal-up.png)<br />

Wenn mehrere Terminals freigegeben werden oder sich der Fokus, die in einer anderen Registerkarte befindet, können Sie den Fokus zu einem bestimmten Terminal bringen, dazu den Eintrag in der Liste freigegebener Terminals.

![Freigegebenes Terminal Fokus](../media/vscode-shared-terminal-focus.png)<br />

Um die terminal-Sitzung zu beenden, geben Sie einfach beenden, schließen Sie die terminal-Fenster oder klicken Sie auf das Symbol "Aufheben der Freigabe Terminal" in der Live-Freigabe-Explorer-Ansicht oder die Registerkarte "Benutzerdefiniert" angegeben wird, und jeder werden getrennt.

## <a name="session-states"></a>Sitzungsstatus

Nachdem Sie gestartet haben, oder zusammenarbeitssitzung verknüpft und haben Zugriff auf den freigegebenen Inhalt, der Statusleiste von Visual Studio Live Share für Elemente aktualisieren ihre Darstellung, um den Zustand der aktiven zusammenarbeitssitzung widerzuspiegeln.

Im folgenden sind die Zustände, die Sie in der Regel angezeigt werden:

| Zustand | Statusleiste | Beschreibung |
|-------|--------------------|-------------|
| inaktiv | ![VS Code-Status: inaktiv](../media/vscode-status-share.png) | Es ist keine aktive zusammenarbeitssitzung, und nichts wird freigegeben. |
| Host: Freigeben von In Bearbeitung | ![VS Code-Status: Freigeben von in Bearbeitung](../media/vscode-status-sharing.png)| Eine zusammenarbeitssitzung beginnt und inhaltsfreigabe beginnt in Kürze. |
| Host: Freigabe | ![VS Code-Status: Freigabe active ](../media/vscode-status-active.png)| Eine zusammenarbeitssitzung ist aktiv, und Inhalt wird freigegeben. |
| Host: Freigeben von nur-Lese | ![VS Code-Status: Freigeben von nur-Lese](../media/vscode-status-sharing-read-only.png)| Freigeben einer nur-Lese zusammenarbeitssitzung an. |
| Gast: Beitreten zu Sitzung | ![VS Code-Status: Verknüpfen](../media/vscode-status-joining.png)| Verknüpfen eine vorhandene zusammenarbeitssitzung. |
| Gast: Verknüpft | ![VS Code-Status: verknüpft](../media/vscode-status-active.png) | Verknüpft und mit einer active zusammenarbeitssitzung und der empfangende freigegebene Inhalte. |
| Gast: Verknüpft wird, schreibgeschützt | ![VS Code-Status: verknüpft nur-Lese](../media/vscode-status-joined-read-only.png) | Verknüpft und mit einer aktiven schreibgeschützte zusammenarbeitssitzung verbunden sind. |

## <a name="guest-limitations"></a>Gast-Einschränkungen

Es gibt zurzeit einige Nachteile, die Gäste bei der Verwendung der oben beschriebenen Features auftreten, behalten Sitzungshosts Zusammenarbeit die vollständige Funktionalität Tool ihrer Wahl. Über die folgenden Links erhalten Sie weitere Informationen:

- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)
- [Alle große Fehler, Features und Einschränkungen](https://aka.ms/vsls-issues)
- [Alle Anfragen zu Features und Einschränkungen](https://aka.ms/vsls-feature-requests)
- [Problembehandlung](../troubleshooting.md)

## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich folgenden Artikel Weitere Informationen.

- [Schnellstart: Freigeben Sie Ihres ersten Projekts](../quickstart/share.md)
- [Schnellstart: Verknüpfen Sie Ihre erste Sitzung](../quickstart/share.md)
- [Gewusst wie: Zusammenarbeiten mithilfe von Visual Studio](vs.md)
- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Details zur Installation von Linux](../reference/linux.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

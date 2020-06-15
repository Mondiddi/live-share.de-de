---
title: Zusammenarbeiten in Visual Studio Code – Visual Studio Live Share | Microsoft-Dokumentation
description: Vorgehensweisen zur Zusammenarbeit in Visual Studio Code und Live Share
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5db1e2f3afff93747685ade5ff46d0f814775563
ms.sourcegitcommit: a48488302bc56abdedf7130ec22b4e21ac16a4ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84337261"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code

In diesem Artikel erfahren Sie,  wie die Zusammenarbeit in Visual Studio Code mithilfe von Live Share funktioniert. Dabei lernen Sie einige Features der Visual Studio Live Share-Erweiterung für Visual Studio Code kennen.

Beachten Sie, dass an allen hier beschriebenen Zusammenarbeitsaktivitäten ein einziger **Zusammenarbeitssitzungs-Gastgeber** und mindestens ein **Gast** beteiligt sind. Der Gastgeber ist die Person, die die Zusammenarbeitssitzung gestartet hat, und jede Person, die ihr beitritt, ist ein Gast.

*Wenn Sie an einer kurzen Zusammenfassung interessiert sind, finden Sie in den Schnellstarts zum [Freigeben](../quickstart/share.md) und [Beitreten](../quickstart/join.md) weitere Informationen.*

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität in beiden Instanzen verwenden. Probieren Sie es aus!

## <a name="installation"></a>Installation

Bevor Sie beginnen, müssen Sie eine Version von Visual Studio Code installiert haben, die die grundlegenden Anforderungen von Live Share erfüllt. Sie benötigen **Visual Studio Code (1.22.0 oder höher)** unter:

- **Windows:** 7, 8.1 oder 10

- **macOS:** Nur Sierra (10.12) und höher.
    - _El Capitan (10.11) und niedriger werden derzeit aufgrund der Anforderungen von [.NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315) nicht unterstützt._

- **Linux**: 64-Bit-Version von Ubuntu Desktop 16.04 und höher, Fedora Workstation 27 und höher, CentOS 7

    - Für Live Share sind einige [Linux-Voraussetzungen](#linux-install-steps) erforderlich, zu deren Installation Sie möglicherweise aufgefordert werden.
    - _Aufgrund der Anforderungen von [.NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314) werden 32-Bit-Versionen von Linux nicht unterstützt._
    - Zudem wird ARM derzeit nicht unterstützt.
    - Weitere Informationen zur Verwendung von Downstreams und anderen Distributionen finden Sie im Artikel [Linux install details (Details zur Linux-Installation)](../reference/linux.md).

Danach ist das Herunterladen und Installieren der Visual Studio Live Share-Erweiterung kinderleicht:

1. Installieren Sie <a href="https://code.visualstudio.com/">Visual Studio Code</a>.
2. [Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter](https://aka.ms/vsls-dl/vscode), und installieren Sie sie.
3. Laden Sie Visual Studio Code neu.
4. Warten Sie, dass die Abhängigkeiten heruntergeladen und installiert werden (achten Sie auf die Statusleiste).<br/>
    ![Installation wird fertiggestellt](../media/vscode-finishing-install.png)
5. **Linux**: Wenn eine Benachrichtigung angezeigt wird, dass fehlende Bibliotheken installiert werden müssen:
    1. Klicken Sie in der Benachrichtigung auf „Install“ (Installieren).
    2. Geben Sie Ihr Administratorkennwort/sudo-Kennwort ein, wenn Sie dazu aufgefordert werden.
    3. Starten Sie Visual Studio Code im Anschluss neu.

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

[![Herunterladen](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Schritte zur Linux-Installation

Linux ist eine sehr variable Umgebung, deren Einrichtung durch die Vielzahl an Desktopumgebungen und Distributionen sich schwierig gestalten kann. Wenn Sie unterstützte Versionen von **Ubuntu Desktop** (16.04 und höher), **Fedora Workstation** (27 und höher) und **CentOS 7** einsetzen und nur **offizielle Distributionen von Visual Studio Code** verwenden, sollte sich die Einrichtung jedoch einfach gestalten. Falls Sie jedoch eine vom Standard abweichende Konfiguration oder eine Downstreamdistribution verwenden, können eventuell Probleme auftreten. Weitere Informationen finden Sie unter [Linux installation details (Details zur Linux-Installation)](../reference/linux.md).

#### <a name="install-linux-prerequisites"></a>Installation der erforderlichen Komponenten für Linux

Einige Distributionen von Linux enthalten nicht alle Bibliotheken, die für Live Share erforderlich sind. Standardmäßig erkennt und installiert Live Share die erforderlichen Komponenten für Linux. Wenn Live Share ein Problem ermittelt, das aus fehlenden Bibliotheken resultiert, wird eine Popupbenachrichtigung angezeigt, die Sie auffordert, Live Share die Berechtigung zum Installieren der Bibliotheken zu erteilen.

![Popupbenachrichtigung mit der Meldung, dass erforderliche Komponenten für Linux fehlen](../media/vscode-linux-prereq-missing.png)

Wenn Sie auf „Install“ (Installieren) klicken, wird ein Terminalfenster angezeigt, in dem Sie Ihr Administratorkennwort/sudo-Kennwort eingeben müssen, um die Installation fortzusetzen. Wenn diese erfolgreich ausgeführt wird, sollte die Einrichtung nach einem Neustart von Visual Studio Code abgeschlossen sein. Weitere Tipps und Problemumgehungen finden Sie im Abschnitt **[tips by distribution (Tipps nach Distribution)](../reference/linux.md#tips-by-distribution)** .

Wenn eine Meldung angezeigt wird, dass das Skript Ihre Distribution nicht unterstützt, finden Sie von der Community zusammengestellte Informationen unter **[tips for community supported distributions (Tipps zu von der Community unterstützten Distributionen)](../reference/linux.md#tips-for-community-supported-distros)** .

Wenn Sie **nicht möchten, dass Visual Studio Code den Befehl für Sie ausführt**, können Sie die aktuelle Version dieses Skripts jederzeit mithilfe des folgenden Befehls über ein Terminalfenster manuell ausführen:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Browserintegration unter Linux

In der Regel sind für die Browserintegration unter Linux **keine zusätzlichen Installationsschritte** in Visual Studio Live Share erforderlich.

Auf manchen Distributionen wird möglicherweise **eine Meldung angezeigt, dass Ihr Administratorkennwort/sudo-Kennwort erforderlich ist**, um die Installation abzuschließen. Daraufhin wird ein Terminalfenster angezeigt, das den Installationspfad für das Startprogramm des Browsers enthält. Geben Sie Ihr Kennwort ein, wenn Sie dazu aufgefordert werden, und drücken Sie nach Abschluss der Installation die EINGABETASTE, um das Terminalfenster zu schließen.

Weitere Informationen zu dieser Anforderung und zum Speicherort von Dateien durch Live Share finden Sie **[hier](../reference/linux.md#linux-browser-integration)** . Beachten Sie jedoch, dass Sie **[Zusammenarbeitssitzungen manuell beitreten können](../use/vscode.md#join-manually)** , wenn die Browserintegration nicht funktioniert.

## <a name="sign-in"></a>Anmelden

Wenn Sie mit anderen Personen zusammenarbeiten möchten, müssen Sie sich in Visual Studio Live Share anmelden, damit diese wissen, wer Sie sind. Dies ist nur eine Sicherheitsmaßnahme. Sie willigen dadurch **nicht** ein, an Marketing- oder anderen Marktforschungsaktivitäten teilzunehmen. Sie können sich mit einem persönlichen Microsoft-Konto (z. B. @outlook.com), einem Geschäfts-, Schul- oder Unikonto von Microsoft (über AAD) oder mit einem GitHub-Konto anmelden. Die Anmeldung ist unkompliziert.

**Klicken** Sie auf der Statusleiste auf „Live Share“, oder drücken Sie **STRG+UMSCHALT+P bzw. CMD+UMSCHALT+P**, und wählen Sie den Befehl „Live Share: Sign In With Browser“ (Live Share: Mit Browser anmelden) aus.

![Schaltfläche zum Anmelden in Visual Studio Code](../media/vscode-sign-in-button.png)

Eine Benachrichtigung wird angezeigt, die Sie auffordert, sich mithilfe Ihres Webbrowsers anzumelden. Wenn Sie auf „launch sign in“ (Anmelden) klicken, wird ein Browser geöffnet, in dem Sie die Anmeldung durchführen können. Schließen Sie den Browser, wenn Sie fertig sind.

![Popupbenachrichtigung mit der Aufforderung, sich über einen Webbrowser anzumelden](../media/vscode-sign-in-toast.png)

> **Linux-Benutzer:** Wenn Sie eine ältere Version von Live Share (v0.3.295 oder darunter) verwenden, werden Sie möglicherweise aufgefordert, einen Benutzercode einzugeben. Aktualisieren Sie auf die neueste Version der Erweiterung, oder klicken Sie nach Ihrer Anmeldung auf den Link „Gibt es Probleme?“, um den Code anzuzeigen. Weitere Informationen finden Sie [im Verlauf des Artikels](#sign-in-using-a-user-code).

#

> **Tipp für Fortgeschrittene:** Mithilfe der Einstellungen `liveshare.account` und `liveshare.accountProvider` können Sie auswählen, welches Konto für die automatische Anmeldung verwendet werden soll, falls Sie Anmeldeinformationen für mehrere Konten zwischengespeichert haben.
> Nehmen Sie beispielsweise an, dass Sie an zwei Projekten arbeiten, für die Sie sich mit unterschiedlichen Identitäten anmelden möchten. In den Arbeitsbereicheinstellungen von Visual Studio Code könnten Sie die Einstellung `liveshare.account` in jedem Projektverzeichnis auf eine andere E-Mail-Adresse festlegen, um sicherzustellen, dass die Anmeldung automatisch mit dem richtigen Konto durchgeführt wird. Die Einstellung `liveshare.accountProvider` könnte auf `"microsoft"` oder `"github"` festgelegt werden, sofern Sie dieselbe E-Mail-Adresse mit mehreren Anbietern verwenden möchten.

Wenn Sie nach der Anmeldung über den Browser nicht in Visual Studio Code angemeldet sind, finden Sie eine weitere Anmeldemethode unter [Anmeldung mit einem Benutzercode](#sign-in-using-a-user-code). In der [Problembehandlung](../troubleshooting.md#sign-in) finden Sie andernfalls weitere Tipps.

### <a name="sign-in-using-a-user-code"></a>Anmeldung mit einem Benutzercode

Wenn Visual Studio Code Ihre durchgeführte Anmeldung nicht erkennt, können Sie stattdessen einen Benutzercode eingeben.

1. Drücken Sie **STRG+UMSCHALT+P, CMD+UMSCHALT+P**, und führen Sie den Befehl „Live Share: Sign in with user code“ (Live Share: Mit Benutzercode anmelden) aus.

2. Daraufhin sollte ein Browserfenster geöffnet werden, in dem Sie den Anmeldevorgang abschließen können.

    > [!NOTE]
    > Wenn der Browser nicht automatisch geöffnet wird, navigieren Sie in einem Browser zu [dieser URL](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login), und melden Sie sich an.

3. Klicken Sie anschließend auf „Having trouble? Click here for user code directions“ (Probleme bei der Anmeldung? Klicken Sie hier, um einen Benutzercode zu erhalten.), um den Benutzercode anzuzeigen.

    ![Screenshot: Benutzercode im Browser](../media/vscode-user-code-browser.png)

4. Kopieren Sie den Benutzercode.

5. Fügen Sie den Benutzercode nun in das Eingabefeld ein, das nach der Ausführung des Befehls angezeigt wurde, und drücken Sie die EINGABETASTE, um die Anmeldung abzuschließen.

    ![Screenshot: Eingabefeld für Benutzercode](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Verwendung des Live Share-Viewlet

Nach der Installation von Visual Studio Live Share wird eine benutzerdefinierte Registerkarte zur Aktivitätsleiste in Visual Studio Code hinzugefügt. Über diese Registerkarte können Sie auf alle Live Share-Funktionen für die Zusammenarbeit zugreifen. Wenn Sie eine Zusammenarbeitssitzung freigeben oder dieser beitreten, wird eine Ansicht auf der Explorer-Registerkarte angezeigt, über die Sie auf diese Funktionen zugreifen können.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Über diese Ansicht wird die Position der Teilnehmer im freigegebenen Code angezeigt. Sie können unter anderem auf einen Teilnehmer klicken, um diesem zu folgen, bestimmte Teilnehmer fokussieren oder auf freigegebene Server und Terminals zugreifen.

## <a name="using-the-scoped-command-menu"></a>Verwendung des bereichsbezogenen Befehlsmenüs

Darüber hinaus sind alle Visual Studio Live Share-Funktionen über die Befehlspalette in Visual Studio Code verfügbar, auf die Sie über STRG+UMSCHALT+P, CMD+UMSCHALT+P oder F1 zugreifen können. Wenn Sie „live share“ eingeben, wird eine vollständige Liste der verfügbaren Befehle angezeigt.

Da diese Liste unter Umständen sehr lang ist, ist es häufig einfacher, ein bereichsbezogenes Befehlsmenü zu verwenden, das über die Statusleiste verfügbar ist. Wenn Sie auf der Statusleiste auf das Symbol für die Anmeldung bzw. den Sitzungszustand klicken, wird sofort eine kontextbezogene Liste der verfügbaren Befehle angezeigt.

![Symbol für Sitzungszustand in Visual Studio Code](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Freigeben eines Projekts

Führen Sie nach dem Herunterladen und Installieren von Visual Studio Live Share die folgenden Schritte aus, um eine Zusammenarbeitssitzung zu starten und einen Kollegen einzuladen.

1. **Melden Sie sich an:**

    Nachdem Sie die Live Share-Erweiterung installiert, neu geladen und gewartet haben, bis die Installation von Abhängigkeiten beendet ist, sollten Sie sich nun anmelden, damit andere Projektmitarbeiter wissen, wer Sie sind. Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Öffnen Sie einen Ordner:**

    Öffnen Sie wie gewohnt einen Ordner, ein Projekt oder eine Projektmappe, die Sie für Gäste freigeben möchten.

3. **Aktualisieren Sie ausgeblendete oder ausgeschlossene Dateien (optional):**

    In Live Share werden Dateien/Ordner, auf die in GITIGNORE-Dateien in Ihren freigegebenen Ordnern verwiesen wird, vor Gästen standardmäßig **ausgeblendet**. Durch **Ausblenden** einer Datei wird verhindert, dass sie in der Dateistruktur des Gasts angezeigt wird. Durch das **Ausschließen** einer Datei wird eine striktere Regel angewendet. Sie verhindert, dass Live Share die Datei für den Gast öffnet, wenn diese z.B. die Aktion „Gehe zu Definition“ durchführen, oder wenn Sie eine Datei beim Debuggen oder während Ihnen ein anderer Teilnehmer folgt schrittweise ausführen. Wenn Sie unterschiedliche Dateien ausblenden/ausschließen möchten, kann eine **VSLS.JSON**-Datei Ihrem Projekt mit diesen Einstellungen hinzugefügt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

4. **Starten Sie eine Zusammenarbeitssitzung:**

    **Klicken** Sie nun auf der Statusleiste auf „Live Share“, oder drücken Sie **STRG+UMSCHALT+P bzw. CMD+UMSCHALT+P**, und wählen Sie den Befehl „Live Share: Start a collaboration session (Share)" (Live Share: Zusammenarbeitssitzung starten (Freigeben)) aus.

    ![Schaltfläche für Freigabe](../media/vscode-share-button-new.png)

    > [!NOTE]
    > Möglicherweise werden Sie von der Firewallsoftware Ihres Desktops gefragt, ob Sie zulassen möchten, dass der Live Share-Agent bei Ihrer ersten Freigabe einen Port öffnet. Dies zuzulassen, ist Ihnen völlig freigestellt, ermöglicht aber einen gesicherten „direkten Modus“ zur Leistungsverbesserung, wenn sich die Person, mit der Sie zusammenarbeiten, in demselben Netzwerk wie Sie befindet. Details dazu finden Sie unter [Changing the connection mode (Ändern des Verbindungsmodus)](../reference/connectivity.md#changing-the-connection-mode).

    Ein Einladungslink wird automatisch in die Zwischenablage kopiert. Andere Personen können mit diesem Link im Browser einer neuen Zusammenarbeitssitzung beitreten, in der Ordnerinhalte für diese Teilnehmer freigegeben werden.

    Außerdem wird die Option „Live Share“ in der Statusleiste in den entsprechenden Sitzungszustand geändert. Informationen zu [Sitzungszuständen](#session-states) finden Sie weiter unten.

    Wenn Sie bereits Inhalte freigeben und den Einladungslink noch einmal abrufen müssen, können Sie auf die auf das Statusleistensymbol für den Sitzungszustand klicken und „Invite Others (Copy Link)“ (Einladen (Link kopieren)) auswählen.

5. **Aktivieren Sie den schreibgeschützten Modus (optional):**

    Sobald Sie Ihre Zusammenarbeitssitzung gestartet haben, können Sie sie als schreibgeschützt festlegen und so verhindern, dass Gäste Änderungen am freigegebenen Code vornehmen.

    Nach der Freigabe erhalten Sie eine Benachrichtigung mit der Information, dass der Einladungslink in Ihre Zwischenablage kopiert wurde. Dann können Sie die Option auswählen, dass die Sitzung schreibgeschützt werden soll.

    ![Schreibgeschützter Modus in Visual Studio Code](../media/vscode-read-only-toast.png)

6. **Senden Sie den Link an eine andere Person:**

    Senden Sie den Link per E-Mail, Slack, Skype usw. an die Personen, die Sie einladen möchten. Bitte beachten Sie: Angesichts der Zugriffsebene, die Live Share-Sitzungen Gästen bereitstellen können, **sollten Sie Inhalte nur für vertrauenswürdige Personen freigeben** und die Folgen Ihrer Freigabe durchdenken.

    > **Sicherheitstipp:** Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

    Wenn der von Ihnen eingeladene Gast Fragen hat, enthält der Artikel [Quickstart: Join your first session (Schnellstart: Beitreten einer Sitzung)](../quickstart/join.md) einige weitere Informationen zum Einrichten und Ausführen einer Sitzung als Gast.

7. **Genehmigen Sie den Gast (optional):**

    Standardmäßig treten Gäste Ihrer Zusammenarbeitssitzung automatisch bei, und Sie werden benachrichtigt, wenn sie zur Zusammenarbeit mit Ihnen bereit sind. Durch diese Benachrichtigung haben Sie die Möglichkeit, den Gast aus der Sitzung zu entfernen. Sie können aber auch festlegen, dass eine Genehmigung erforderlich ist, sobald eine Person der Sitzung beitritt.

    Fügen Sie folgende Zeile zu „settings.json“ hinzu, um dieses Feature zu aktivieren:

         "liveshare.guestApprovalRequired": true

    Wenn anschließend ein Gast der Sitzung beitreten möchte, erhalten Sie eine Benachrichtigung mit einer Genehmigungsanforderung.

    ![Genehmigungsanforderung für einen Beitritt zur Sitzung in Visual Studio Code](../media/vscode-join-approval.png)

    Unter [Invitations and join access (Konfigurieren von Einladungen und Beitritten)](../reference/security.md#invitations-and-join-access) finden Sie weitere Informationen zur Sicherheit von Einladungen.

Damit haben Sie alle erforderlichen Schritte abgeschlossen.

### <a name="stop-the-collaboration-session"></a>Beenden der Zusammenarbeitssitzung

Als Gastgeber können Sie die Freigabe und die Zusammenarbeitssitzung jederzeit beenden, indem Sie die Live Share-Ansicht im Explorer oder über die benutzerdefinierte Live Share-Registerkarte öffnen und auf das Symbol zum Beenden der Zusammenarbeitssitzung klicken.

![Beenden der Zusammenarbeitssitzung](../media/vscode-end-collaboration-viewlet.png)

Alle Gäste werden benachrichtigt, dass die Sitzung beendet wurde.  Anschließend können sie nicht mehr auf Inhalte zugreifen, und alle temporären Dateien werden automatisch gelöscht.

Falls bei der Freigabe Probleme auftreten, sollten Sie sich die [Problembehandlung](../troubleshooting.md#share-and-join) ansehen.

## <a name="join-a-collaboration-session"></a>Beitreten einer Zusammenarbeitssitzung

Nach dem Herunterladen und Installieren von Visual Studio Live Share können Gäste in wenigen Schritten einer Zusammenarbeitssitzung beitreten. Dazu können sie entweder den [Browser](#join-via-the-browser) nutzen oder [manuell](#join-manually) beitreten.

> **Sicherheitstipp:** Als Gast, der einer Zusammenarbeitssitzung beitritt, ist es wichtig zu verstehen, dass Gastgeber Ihren Zugriff auf bestimmte Dateien oder Features einschränken können. Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features und -Einstellungen verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

### <a name="join-via-the-browser"></a>Beitreten mithilfe des Browsers

Die einfachste Möglichkeit, einer Zusammenarbeitssitzung beizutreten, besteht darin, einen Link in einem Webbrowser zu öffnen. Gehen Sie dazu folgendermaßen vor:

1. **Melden Sie sich an:**

    Nachdem Sie die Live Share-Erweiterung installiert, neu geladen und gewartet haben, bis die Installation von Abhängigkeiten beendet ist, sollten Sie sich nun anmelden, damit andere Projektmitarbeiter wissen, wer Sie sind. Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Klicken Sie auf den Einladungslink, oder öffnen Sie ihn im Browser:**

    Öffnen Sie jetzt den Einladungslink in einem Browser (oder öffnen Sie ihn erneut darin).

    > **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, werden Ihnen Links zum Extension Marketplace angezeigt. Installieren Sie die Erweiterung, starten Sie ihr Tool neu, und wiederholen Sie den Vorgang.

    Sie sollten benachrichtigt werden, dass der Browser ein Live Share-fähiges Tool starten möchte. Wenn Sie zulassen, dass er Ihr ausgewähltes Tool startet, werden Sie gleich nach dem Start mit der Zusammenarbeitssitzung verbunden.

    ![Seite „Beitreten“](../media/join-page.png)

    Wenn der Gastgeber offline ist, werden Sie an diesem Punkt entsprechend benachrichtigt. Dann können Sie Kontakt mit dem Gastgeber aufnehmen und ihn um erneute Freigabe bitten.

    > [!NOTE]
    > **Starten Sie das Tool mindestens einmal**, nachdem Sie die Visual Studio Live Share-Erweiterung installiert haben, und warten Sie auf den Abschluss der Installation, bevor Sie die Seite für die Einladung öffnen oder erneut öffnen. Noch immer Probleme? Unter [Manuelles Beitreten](#join-manually) finden Sie weitere Informationen.

3. **Zusammenarbeit**

    Das ist alles! Nach einigen Augenblicken wird die Verbindung hergestellt, und Sie können mit anderen Personen zusammenarbeiten.

    Die Schaltfläche „Live Share“ wird zudem in den Sitzungszustand geändert. Informationen zu [Sitzungszuständen](#session-states) finden Sie weiter unten.

    Anschließend werden Sie automatisch zur Datei weitergeleitet, die der Gastgeber aktuell bearbeitet.

### <a name="join-manually"></a>Manuelles Beitreten

Sie können einer Sitzung auch manuell, also ohne einen Webbrowser, beitreten. Dies kann in Situationen nützlich sein, in denen das Tool, das Sie verwenden möchten, bereits ausgeführt wird oder Sie ein anderes Tool als sonst üblich nutzen wollen. Auch bei Problemen mit Einladungslinks kann ein Beitritt ohne Webbrowser sinnvoll sein. Ein manueller Beitritt ist leicht mit den folgenden Schritten möglich:

1. **Melden Sie sich an:**

    Nachdem Sie die Live Share-Erweiterung installiert, neu geladen und gewartet haben, bis die Installation von Abhängigkeiten beendet ist, sollten Sie sich nun anmelden, damit andere Projektmitarbeiter wissen, wer Sie sind. Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Verwenden Sie den Beitrittsbefehl:**

    Öffnen Sie die benutzerdefinierte Live Share-Registerkarte über die Aktivitätsleiste in Visual Studio Code, und wählen Sie das Symbol oder den Eintrag zum Beitreten der Zusammenarbeitssitzung aus.

    ![Viewlet-Symbol für den Beitritt](../media/vscode-join-viewlet.png)

3. **Fügen Sie den Einladungslink ein:**

    Fügen Sie die Einladungs-URL ein, die Sie erhalten haben, und drücken Sie zur Bestätigung die EINGABETASTE.

4. **Arbeiten Sie zusammen!**

    Das ist alles! Nach einigen Augenblicken sollte eine Verbindung mit der Zusammenarbeitssitzung hergestellt werden.

    Die Schaltfläche „Live Share“ wird zudem in den Sitzungszustand geändert. Informationen zu [Sitzungszuständen](#session-states) finden Sie weiter unten.

    Anschließend werden Sie automatisch zur Datei weitergeleitet, die der Gastgeber aktuell bearbeitet.

### <a name="leave-the-collaboration-session"></a>Verlassen der Zusammenarbeitssitzung

Als Gast können Sie die Zusammenarbeitssitzung verlassen, ohne diese für die anderen Teilnehmer zu beenden, indem Sie einfach das Visual Studio Code-Fenster schließen. Wenn Sie das Fenster geöffnet lassen möchten, können Sie den Live Share-Explorer oder die benutzerdefinierte Live Share-Registerkarte öffnen und auf „Leave collaboration session“ (Zusammenarbeitssitzung beenden) klicken.

![Symbol zum Beenden der Sitzung](../media/vscode-leave-session-viewlet.png)

Alle temporären Dateien werden automatisch gelöscht. Weitere Aktionen sind nicht erforderlich.

Falls während des Beitretens Probleme auftreten, sollten Sie sich die [Problembehandlung](../troubleshooting.md#share-and-join) ansehen.

## <a name="co-editing"></a>Gemeinsame Bearbeitung

Nachdem ein Gast einer Zusammenarbeitssitzung beigetreten ist, können alle Projektmitarbeiter in Echtzeit sämtliche Änderungen und Auswahlaktionen anderer Personen sehen. Dazu müssen sie nur im Datei-Explorer eine Datei auswählen und mit der Bearbeitung beginnen. Sowohl Gastgebern und als auch Gästen werden Änderungen unmittelbar angezeigt. Diese Personen können außerdem selbst Inhalte beitragen, die anschließend wiederholt bearbeitet werden können, wodurch sich Lösungen schnell erarbeiten lassen.

> [!NOTE]
> In einer schreibgeschützten Zusammenarbeitssitzung können Gäste keine Dateien bearbeiten. Der Gastgeber kann für die [Freigabe den schreibgeschützten Modus aktivieren](#share-a-project). Gäste erkennen eine schreibgeschützte Sitzung am [Sitzungszustand](#session-states).

![Screenshot: gemeinsame Bearbeitung](../media/vscode-coedit.png)

> [!NOTE]
> Bei der gemeinsamen Bearbeitung kann es für bestimmte Sprachen zu Einschränkungen kommen. Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

Zusätzlich zu Cursors und Bearbeitungen sind auch Auswahlaktionen in einer Datei für alle Teilnehmer sichtbar. Dadurch können mögliche Probleme hervorgehoben und Vorschläge vermittelt werden.

![Screenshot: Hervorhebung](../media/vscode-highlight.png)

Sie und weitere Teilnehmer können darüber hinaus zu allen Dateien eines freigegebenen Projekts navigieren. Sie können Dateien entweder gemeinsam oder unabhängig voneinander bearbeiten. Dadurch können Sie wahlweise Probleme untersuchen, kleinere Korrekturen vornehmen oder intensiv mit anderen Personen zusammenarbeiten.

Bearbeitungen werden auf dem Computer des Gastgebers gespeichert. Nach der Bearbeitung müssen Dateien deswegen nicht synchronisiert, gepusht oder an andere Personen gesendet werden.

> **Sicherheitstipp:** Da alle Teilnehmer zu Dateien navigieren und diese bearbeiten können, haben Sie als Gastgeber die Möglichkeit, mit einer VSLS.JSON-Datei den Zugriff auf Dateien innerhalb eines Projekts einzuschränken. Wenn Sie Gast sind, sollten Sie bedenken, dass einige Dateien aufgrund dieser Einstellungen möglicherweise nicht angezeigt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

### <a name="changing-participant-flag-behaviors"></a>Ändern des Flagverhaltens für Teilnehmer

In der Standardeinstellung zeigt Visual Studio Live Share automatisch ein Flag neben dem Teilnehmercursor an, wenn mit diesem auf etwas gezeigt oder wenn dieser bewegt wird. Dasselbe gilt bei Bearbeitungen oder Hervorhebungen. In einigen Fällen empfiehlt es sich, dieses Verhalten zu ändern.

Bearbeiten Sie einfach **settings.json** (Datei > Einstellungen > Einstellungen), indem Sie eine der folgenden Zeilen hinzufügen, und starten Sie Visual Studio Code dann neu:

| Einstellung | Verhalten |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | Das Flag wird nur angezeigt, wenn Sie mit dem Cursor auf etwas zeigen. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Dies ist die Standardeinstellung. Das Flag wird angezeigt, wenn mit dem Cursor auf etwas gezeigt oder wenn dieser bewegt wird. Zusätzlich wird es bei Bearbeitungen oder Hervorhebungen angezeigt. |
| ``"liveshare.nameTagVisibility":"Always"`` | Das Flag ist immer sichtbar. |

## <a name="following"></a>Folgen von Teilnehmern

Manchmal müssen Sie ein Problem erläutern oder etwas entwerfen, dass sich über mehrere Dateien oder Stellen im Code erstreckt. In diesen Fällen kann es hilfreich sein, einem Kollegen vorübergehend zu folgen, während er das Projekt bearbeitet. Aus diesem Grund folgen Sie beim Beitritt einer Zusammenarbeitssitzung automatisch dem Gastgeber. Wenn Sie jemandem folgen, werden in Ihrem Editor die geöffnete Datei sowie die Scrollposition synchronisiert.

> [!NOTE]
> Live Share öffnet Dateien standardmäßig auch außerhalb des freigegebenen Ordners. Wenn Sie dieses Feature deaktivieren möchten, ändern Sie `liveshare.shareExternalFiles` in „settings.json“ in `false`.

Wenn Sie einem Teilnehmer (als Gastgeber oder Gast) folgen möchten, klicken Sie auf der Teilnehmerliste im Live Share-Explorer oder auf der benutzerdefinierten Live Share-Registerkarte auf dessen Namen. Der Kreis neben dem Namen wird dann ausgefüllt. Das bedeutet, dass Sie diesem Teilnehmer folgen.

![Folgen-Viewlet in Visual Studio Code](../media/vscode-follow-multiple-viewlet.png)

Sie können alternativ auf das Stecknadelsymbol oben rechts in der Editor-Gruppe klicken oder **STRG+ALT+F bzw. CMD+ALT+F** drücken.

![Stecknadel in Visual Studio Code](../media/vscode-pin.png)

> [!NOTE]
> Wenn mehr als eine weitere Person an der Zusammenarbeitssitzung teilnimmt, werden Sie aufgefordert, den Teilnehmer auszuwählen, dem Sie folgen möchten.
>
>![Screenshot: Liste der Teilnehmer](../media/vscode-list-collaborators.png)

Da das Folgen an eine Editor-Gruppe gebunden ist, können Sie die Ansicht teilen oder ein Rasterlayout anwenden. So ist eine Gruppe verfügbar, die einem Teilnehmer folgt, und eine Gruppe, in der das nicht der Fall ist. So können Sie einem Teilnehmer passiv folgen und gleichzeitig unabhängig davon in der anderen Gruppe weiterarbeiten. Wenn eine Editor-Gruppe ausgewählt ist, können Sie auf einen Teilnehmer in der Teilnehmerliste klicken, damit die Gruppe diesem folgt.

![Visual Studio Code in der geteilten Ansicht mit Stecknadel](../media/vscode-follow-split.png)

In folgenden Fällen wird der Modus zum Folgen von Teilnehmern automatisch beendet, sodass Sie einfach mit Ihrer eigenen Arbeit beginnen können:

1. Wenn Sie die derzeit aktive Datei bearbeiten.
1. Wenn Sie eine andere Datei öffnen.
1. Wenn Sie die derzeit aktive Datei schließen.

Darüber hinaus können Sie das Folgen eines Teilnehmers explizit beenden, indem Sie erneut auf das Stecknadelsymbol klicken oder **STRG+ALT+F bzw. CMD+ALT+F** drücken.

## <a name="listing-participants"></a>Auflisten der Teilnehmer

Die Teilnehmerliste im Live Share-Explorer bzw. in der benutzerdefinierten Live Share-Registerkarte bietet eine schnelle Übersicht über die Teilnehmer der Zusammenarbeitssitzung. In dieser Ansicht werden alle Teilnehmer der Sitzung angezeigt.

![Screenshot: Benutzer in der Sitzung](../media/vscode-explorer-view.png)

Wenn Sie auf einen Teilnehmer in dieser Liste klicken, folgen Sie diesem in Ihrer aktiven Editor-Gruppe.

Alternativ können Sie **STRG+UMSCHALT+P bzw. CMD+UMSCHALT+P** drücken und den Befehl „Live Share: List Participants“ (Live Share: Teilnehmer auflisten) auswählen oder auf das Statusleistenelement **klicken**, das die Anzahl der Teilnehmer in der Sitzung darstellt.

![Screenshot: Statusleistensymbol für Benutzer in der Sitzung](../media/vscode-user-status.png)

Daraufhin wird eine Liste aller Teilnehmer der Sitzung angezeigt. Anders als beim Stecknadelsymbol wird diese Liste auch angezeigt, wenn nur eine weitere Person an der Sitzung teilnimmt. So haben Sie immer einen schnellen Überblick darüber, wo die anderen Teilnehmer sich befinden. Sie können auch einfach wie beim Stecknadelsymbol in der Liste auf einen der Teilnehmer klicken, um diesem zu folgen. Drücken Sie die ESC-Taste, wenn Sie die Sitzung stattdessen beenden möchten.

## <a name="focusing"></a>Hinzuziehen von Teilnehmern

Gelegentlich ist es erforderlich, dass Teilnehmer einer Zusammenarbeitssitzung einen Blick auf einen bestimmten Bearbeitungsstand werfen. In Live Share können Sie mit einer Benachrichtigung andere Teilnehmer hinzuziehen, was es diesen erleichtert, Ihnen ebenfalls zu folgen.

Öffnen Sie die benutzerdefinierte Live Share-Registerkarte über die Aktivitätsleiste von Visual Studio Code, oder wechseln Sie zum Live Share-Explorer, und klicken Sie auf das Symbol zum Hinzuziehen von Teilnehmern.

![Symbol für das Hinzuziehen-Viewlet](../media/vscode-focus-viewlet.png)

Wenn Sie diesen Befehl ausführen, erhalten alle Teilnehmer der Zusammenarbeitssitzung anschließend eine Benachrichtigung.

![Popupbenachrichtigung für Option „Teilnehmer hinzuziehen“](../media/vscode-focus-toast.png)

In dieser können sie einfach auf „Folgen“ klicken.

## <a name="co-debugging"></a>Gemeinsames Debuggen

Mit dem Feature für gemeinsames Debuggen steht in Visual Studio Live Share ein besonderes und leistungsstarkes Tool zur Verfügung. Mit diesem können Sie nicht nur gemeinsam Probleme beheben, sondern auch innerhalb einer Sitzung solche untersuchen, die möglicherweise umgebungsspezifisch sind. Dazu wird auf dem Gastgebercomputer eine freigegebene Debugsitzung bereitgestellt.

> **Sicherheitstipp:** Da alle Teilnehmer zu Dateien navigieren und diese bearbeiten können, haben Sie als Gastgeber die Möglichkeit, mit einer VSLS.JSON-Datei den Zugriff auf Dateien innerhalb eines Projekts einzuschränken. Beachten Sie außerdem, dass Teilnehmer beim Zugriff über eine Konsole oder REPL Befehle auf Ihrem Computer ausführen können. Sie sollten also nur gemeinsam mit Personen debuggen, denen Sie vertrauen. Wenn Sie Gast sind, sollten Sie berücksichtigen, dass Ihnen aufgrund dieser Einstellungen Debugergebnisse möglicherweise nicht angezeigt werden, wenn in Dateien mit Zugriffsbeschränkungen Anweisungen schrittweise ausgeführt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

Die Verwendung ist einfach:

1. Stellen Sie sicher, dass beim Gastgeber und beim Gast die richtige Erweiterung für das Debuggen installiert ist. (Technisch gesehen ist es nicht immer notwendig, aber im Allgemeinen hilfreich.)

2. Als Gastgeber sollten Sie [launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) konfigurieren, damit die Anwendung wie gewohnt über Visual Studio Code debuggt wird, sofern Sie das noch nicht getan haben. Eine spezielle Einrichtung ist nicht erforderlich.

3. Nun kann der Gastgeber das Debuggen wie gewohnt über die Schaltfläche auf der Registerkarte „Debuggen“ starten.

    ![Debugschaltfläche in Visual Studio Code](../media/vscode-debug-button.png)

    > [!TIP]
    > Sie können über Visual Studio Code auch an Visual Studio-Debugsitzungen teilnehmen und umgekehrt. Weitere Informationen finden Sie in der [Visual Studio-Anleitung zum gemeinsamen Debuggen](vs.md#co-debugging).

Nachdem der Debugger dem Debugprozess auf dem Gastgebercomputer angefügt wurde, werden auch alle Gäste automatisch angefügt. Auf dem Gastgebercomputer wird genau eine Debugsitzung ausgeführt, mit der alle Teilnehmer verbunden werden. Diese verfügen aber jeweils über eine eigene Ansicht.

![Visual Studio Code-Debugger angefügt](../media/vscode-debugger.png)

Der Debugprozess kann von allen Teilnehmern schrittweise ausgeführt werden. So können abwechselnd unterschiedliche Personen auf diesen zugreifen, ohne dass eine Zugriffssteuerung für die verschiedenen Teilnehmer erforderlich ist.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

Jeder Projektmitarbeiter kann unterschiedliche Variablen untersuchen, zu verschiedenen Dateien in der Aufrufliste wechseln und darüber hinaus Breakpoints hinzufügen oder entfernen. Mit Features zur gemeinsamen Bearbeitung können die Teilnehmer anschließend Debugschritte anderer Personen nachverfolgen. So können unterschiedliche Aspekte des Problems gleichzeitig untersucht werden, und bei Bedarf kann zum gemeinsamen Debuggen gewechselt werden.

> [!NOTE]
> In einer schreibgeschützten Zusammenarbeitssitzung können Gäste Anweisungen im Debugprozess nicht schrittweise ausführen. Sie können jedoch nach wie vor Breakpoints hinzufügen oder entfernen und Variablen untersuchen.

![Animation: gleichzeitiges Debuggen](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Anpassen des Visual Studio Code-Verhaltens für Beitritte zu Debugsitzungen

Als Gast werden Sie standardmäßig Debugsitzungen angefügt, wenn diese vom Gastgeber freigegeben werden. Dieses Verhalten kann in einigen Fällen störend wirken. Sie können es allerdings wie folgt ändern:

Bearbeiten Sie einfach **settings.json** (Datei > Einstellungen > Einstellungen), indem Sie eine der folgenden Zeilen hinzufügen, und starten Sie Visual Studio Code dann neu:

| Einstellung | Verhalten |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | Der Standardwert. Als Gast treten Sie automatisch allen freigegebenen Debugsitzungen bei, die vom Gastgeber gestartet werden. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Als Gast werden Sie aufgefordert, einer freigegebenen Debugsitzung beizutreten, wenn diese vom Gastgeber gestartet wird. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Als Gast müssen Sie Debugsitzungen manuell beitreten. Weitere Informationen finden Sie unter [Trennen und erneutes Anfügen](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Trennen und erneutes Anfügen

Als Gast können Sie das Debuggen vorübergehend anhalten. Klicken Sie in der Debugsymbolleiste auf das Stoppsymbol, um den Debugger zu trennen, ohne dabei den Gastgeber oder andere Gäste zu beeinflussen.

![Schaltfläche zum Beenden des Debuggens in Visual Studio Code](../media/vscode-debug-stop.png)

Wenn Sie die Einstellungen aktualisiert haben, sodass nicht mehr automatisch angefügt wird, oder wenn Sie später erneut anfügen möchten, können Sie hierfür **STRG+UMSCHALT+P bzw. CMD+UMSCHALT+P** drücken oder auf das Statusleistenelement für den Sitzungszustand **klicken** und „Attach to a Shared Debugging Session“ (An freigegebene Debugsitzung anfügen) auswählen.

![Debugger anfügen in Visual Studio Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Freigabe der ausgeführten Anwendung im Browser

In Visual Studio Code ist das Konzept eines bekannten Webanwendungsports für Projekttypen wie ASP.NET nicht wie in Visual Studio enthalten. Wenn Sie jedoch einer Zusammenarbeitssitzung beitreten, deren Gastgeber in Visual Studio arbeitet, wird Ihr Standardbrowser automatisch angezeigt, wenn das Debuggen gestartet wird, und automatisch mit den ausgeführten Anwendungen des Gastgebers verknüpft. Weitere Informationen finden Sie im Artikel zu [Visual Studio](vs.md#automatic-web-app-sharing).

Als Gastgeber können Sie hierfür die Anwendung oder andere Endpunkte wie RESTful-Dienste manuell freigeben, indem Sie das Feature „Share Local Server“ (Lokalen Server freigeben) verwenden. Gäste, die Visual Studio oder Visual Studio Code verwenden, können dann im Browser denselben localhost-Port öffnen, um die ausgeführte Anwendung anzuzeigen.  Weitere Informationen finden Sie unter [Freigeben eines Servers](#share-a-server).

## <a name="share-a-server"></a>Freigeben eines Servers

Als Zusammenarbeitssitzungs-Gastgeber müssen Sie in einigen Fällen eine Webanwendung oder andere lokal ausgeführte Server oder Dienste für Gäste freigeben. Diese reichen von RESTful-Endpunkten über Datenbanken bis hin zu anderen Servern. In Visual Studio Live Share können Sie eine lokale Portnummer angeben, sie optional benennen und anschließend für alle Gäste freigeben.

Der freigegebene Server ist dann auf demselben Port über die lokalen Computer der Gäste zugänglich. Wenn Sie beispielsweise einen Webserver freigegeben haben, **der auf Port 3000 ausgeführt wird**, können Gäste diesen auf ihrem **lokalen Computer** unter http://localhost:3000 erreichen. Dazu wird ein sicherer SSH- oder SSL-Tunnel zwischen dem Gastgeber und den Gästen erstellt und über den Dienst authentifiziert. So wird sichergestellt, dass nur Teilnehmer der Zusammenarbeitssitzung Zugriff haben.

> **Sicherheitstipp:** Als Gastgeber sollten Sie nur ganz bestimmte Ports für Gäste freigeben und Anwendungs- statt Systemports verwenden. Für Gäste verhalten sich freigegebene Ports so, als würde der Server oder Dienst auf dem lokalen Gastcomputer ausgeführt werden. Dies ist zwar sehr nützlich, kann aber auch riskant sein, wenn der falsche Port freigegeben wird.

Aus Sicherheitsgründen stehen nur Server, deren Ports Sie festlegen, für andere Gäste zur Verfügung. Als **Gastgeber** können Sie einen Server ganz einfach hinzufügen. Gehen Sie dabei folgendermaßen vor:

1. Öffnen Sie die benutzerdefinierte Live Share-Registerkarte über die Aktivitätsleiste von Visual Studio Code, oder wechseln Sie zum Live Share-Explorer, und klicken Sie auf den Eintrag „Server freigeben...“ oder auf das Symbol.

    ![Freigabe des lokalen Servers in Visual Studio Code](../media/vscode-share-local-server-viewlet.png)<br />

1. Geben Sie die Portnummer ein, auf der der Server ausgeführt wird, und ggf. einen Namen (optional).

    ![Screenshot: Aufforderung zur Eingabe der Portnummer](../media/vscode-enter-port.png)<br />

Das ist alles! Der Server wird nun auf dem Gastcomputer dem Localhost auf dem gleichen Port zugeordnet, falls dieser Port noch nicht verwendet wird.

Wird der Port hingegen auf dem Gastcomputer bereits verwendet, wird ein automatisch ein anderer ausgewählt. Als Gast können Sie im Live Share-Explorer oder über die benutzerdefinierte Live Share-Registerkarte in der Aktivitätsleiste von Visual Studio Code eine Liste der derzeit freigegebenen Ports aufrufen (nach Name, falls angegeben) und die Liste der freigegebenen Server anzeigen. Wenn Sie auf einen Eintrag klicken, wird dieser Server in Ihrem Browser geöffnet. Sie können auch mit der rechten Maustaste klicken und die Option auswählen, um die URL zum Server in die Zwischenablage zu kopieren.

![Zugriff auf lokalen Server in Visual Studio Code](../media/vscode-access-shared-server-viewlet.png)<br />

Beachten Sie, dass *Gäste aus Sicherheitsgründen nicht festlegen können*, welche Ports auf dem Computer des Gastgebers freigegeben werden.

Wenn Sie die Freigabe des lokalen Servers als Gastgeber **beenden** möchten, zeigen Sie auf den Eintrag für den Server in der Liste der freigegebenen Server im Live Share-Explorer bzw. auf der benutzerdefinierten Live Share-Registerkarte, und klicken Sie auf „Unshare server“ (Freigabe des Servers beenden).

![Freigabe des Servers in Visual Studio Code beenden](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Freigeben eines Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Als Gastgeber können Sie in Live Share für Gäste bei Bedarf ein Terminal freigeben. Das freigegebene Terminal kann schreibgeschützt oder vollständig für die Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Sie können Gästen die Terminalausgabe oder das Terminal selbst zugänglich machen. Im letztgenannten Fall können Gäste Tests und Builds ausführen oder auch umgebungsspezifische Probleme selektieren, die nur auf Ihrem Computer auftreten.

Terminals werden jedoch standardmäßig **nicht** freigegeben, da Gäste in jedem Fall Leseberechtigungen für die Ausgabe der ausgeführten Befehle erhalten und darüber hinaus eventuell auch selbst Befehle ausführen können. Auf diese Weise können Sie in lokalen Terminals ohne Risiken Befehle ausführen und Terminals nur bei Bedarf freigeben. Des Weiteren haben nur Gastgeber die Möglichkeit, freigegebene Terminals zu starten. So werden Gäste daran gehindert, ein eigenes Terminal aufzurufen und unerwartete Befehle auszuführen, die Sie nicht überwachen können.

Als Gastgeber können Sie ein Terminal freigeben, indem Sie die benutzerdefinierte Live Share-Registerkarte über die Aktivitätsleiste von Visual Studio Code öffnen oder zum Live Share-Explorer wechseln und auf den Eintrag „Server freigeben...“ oder auf das Symbol klicken.

![Terminal freigeben in Visual Studio Code](../media/vscode-share-terminal-viewlet.png)<br />

Nun können Sie aus dem Menü ein Terminal mit Leseberechtigungen oder mit Lese-/Schreibberechtigungen auswählen. Im zweiten Fall kann jede Person einschließlich des Gastgebers Befehle im Terminal eingeben. Dadurch können unerwünschte Gastaktionen leicht unterbunden werden. **Die Lese- und Schreibberechtigungen sollten Sie aus Sicherheitsgründen ausschließlich Gästen bereitstellen, die darauf angewiesen sind**. Terminals mit Leseberechtigungen sollten Sie in Szenarios einsetzen, in denen Gäste nur die Ausgabe der von Ihnen ausgeführten Befehle sehen dürfen. Beachten Sie, dass der Gast mit dem Lese-/Schreibzugriff denselben Zugriff auf Ihren Terminal wie Sie erhält und auch jeden beliebigen Befehl auf Ihrem Computer ausführen kann.

> [!NOTE]
> Wenn sich die Zusammenarbeitssitzung im schreibgeschützten Modus befindet, können nur Terminals, für die Leseberechtigungen vorliegen, vom Gastgeber freigegeben werden.

![Auswahl von Lese- oder Lese-/Schreibzugriff](../media/vscode-share-terminal-ro-rw.png)<br />

Nachdem Sie die Art des freigegebenes Terminals ausgewählt haben, das gestartet werden soll, wird ein neues freigegebenes Terminal auf der Registerkarte „Terminals“ in Visual Studio Code angezeigt.

![Ausgeführtes freigegebenes Terminal](../media/vscode-share-terminal-up.png)<br />

Wenn mehrere Terminals freigegeben wurden oder Sie eine andere Registerkarte fokussiert haben, können Sie ein bestimmtes Terminal fokussieren, indem Sie auf den entsprechenden Eintrag in der Liste der freigegebenen Terminals klicken.

![Fokussieren eines freigegebenen Terminals](../media/vscode-shared-terminal-focus.png)<br />

Sie können die Terminalsitzung beenden, indem Sie „exit“ eingeben und das Terminalfenster schließen oder indem Sie auf das Symbol zum Beenden der Freigabe des Terminals im Live Share-Explorer oder auf der benutzerdefinierten Live Share-Registerkarte klicken. Die Verbindung wird dann für alle Teilnehmer getrennt.

## <a name="session-states"></a>Sitzungszustände

Nachdem Sie eine Zusammenarbeitssitzung gestartet haben oder dieser beigetreten sind und Zugriff auf freigegebene Inhalte haben, ändern sich die Statusleistenelemente in Visual Studio Live Share so, dass der Zustand der aktiven Zusammenarbeitssitzung angezeigt wird.

Folgende Zustände sind möglich:

| Zustand | Statusleiste | Beschreibung |
|-------|--------------------|-------------|
| Inaktiv | ![Zustand „Inaktiv“ in Visual Studio Code](../media/vscode-status-share.png) | Es ist keine aktive Zusammenarbeitssitzung vorhanden, und keine Inhalte werden freigegeben. |
| Gastgeber: Wird freigegeben... | ![Zustand „Wird freigegeben...“ in Visual Studio Code](../media/vscode-status-sharing.png)| Eine Zusammenarbeitssitzung wird gestartet, und Inhalte werden in Kürze freigegeben. |
| Gastgeber: Freigabe | ![Zustand „Freigabe aktiv“ in Visual Studio Code ](../media/vscode-status-active.png)| Eine aktive Zusammenarbeitssitzung ist vorhanden, und Inhalte werden freigegeben. |
| Gastgeber: Schreibgeschützt freigeben | ![Zustand „Schreibgeschützt freigeben“ in Visual Studio Code](../media/vscode-status-sharing-read-only.png)| Eine schreibgeschützte Zusammenarbeitssitzung wird freigegeben. |
| Gast: Beitritt zur Sitzung | ![Zustand „Beitritt zur Sitzung“ in Visual Studio Code](../media/vscode-status-joining.png)| Ein Teilnehmer tritt einer vorhandenen Zusammenarbeitssitzung bei. |
| Gast: Beigetreten | ![Zustand „Beigetreten“ in Visual Studio Code](../media/vscode-status-active.png) | Ein Teilnehmer ist einer aktiven Zusammenarbeitssitzung beigetreten und empfängt freigegebene Inhalte. |
| Gast: Schreibgeschützt beigetreten | ![Zustand „Schreibgeschützt beigetreten“ in Visual Studio Code](../media/vscode-status-joined-read-only.png) | Ein Teilnehmer ist einer aktiven schreibgeschützten Zusammenarbeitssitzung beigetreten. |

## <a name="guest-limitations"></a>Einschränkungen für Gäste

Aktuell treten bei Verwendung der Gastfeatures einige Probleme auf. Zusammenarbeitssitzungs-Gastgeber können allerdings weiterhin alle Funktionen ihres bevorzugten Tools verwenden. Über die folgenden Links erhalten Sie weitere Informationen:

- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)
- [Problembehandlung](../troubleshooting.md)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie weitere Informationen benötigen, sehen Sie sich diese zusätzlichen Artikel an.

- [Schnellstart: Freigeben Ihres ersten Projekts](../quickstart/share.md)
- [Schnellstart: Beitreten zu Ihrer ersten Sitzung](../quickstart/share.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](vs.md)
- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Details zur Linux-Installation](../reference/linux.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

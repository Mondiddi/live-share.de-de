---
title: Zusammenarbeiten in Visual Studio – Visual Studio Live Share | Microsoft-Dokumentation
description: Vorgehensweisen zur Zusammenarbeit in Visual Studio und Live Share
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 65c48d1a95cc94bc7505c185be353e437e3c5ba1
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062305"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Vorgehensweise: Zusammenarbeiten in Visual Studio

In diesem Artikel erfahren Sie, wie die Zusammenarbeit in Visual Studio mithilfe von Live Share funktioniert. Dabei lernen Sie einige Features der Visual Studio Live Share-Erweiterung für Visual Studio kennen.

Beachten Sie, dass an allen hier beschriebenen Zusammenarbeitsaktivitäten ein einziger **Zusammenarbeitssitzungs-Gastgeber** und mindestens ein **Gast** beteiligt sind. Der Gastgeber ist die Person, die die Zusammenarbeitssitzung gestartet hat, und jede Person, die ihr beitritt, ist ein Gast.

*Wenn Sie an einer kurzen Zusammenfassung interessiert sind, finden Sie in den Schnellstarts zum [Freigeben](../quickstart/share.md) und [Beitreten](../quickstart/join.md) weitere Informationen.*

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

## <a name="installation"></a>Installation

Installieren Sie zuerst **Visual Studio 2019** oder **Visual Studio 2017 15.6 oder höher** auf Windows 7, 8.1. oder 10. *Empfohlen wird jedoch Visual Studio 15.7 oder höher, da Sie damit lokale Änderungen rückgängig machen oder wiederholen können.*

Die ersten Schritte sind einfach:

Für Visual Studio 2019:
1. Installieren Sie eine beliebige Edition von [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).
2. Installieren Sie eine [unterstützte Workload](../reference/platform-support.md). (z.B. ASP.NET, .NET Core, C++, Python und/oder Node.js)
3. Visual Studio Live Share wird mit diesen Workloads standardmäßig installiert.

Für Visual Studio 2017:
1. Installieren Sie [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/vs/older-downloads/).
2. Installieren Sie eine [unterstützte Workload](../reference/platform-support.md). (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)
3. [Laden Sie die Visual Studio Live Share-Erweiterung aus dem Marketplace herunter](https://aka.ms/vsls-dl/vs), und installieren Sie sie.

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

[![Herunterladen](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Anmelden

Wenn Sie mit anderen Personen zusammenarbeiten möchten, müssen Sie sich in Visual Studio Live Share anmelden, damit diese wissen, wer Sie sind. Dies ist nur eine Sicherheitsmaßnahme. Sie willigen dadurch **nicht** ein, an Marketing- oder anderen Marktforschungsaktivitäten teilzunehmen. Sie können sich mit einem persönlichen Microsoft-Konto (z. B. @outlook.com), einem Geschäfts-, Schul- oder Unikonto von Microsoft (über AAD) oder mit einem GitHub-Konto anmelden. Die Anmeldung ist unkompliziert.

Standardmäßig wird in Visual Studio Ihr [Personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) verwendet. Wenn Sie bereits bei Visual Studio angemeldet sind, können Sie diesen Schritt überspringen. Andernfalls melden Sie sich wie gewohnt an.

![Anmeldeschaltfläche in Visual Studio](../media/vs-sign-in-button.png)


Wenn Sie zur Anmeldung nicht Ihr [Visual Studio-Personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) verwenden möchten, wechseln Sie zu **Extras &gt; Optionen &gt; Live Share &gt; Benutzerkonto**, um andere Anmeldeinformationen festzulegen.

![Option „Extras > Optionen > Live Share“ in Visual Studio](../media/vs-tools-options-new.png)

Wenn Sie **External Account** (Externes Konto) auswählen, können Sie ein Konto wie GitHub festlegen, das nicht durch das Personalisierungsfeature von Visual Studio unterstützt wird. Bei der ersten Nutzung des Live Share-Features wird ein Browser geöffnet, in dem Sie die Anmeldung abschließen können.
>[!Tip]
>Wussten Sie, dass man unter **Extras &gt; Optionen &gt; Live Share &gt; Allgemein** alle Live Share-Standardeinstellungen anzeigen kann? Passen Sie die Oberfläche für Zusammenarbeit an Ihre Anforderungen an. Sie können auch alle neuen Live Share-Features ausprobieren, indem Sie innerhalb der allgemeinen Live Share-Einstellungen **Erweitert &gt; Features &gt; Insider** auswählen.  

Falls Probleme auftreten, finden Sie in der [Problembehandlung](../troubleshooting.md#sign-in) weitere Tipps.

## <a name="share-a-project"></a>Freigeben eines Projekts

Führen Sie nach dem Herunterladen und Installieren von Visual Studio Live Share die folgenden Schritte aus, um eine Zusammenarbeitssitzung zu starten und einen Kollegen einzuladen.

1. **Melden Sie sich an:**

    Nach der Anmeldung sind Sie jetzt bereit, Ihre eigene Zusammenarbeitssitzung zu starten.
    Sie sind nicht angemeldet? Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Öffnen Sie eine Projektmappe, ein Projekt oder einen Ordner:**

    Öffnen Sie wie gewohnt einen Ordner, ein Projekt oder eine Projektmappe, die Sie für Gäste freigeben möchten.

3. **Aktualisieren Sie ausgeblendete oder ausgeschlossene Dateien (optional):**

    In Live Share werden Dateien und Ordner, auf die in GITIGNORE-Dateien in Ihrem Projekt verwiesen wird, standardmäßig für Gäste **ausgeblendet**. Das **Ausblenden** einer Datei verhindert, dass sie in der Dateistruktur angezeigt wird. Durch das **Ausschließen** wird eine Übertragung unterbunden, was auch für Vorgänge wie beispielsweise Debuggen gilt. Wenn Sie unterschiedliche Dateien ausblenden/ausschließen möchten, kann eine **VSLS.JSON**-Datei Ihrem Projekt mit diesen Einstellungen hinzugefügt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

4. **Starten Sie eine Zusammenarbeitssitzung:**

    Klicken Sie jetzt einfach oben rechts auf die Schaltfläche „Live Share“, um eine Live Share-Sitzung zu starten.     Ein Link zur Zusammenarbeitssitzung wird automatisch in die Zwischenablage kopiert und kann weitergegeben werden. 

    ![Schaltfläche „Freigeben“ in Visual Studio](../media/vs-share-button.png)

    Nachdem Sie Ihre Zusammenarbeitssitzung zum ersten Mal gestartet haben, wird Ihnen ein Live Share-Toolfenster angezeigt. Docken Sie dieses Fenster an, um sicherzustellen, dass es beim nächsten Start einer Live Share-Sitzung angezeigt wird.

   ![VS Live Share-Toolfenster](../media/vs-live-share-tool-window.png)

    > [!NOTE]
    > Möglicherweise werden Sie von der Firewallsoftware Ihres Desktops gefragt, ob Sie zulassen möchten, dass der Live Share-Agent bei Ihrer ersten Freigabe einen Port öffnet. Dies zuzulassen, ist Ihnen völlig freigestellt, ermöglicht aber einen gesicherten „direkten Modus“ zur Leistungsverbesserung, wenn sich die Person, mit der Sie zusammenarbeiten, in demselben Netzwerk wie Sie befindet. Details dazu finden Sie unter [Changing the connection mode (Ändern des Verbindungsmodus)](../reference/connectivity.md#changing-the-connection-mode).

5. **Aktivieren Sie den schreibgeschützten Modus (optional):**

    Sobald Sie Ihre Zusammenarbeitssitzung gestartet haben, können Sie sie als schreibgeschützt festlegen und so verhindern, dass Gäste Änderungen am freigegebenen Code vornehmen.

    Nach der Freigabe erhalten Sie eine Benachrichtigung mit der Information, dass der Einladungslink in Ihre Zwischenablage kopiert wurde. Dann können Sie die Option auswählen, dass die Sitzung schreibgeschützt werden soll.

    ![Schreibgeschützter Modus in Visual Studio](../media/vs-read-only-notification.png)

6. **Senden Sie den Link an eine andere Person:**

    Senden Sie den Link per E-Mail, Slack, Skype usw. an die Personen, die Sie einladen möchten. Bitte beachten Sie: Angesichts der Zugriffsebene, die Live Share-Sitzungen Gästen bereitstellen können, **sollten Sie Inhalte nur für vertrauenswürdige Personen freigeben** und die Folgen Ihrer Freigabe durchdenken.

    > **Sicherheitstipp:** Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

    Wenn der von Ihnen eingeladene Gast Fragen hat, enthält der Artikel [Quickstart: Join your first session (Schnellstart: Beitreten einer Sitzung)](../quickstart/join.md) einige weitere Informationen zum Einrichten und Ausführen einer Sitzung als Gast.

7. **Genehmigen Sie den Gast (optional):**

    Standardmäßig treten Gäste Ihrer Zusammenarbeitssitzung automatisch bei, und Sie werden benachrichtigt, wenn sie zur Zusammenarbeit mit Ihnen bereit sind. Durch diese Benachrichtigung haben Sie die Möglichkeit, den Gast aus der Sitzung zu entfernen. Sie können aber auch festlegen, dass eine Genehmigung erforderlich ist, sobald eine Person der Sitzung beitritt.

    Ändern Sie dazu den Wert der Option **Extras > Optionen > Live Share > Gastgenehmigung erforderlich** in „TRUE“, um das Feature zu aktivieren. Wenn anschließend ein Gast der Sitzung beitreten möchte, erhalten Sie eine Benachrichtigung mit einer Genehmigungsanforderung.

    ![Genehmigungsanforderung für einen Beitritt zur Sitzung in Visual Studio](../media/vs-join-approval.png)

    Unter [Invitations and join access (Konfigurieren von Einladungen und Beitritten)](../reference/security.md#invitations-and-join-access) finden Sie weitere Informationen zur Sicherheit von Einladungen.

8. **Verwalten Ihrer Live Share-Sitzung**
    
    Nachdem Ihr Gast den Link zur freigegebenen Sitzung in VS Code oder Visual Studio geöffnet hat, wird er unter den Teilnehmern im Live Share-Toolfenster aufgeführt. Neben dem Namen können Sie jetzt sehen, in welcher Datei sich Ihr Gast gerade befindet.  
    
    ![VS Live Share-Toolfenster](../media/vs-live-share-tool-window-participant.png)

    Das Live Share-Toolfenster ermöglicht Ihnen den Zugriff auf alle wichtigen Features, um Ihre Sitzung an einem Ort zu verwalten. 

    > [!TIP]
    > Wird das Live Share-Toolfenster während der Sitzungen nicht mehr angezeigt? Sie finden es jederzeit unter **Ansicht &gt; Weitere Fenster &gt; Live Share**!

### <a name="ending-the-collaboration-session"></a>Beenden der Zusammenarbeitssitzung

Als Gastgeber können Sie die Freigabe und die Zusammenarbeitssitzung beenden, indem Sie auf die Schaltfläche mit dem Sitzungszustand rechts oben und anschließend auf „End Collaboration Session“ (Zusammenarbeitssitzung beenden) klicken.

![Freigabe beenden](../media/vs-stop-sharing.png)

Alle Gäste werden benachrichtigt, dass die Sitzung beendet wurde. Anschließend können sie nicht mehr auf Inhalte zugreifen, und alle temporären Dateien werden automatisch gelöscht.

Falls bei der Freigabe Probleme auftreten, sollten Sie sich die [Problembehandlung](../troubleshooting.md#share-and-join) ansehen.

## <a name="join-a-collaboration-session"></a>Beitreten einer Zusammenarbeitssitzung

Nach dem Herunterladen und Installieren von Visual Studio Live Share können Gäste in wenigen Schritten einer Zusammenarbeitssitzung beitreten. Dazu können sie entweder den [Browser](#join-via-the-browser) nutzen oder [manuell](#join-manually) beitreten.

> **Sicherheitstipp:** Als Gast, der einer Zusammenarbeitssitzung beitritt, ist es wichtig zu verstehen, dass Gastgeber Ihren Zugriff auf bestimmte Dateien oder Features einschränken können. Möchten Sie die Sicherheitsauswirkungen einiger Live Share-Features und -Einstellungen verstehen? Dann lesen Sie den Artikel [Sicherheit](../reference/security.md).

### <a name="join-via-the-browser"></a>Beitreten mithilfe des Browsers

Die einfachste Möglichkeit, einer Zusammenarbeitssitzung beizutreten, besteht darin, einen Link in einem Webbrowser zu öffnen. Gehen Sie dazu folgendermaßen vor:

1. **Melden Sie sich an:**

    Melden Sie sich nach der Installation der Live Share-Erweiterung an, damit andere Projektmitarbeiter wissen, wer Sie sind. Standardmäßig wird in Visual Studio Ihr Personalisierungskonto verwendet. Sie können diesen Schritt also eventuell überspringen.

    Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Klicken Sie auf den Einladungslink, oder öffnen Sie ihn im Browser:**

    Öffnen Sie jetzt den Einladungslink in einem Browser (oder öffnen Sie ihn erneut darin).

    > **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, werden Ihnen Links zum Extension Marketplace angezeigt. Installieren Sie die Erweiterung, starten Sie ihr Tool neu, und wiederholen Sie den Vorgang.

    Sie sollten benachrichtigt werden, dass der Browser ein Live Share-fähiges Tool starten möchte. Wenn Sie zulassen, dass er Ihr ausgewähltes Tool startet, werden Sie gleich nach dem Start mit der Zusammenarbeitssitzung verbunden.

    ![Seite „Beitreten“](../media/join-page.png)

    Wenn der Gastgeber offline ist, werden Sie an diesem Punkt entsprechend benachrichtigt. Dann können Sie Kontakt mit dem Gastgeber aufnehmen und ihn um erneute Freigabe bitten.

    > [!NOTE]
    > Noch immer Probleme? Unter [Manuelles Beitreten](#join-manually) finden Sie weitere Informationen.

3. **Zusammenarbeiten:**

    Damit haben Sie alle erforderlichen Schritte abgeschlossen. Nach einigen Augenblicken wird die Verbindung hergestellt, und Sie können mit anderen Personen zusammenarbeiten.

    Die Schaltfläche „Live Share“ wird zudem in den Sitzungszustand geändert. Informationen zu [Sitzungszuständen](#session-states) finden Sie weiter unten.

    Anschließend werden Sie automatisch zur Datei weitergeleitet, die der Gastgeber aktuell bearbeitet.

### <a name="join-manually"></a>Manuelles Beitreten

Sie können einer Sitzung auch manuell, also ohne einen Webbrowser, beitreten. Dies kann in Situationen nützlich sein, in denen das Tool, das Sie verwenden möchten, bereits ausgeführt wird oder Sie ein anderes Tool als sonst üblich nutzen wollen. Auch bei Problemen mit Einladungslinks kann ein Beitritt ohne Webbrowser sinnvoll sein. Ein manueller Beitritt ist leicht mit den folgenden Schritten möglich:

1. **Melden Sie sich an:**

    Melden Sie sich nach der Installation der Live Share-Erweiterung an, damit andere Projektmitarbeiter wissen, wer Sie sind. Standardmäßig wird in Visual Studio Ihr Personalisierungskonto verwendet. Sie können diesen Schritt also eventuell überspringen.

    Weitere Informationen finden Sie unter [Anmelden](#sign-in).

2. **Verwenden Sie den Beitrittsbefehl:**

    Navigieren Sie einfach zu **Datei > Live Share-Sitzung beitreten...** .

    ![Beitrittsmenü in Visual Studio](../media/vs-join.png)

3. **Fügen Sie den Einladungslink ein:**

    Fügen Sie die Einladungs-URL ein, die Sie erhalten haben, und bestätigen Sie diese.

4. **Zusammenarbeiten:**

    Das ist alles! Nach einigen Augenblicken sollte eine Verbindung mit der Zusammenarbeitssitzung hergestellt werden.

    Die Schaltfläche „Live Share“ wird zudem in den Sitzungszustand geändert. Informationen zu [Sitzungszuständen](#session-states) finden Sie weiter unten.

    Anschließend werden Sie automatisch zu den Inhalten weitergeleitet, die der Gastgeber aktuell bearbeitet.

### <a name="leave-the-collaboration-session"></a>Verlassen der Zusammenarbeitssitzung

Als Gast können Sie die Zusammenarbeitssitzung verlassen, ohne diese für andere Personen zu beenden. Schließen Sie dazu das Tool, oder klicken Sie auf die Schaltfläche mit dem Sitzungszustand und anschließend auf „Leave Collaboration Session“ (Zusammenarbeitssitzung verlassen).

![Beitrittsmenü in Visual Studio](../media/vs-leave-session.png)

Alle temporären Dateien werden automatisch gelöscht. Weitere Aktionen sind nicht erforderlich.

Falls während des Beitretens Probleme auftreten, sollten Sie sich die [Problembehandlung](../troubleshooting.md#share-and-join) ansehen.

## <a name="co-editing"></a>Gemeinsame Bearbeitung

Nachdem ein Gast einer Zusammenarbeitssitzung beigetreten ist, können alle Projektmitarbeiter in Echtzeit sämtliche Bearbeitungen und Auswahlaktionen anderer Personen sehen. Dazu müssen sie nur im Datei-Explorer eine Datei auswählen und mit der Bearbeitung beginnen. Sowohl Gastgebern und als auch Gästen werden Änderungen unmittelbar angezeigt. Diese Personen können außerdem selbst Inhalte beitragen, die anschließend wiederholt bearbeitet werden können, wodurch sich Lösungen schnell erarbeiten lassen.

> [!NOTE]
> In einer schreibgeschützten Zusammenarbeitssitzung können Gäste keine Dateien bearbeiten. Der Gastgeber kann für die [Freigabe den schreibgeschützten Modus aktivieren](#share-a-project). Gäste erkennen eine schreibgeschützte Sitzung am [Sitzungszustand](#session-states).

![Screenshot: gemeinsame Bearbeitung](../media/vs-coedit.png)

> [!NOTE]
> Bei der gemeinsamen Bearbeitung kann es für bestimmte Sprachen zu Einschränkungen kommen. Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

Zusätzlich zu Cursors und Bearbeitungen sind auch Auswahlaktionen in einer Datei für alle Teilnehmer sichtbar. Dadurch können mögliche Probleme hervorgehoben und Vorschläge vermittelt werden.

![Screenshot: Hervorhebung](../media/vs-highlight.png)

Sie und weitere Teilnehmer können darüber hinaus zu allen Dateien eines freigegebenen Projekts navigieren. Sie können Dateien entweder gemeinsam oder unabhängig voneinander bearbeiten. Dadurch können Sie wahlweise Probleme untersuchen, kleinere Korrekturen vornehmen oder intensiv mit anderen Personen zusammenarbeiten.

> [!NOTE]
> Live Share öffnet Dateien standardmäßig auch außerhalb der freigegebenen Projektmappe. Wenn Sie dieses Feature deaktivieren möchten, legen Sie unter „Extras &gt; Optionen &gt; Live Share“ als Wert für die Option „Externe Dateien freigeben“ den Wert „FALSE“ fest.

Bearbeitungen werden auf dem Computer des Gastgebers gespeichert. Nach der Bearbeitung müssen Dateien deswegen nicht synchronisiert, gepusht oder an andere Personen gesendet werden.

> **Sicherheitstipp:** Da alle Teilnehmer zu Dateien navigieren und diese bearbeiten können, haben Sie als Gastgeber die Möglichkeit, mit einer VSLS.JSON-Datei den Zugriff auf Dateien innerhalb eines Projekts einzuschränken. Wenn Sie Gast sind, sollten Sie bedenken, dass einige Dateien aufgrund dieser Einstellungen möglicherweise nicht angezeigt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

### <a name="changing-participant-flag-behaviors"></a>Ändern des Flagverhaltens für Teilnehmer

In der Standardeinstellung zeigt Visual Studio Live Share automatisch ein Flag neben dem Teilnehmercursor an, wenn mit diesem auf etwas gezeigt oder wenn dieser bewegt wird. Dasselbe gilt bei Bearbeitungen oder Hervorhebungen. In einigen Fällen empfiehlt es sich, dieses Verhalten zu ändern. Gehen Sie hierzu wie folgt vor:

1. Wechseln Sie zu **Extras > Optionen > Live Share**.
2. Legen Sie für die Option **Flagsichtbarkeit** einen der folgenden Werte fest:

| Option | Verhalten |
|--------|----------|
| OnHoverOnly | Das Flag wird nur angezeigt, wenn Sie mit dem Cursor auf etwas zeigen. |
| OnHoverOrActivity | Dies ist die Standardeinstellung. Das Flag wird angezeigt, wenn mit dem Cursor auf etwas gezeigt oder wenn dieser bewegt wird. Zusätzlich wird es bei Bearbeitungen oder Hervorhebungen angezeigt. |
| Always | Das Flag ist immer sichtbar.

## <a name="following"></a>Folgen von Teilnehmern

Nachdem Sie einer Zusammenarbeitssitzung beigetreten sind, sehen Sie die Initialen der Teilnehmer oben rechts im Editor neben der Anmeldeschaltfläche. Wenn Sie auf die Initialen zeigen, werden alle Informationen zu diesem Teilnehmer angezeigt.

![Screenshot: Benutzer](../media/vs-person.png)

Manchmal müssen Sie ein Problem erläutern oder eine Lösung entwerfen, die sich über mehrere Dateien oder Codestellen erstreckt. In diesen Fällen kann es hilfreich sein, einem Kollegen vorübergehend zu folgen, während er das Projekt bearbeitet. Aus diesem Grund folgen Sie als Gast beim Beitritt zu einer Zusammenarbeitssitzung automatisch dem Gastgeber. Wenn Sie einem Teilnehmer folgen, werden in Ihrem Editor die geöffnete Datei sowie die Cursor- und Scrollposition synchronisiert.

> [!NOTE]
> Live Share öffnet Dateien standardmäßig auch außerhalb der freigegebenen Projektmappe. Wenn Sie dieses Feature deaktivieren möchten, legen Sie unter „Extras &gt; Optionen &gt; Live Share“ als Wert für die Option „Externe Dateien freigeben“ den Wert „FALSE“ fest.

Sie können den Modus zum Folgen von Teilnehmern beenden und selbst mit dem Bearbeiten beginnen, wenn Sie eine der folgenden Aktionen ausführen:

1. Sie nehmen eine Bearbeitung vor, bewegen den Cursor oder treffen eine Auswahl.
2. Sie wählen eine andere Datei aus.

Wenn Sie einer Person nicht mehr folgen möchten, können Sie auf ihre Initialen oben rechts klicken. Dadurch wird der Kreis, der darauf hinweist, dass Sie dieser Person folgen, nicht mehr angezeigt.

![Eine Person folgt dem Visual Studio-Teilnehmer](../media/vs-pinned.png) ![Eine Person folgt dem Visual Studio-Teilnehmer nicht](../media/vs-pin-hover.png)

Sie können innerhalb der Zusammenarbeitssitzung auf die Initialen aller angezeigten Gastgeber oder Gäste klicken, um diesen zu folgen. Wenn Sie stattdessen nur zur Bearbeitungsstelle einer Person wechseln möchten, ohne dieser zu folgen, genügt ein Doppelklick auf die Initialen.

## <a name="focusing"></a>Hinzuziehen von Teilnehmern

Gelegentlich ist es erforderlich, dass Teilnehmer einer Zusammenarbeitssitzung einen Blick auf einen bestimmten Bearbeitungsstand werfen. In Live Share können Sie mit einer Benachrichtigung andere Teilnehmer hinzuziehen, was es diesen erleichtert, Ihnen ebenfalls zu folgen.

Klicken Sie auf die Schaltfläche mit dem Sitzungszustand oben rechts und anschließend auf „Teilnehmer hinzuziehen“.

![Menüoption „Teilnehmer hinzuziehen“](../media/vs-focus.png)

Alle Teilnehmer der Zusammenarbeitssitzung erhalten anschließend eine Benachrichtigung.

![Popupbenachrichtigung für Option „Teilnehmer hinzuziehen“](../media/vs-focus-toast.png)

In dieser können sie einfach auf „Folgen“ klicken.

## <a name="co-debugging"></a>Gemeinsames Debuggen

Mit dem Feature für gemeinsames Debuggen steht in Visual Studio Live Share ein besonderes und leistungsstarkes Tool zur Verfügung. Mit diesem können Sie nicht nur gemeinsam Probleme beheben, sondern auch innerhalb einer Sitzung solche untersuchen, die möglicherweise umgebungsspezifisch sind. Dazu wird auf dem Gastgebercomputer eine freigegebene Debugsitzung bereitgestellt.

> **Sicherheitstipp:** Da alle Teilnehmer zu Dateien navigieren und diese bearbeiten können, haben Sie als Gastgeber die Möglichkeit, mit einer VSLS.JSON-Datei den Zugriff auf Dateien innerhalb eines Projekts einzuschränken. Beachten Sie außerdem, dass Teilnehmer beim Zugriff über eine Konsole oder REPL Befehle auf Ihrem Computer ausführen können. Sie sollten also nur gemeinsam mit Personen debuggen, denen Sie vertrauen. Wenn Sie Gast sind, sollten Sie berücksichtigen, dass Ihnen aufgrund dieser Einstellungen Debugergebnisse möglicherweise nicht angezeigt werden, wenn in Dateien mit Zugriffsbeschränkungen Anweisungen schrittweise ausgeführt werden. Die Details dazu finden Sie unter [Steuern von Dateizugriff und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility).

Die Nutzung ist unkompliziert. Der Zusammenarbeitssitzungs-Gastgeber startet das Debuggen wie gewohnt in Visual Studio.

![Debugschaltfläche in Visual Studio](../media/vs-debug-button.png)

Nachdem der Debugger auf dem Gastgebercomputer angefügt wurde, werden auch alle Gäste automatisch angefügt. Auf dem Gastgebercomputer wird genau eine Debugsitzung ausgeführt, mit der alle Teilnehmer verbunden werden. Diese verfügen aber jeweils über eine eigene Ansicht.

> [!TIP]
> Wenn Sie die Einstellungen für das gemeinsame Debuggen konfigurieren möchten, können Sie das Standardverhalten unter **Extras > Optionen > Live Share** ändern.

![Visual Studio-Debugger angefügt](../media/vs-debugger.png)

Der Debugprozess kann von allen Teilnehmern schrittweise ausgeführt werden. So können abwechselnd unterschiedliche Personen auf diesen zugreifen, ohne dass eine Zugriffssteuerung für die verschiedenen Teilnehmer erforderlich ist.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

Jeder Projektmitarbeiter kann unterschiedliche Variablen untersuchen, zu verschiedenen Dateien in der Aufrufliste wechseln und darüber hinaus Breakpoints hinzufügen oder entfernen. Mit Features zur gemeinsamen Bearbeitung können die Teilnehmer anschließend Debugschritte anderer Personen nachverfolgen. So können unterschiedliche Aspekte des Problems gleichzeitig untersucht werden, und bei Bedarf kann zum gemeinsamen Debuggen gewechselt werden.

> [!NOTE]
> In einer schreibgeschützten Zusammenarbeitssitzung können Gäste Anweisungen im Debugprozess nicht schrittweise ausführen. Sie können jedoch nach wie vor Breakpoints hinzufügen oder entfernen und Variablen untersuchen.

> [!TIP]
> Sie können über Visual Studio auch an VS Code-Debugsitzungen teilnehmen und umgekehrt. Weitere Informationen finden Sie in der [Visual Studio-Anleitung zum gemeinsamen Debuggen](vscode.md#co-debugging).

### <a name="automatic-web-app-sharing"></a>Automatische Web-App-Freigabe

Wenn bei Web-App-Projekten in ASP.NET das Gastgeberprojekt so konfiguriert ist, dass automatisch ein Webbrowser gestartet wird, um beim Debuggen eine Verbindung mit der ausgeführten Webanwendung herzustellen, führt Live Share standardmäßig denselben Vorgang auf jedem Gastcomputer aus. Diese Vorgehensweise ist sicher, da die Remotewebanwendung in der Standardeinstellung nur während der Debugsitzung für Gäste verfügbar ist.

Unter [Freigeben eines Servers](#share-a-server) finden Sie Informationen dazu, wie Sie einen Server für andere Projekttypen und/oder für die Dauer der Sitzung freigeben.

> [!TIP]
> Wenn das Verhalten zur automatischen Freigabe nicht verwendet werden soll, können Sie die Einstellungen unter **Extras > Optionen > Live Share** ändern.

![Animation: gleichzeitiges Debuggen](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Anpassen des Visual Studio-Verhaltens für Beitritte zu Debugsitzungen

Als Gast werden Sie standardmäßig Debugsitzungen angefügt, wenn diese vom Gastgeber freigegeben werden. Dieses Verhalten kann in einigen Fällen störend wirken. Sie können es allerdings wie folgt ändern:

1. Wechseln Sie zu **Extras > Optionen > Live Share**.
2. Legen Sie für die Option **Join debug session** (Debugsitzung beitreten) einen der folgenden Werte fest:

| Option | Verhalten |
|--------|----------|
| Automatische | Der Standardwert. Als Gast treten Sie automatisch allen freigegebenen Debugsitzungen bei, die vom Gastgeber gestartet werden. |
| Prompted (Bei Aufforderung) | Als Gast werden Sie aufgefordert, einer freigegebenen Debugsitzung beizutreten, wenn diese vom Gastgeber gestartet wird. |
| Manuell | Als Gast müssen Sie Debugsitzungen manuell beitreten. Weitere Informationen finden Sie unter [Trennen und erneutes Anfügen](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Trennen und erneutes Anfügen

Als Gast können Sie das Debuggen vorübergehend anhalten. Klicken Sie in der Debugsymbolleiste auf das Stoppsymbol, um den Debugger zu trennen, ohne dabei den Gastgeber oder andere Gäste zu beeinflussen.

Wenn Sie die Einstellungen so angepasst haben, dass der Debugger nicht mehr automatisch angefügt wird, oder wenn Sie diesen später erneut anfügen möchten, können Sie aus der Dropdownliste „Startelement auswählen“ die ausgeführte Debugsitzung auswählen.

![Debugschaltfläche in Visual Studio](../media/vs-select-reattach.png)

Anschließend fügen Sie den ausgewählten Eintrag mit einem Klick an.

![Debugschaltfläche in Visual Studio](../media/vs-reattach.png)

## <a name="share-a-server"></a>Freigeben eines Servers

Als Zusammenarbeitssitzungs-Gastgeber müssen Sie in einigen Fällen zusätzliche lokale Server oder Dienste für Gäste freigeben. Diese reichen von RESTful-Endpunkten über Datenbanken bis hin zu anderen Servern. In Visual Studio Live Share können Sie eine lokale Portnummer angeben, sie optional benennen und anschließend für alle Gäste freigeben.

Der freigegebene Server ist dann auf demselben Port über die lokalen Computer der Gäste zugänglich. Wenn Sie beispielsweise einen Webserver freigegeben haben, **der auf Port 3000 ausgeführt wird**, können Gäste diesen auf ihrem **lokalen Computer** unter http://localhost:3000 erreichen. Dazu wird ein sicherer SSH- oder SSL-Tunnel zwischen dem Gastgeber und den Gästen erstellt und über den Dienst authentifiziert. So wird sichergestellt, dass nur Teilnehmer der Zusammenarbeitssitzung Zugriff haben.

> **Sicherheitstipp:** Als Gastgeber sollten Sie nur ganz bestimmte Ports für Gäste freigeben und Anwendungs- statt Systemports verwenden. Für Gäste verhalten sich freigegebene Ports so, als würde der Server oder Dienst auf dem lokalen Gastcomputer ausgeführt werden. Dies ist zwar sehr nützlich, kann aber auch riskant sein, wenn der falsche Port freigegeben wird.

Aus Sicherheitsgründen stehen nur Server, deren Ports Sie festlegen, für andere Gäste zur Verfügung. Als **Zusammenarbeitssitzungs-Gastgeber** können Sie einen Server ganz einfach hinzufügen. Gehen Sie dabei folgendermaßen vor:

1. Klicken Sie auf die Schaltfläche mit dem Sitzungszustand rechts oben und anschließend auf „Manage Shared Local Servers“ (Freigegebene lokale Server verwalten).

    ![Freigegebene lokale Server verwalten](../media/vs-share-local-servers.png)

2. Klicken Sie im angezeigten Dialogfeld auf „Add“ (Hinzufügen), und geben Sie die Nummer des Ports, auf dem der Server ausgeführt wird, und einen Namen ein. Drücken Sie anschließend die EINGABETASTE, und klicken Sie auf „OK“.

    ![Freigegebene lokale Server verwalten](../media/vs-manage-local-shared-servers.png)

Das ist alles! Der Server wird nun auf dem Gastcomputer dem Localhost auf dem gleichen Port zugeordnet, falls dieser Port noch nicht verwendet wird.

Wird er hingegen bereits verwendet, wird ein automatisch ein anderer ausgewählt. Wenn Sie als Gast auf die Schaltfläche mit dem Sitzungszustand oben rechts und anschließend auf „View Shared Local Servers“ (Freigegebene lokale Server anzeigen) klicken, wird eine Liste der aktuell freigegebenen Ports nach Namen (sofern festgelegt) angezeigt.

![Freigegebene lokale Server anzeigen](../media/vs-view-shared-servers.png)

Beachten Sie, dass *Gäste aus Sicherheitsgründen nicht festlegen können*, welche Ports auf dem Computer des Gastgebers freigegeben werden.

Wenn ein lokaler Server **nicht mehr freigegeben werden soll**, muss der Gastgeber auf die Schaltfläche mit dem Sitzungszustand oben rechts und anschließend auf „Manage Shared Local Servers“ (Freigegebene lokale Server verwalten) klicken, den entsprechenden Port auswählen und auf „Remove“ (Entfernen) klicken.

## <a name="share-a-terminal"></a>Freigeben eines Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Als Gastgeber können Sie in Live Share für Gäste bei Bedarf ein Terminal freigeben. Das freigegebene Terminal kann schreibgeschützt oder vollständig für die Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Sie können Gästen die Terminalausgabe oder das Terminal selbst zugänglich machen. Im zweiten Fall können Gäste Tests und Builds ausführen oder auch umgebungsspezifische Probleme selektieren, die nur auf Ihrem Computer auftreten.

Terminals werden jedoch standardmäßig **nicht** freigegeben, da Gäste in jedem Fall Leseberechtigungen für die Ausgabe der ausgeführten Befehle erhalten und darüber hinaus eventuell auch selbst Befehle ausführen können. Auf diese Weise können Sie in lokalen Terminals ohne Risiken Befehle ausführen und Terminals nur bei Bedarf freigeben. Des Weiteren haben nur Gastgeber die Möglichkeit, freigegebene Terminals zu starten. So werden Gäste daran gehindert, ein eigenes Terminal aufzurufen und unerwartete Befehle auszuführen, die Sie nicht überwachen können.

Sie können als Gastgeber ein Terminal freigeben, indem Sie auf die Schaltfläche mit dem Sitzungszustand oben rechts klicken und anschließend eines der „Terminal freigeben“-Menüelemente auswählen.

![Terminalmenü](../media/vs-terminal-menu.png)

Nun können Sie aus dem Menü ein Terminal mit Leseberechtigungen oder mit Lese-/Schreibberechtigungen auswählen. Im zweiten Fall kann jede Person einschließlich des Gastgebers Befehle im Terminal eingeben. Dadurch können unerwünschte Gastaktionen leicht unterbunden werden. **Die Lese- und Schreibberechtigungen sollten Sie aus Sicherheitsgründen ausschließlich Gästen bereitstellen, die darauf angewiesen sind**. Terminals mit Leseberechtigungen sollten Sie in Szenarios einsetzen, in denen Gäste nur die Ausgabe der von Ihnen ausgeführten Befehle sehen dürfen.

> [!NOTE]
> Wenn sich die Zusammenarbeitssitzung im schreibgeschützten Modus befindet, können nur Terminals, für die Leseberechtigungen vorliegen, vom Gastgeber freigegeben werden.

Nachdem Sie die Art des freigegebenes Terminals ausgewählt haben, das gestartet werden soll, wird ein neues freigegebenes Terminal für alle Teilnehmer mit den richtigen Berechtigungen angezeigt. Visual Studio Code unterstützt standardmäßig Terminals, Visual Studio hingegen nicht. Aus diesem Grund wird in der Standardeinstellung ein neues Fenster mit dem Terminal angezeigt. Wenn allerdings die [Whack Whack Terminal-Erweiterung](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal) installiert ist, wird von Live Share ein integriertes Terminal erstellt. In Visual Studio wird ein Installationslink angezeigt, wenn Sie ein freigegebenes Terminal zum ersten Mal starten oder diesem beitreten.

![Popupbenachrichtigung zur Terminalinstallation](../media/vs-terminal-install.png)

Geben Sie zum Beenden der Terminalsitzung „exit“ ein, oder schließen Sie das Terminalfenster. Dadurch werden alle Teilnehmerverbindungen getrennt.

## <a name="session-states"></a>Sitzungszustände

Nachdem Sie eine Zusammenarbeitssitzung gestartet haben oder dieser beigetreten sind und Zugriff auf freigegebene Inhalte haben, wird die Schaltfläche „Live Share“ mit dem Zustand der aktiven Sitzung aktualisiert.

Folgende Zustände sind möglich:

| Zustand | Schaltfläche | BESCHREIBUNG |
|-------|--------|-------------|
| Inaktiv | ![Zustand „Inaktiv“ in Visual Studio](../media/vs-status-share.png) | Es ist keine aktive Zusammenarbeitssitzung vorhanden, und keine Inhalte werden freigegeben. |
| Gastgeber: Wird freigegeben... | ![Zustand „Wird freigegeben...“ in Visual Studio](../media/vs-status-sharing.png) | Eine Zusammenarbeitssitzung wird gestartet, und Inhalte werden in Kürze freigegeben. |
| Gastgeber: Freigabe | ![Zustand „Freigabe aktiv“ in Visual Studio ](../media/vs-status-active.png) | Eine aktive Zusammenarbeitssitzung ist vorhanden, und Inhalte werden freigegeben. |
| Gastgeber: Schreibgeschützt freigeben | ![Zustand „Schreibgeschützt freigeben“ in Visual Studio](../media/vs-status-sharing-read-only.png)| Eine schreibgeschützte Zusammenarbeitssitzung wird freigegeben. |
| Gast: Beitritt zur Sitzung | ![Zustand „Beitritt zur Sitzung“ in Visual Studio Code](../media/vs-status-joining.png) | Ein Teilnehmer tritt einer vorhandenen Zusammenarbeitssitzung bei. |
| Gast: Beigetreten | ![Zustand „Beigetreten“ in Visual Studio](../media/vs-status-joined.png) | Ein Teilnehmer ist einer aktiven Zusammenarbeitssitzung beigetreten und empfängt freigegebene Inhalte. |
| Gast: Schreibgeschützt beigetreten | ![Zustand „Schreibgeschützt beigetreten“ in Visual Studio](../media/vs-status-joined-read-only.png) | Ein Teilnehmer ist einer aktiven schreibgeschützten Zusammenarbeitssitzung beigetreten. |

## <a name="guest-limitations"></a>Einschränkungen für Gäste

Aktuell treten bei Verwendung der Gastfeatures einige Probleme auf. Zusammenarbeitssitzungs-Gastgeber können allerdings weiterhin alle Funktionen ihres bevorzugten Tools verwenden. Über die folgenden Links erhalten Sie weitere Informationen:

- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie weitere Informationen benötigen, sehen Sie sich diese zusätzlichen Artikel an.

- [Schnellstart: Freigeben Ihres ersten Projekts](../quickstart/share.md)
- [Schnellstart: Beitreten zu Ihrer ersten Sitzung](../quickstart/join.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](vscode.md)
- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

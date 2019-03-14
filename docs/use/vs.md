---
title: Zusammenarbeiten mithilfe von Visual Studio – Visual Studio Live Share | Microsoft-Dokumentation
description: Ein Satz von Zusammenarbeit Vorgehensweisen für Visual Studio und Live Share.
ms.custom: ''
ms.date: 04/25/2018
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
ms.openlocfilehash: 995c9e16d24328bb2680deb99cd7e7d421af945c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256130"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Gewusst wie: Zusammenarbeiten mithilfe von Visual Studio

Möchten Sie mit Live Share in Visual Studio Zusammenarbeit erhalten? Wenn dies der Fall ist, können Sie in die richtige Stelle. In diesem Artikel werden Sie einige der spezifischen Features in Visual Studio Live Share-Erweiterung für Visual Studio zu verwenden wie erläutert.

Beachten Sie, die alle Aktivitäten in der Zusammenarbeit im hier beschriebenen umfassen ein einzelnes **Zusammenarbeit Sitzungshost** und einem oder mehreren **Gäste**. Der Gastgeber ist die Person, die die Zusammenarbeitssitzung gestartet hat, und jede Person, die ihr beitritt, ist ein Gast.

*Suchen Sie eine Zusammenfassung der gekürzte? Sehen Sie sich die [freigeben](../quickstart/share.md) oder [Join](../quickstart/join.md) Schnellstarts stattdessen.*

> [!TIP]
> Wussten Sie schon, dass Sie *Ihrer eigenen Zusammenarbeitssitzung beitreten* können? Auf diese Weise können Sie Live Share selber ausprobieren oder aber eine Instanz von Visual Studio oder VS Code starten und eine Remoteverbindung damit herstellen! Sie können sogar dieselbe Identität für beide Instanzen verwenden. Probieren Sie es aus!

## <a name="installation"></a>Installation

Bevor Sie beginnen, müssen Sie installieren **Visual Studio 2017 15.6 oder höher** auf Windows 7, 8.1 oder 10. *Visual Studio 15.7 und höher wird jedoch empfohlen, diese lokalen Rückgängig/Wiederholen-Unterstützung ermöglicht.*

Es ist einfach, ersten Schritten:

1. Installieren Sie die eine beliebige Edition von [Visual Studio 2017](https://visualstudio.microsoft.com/vs/) 15.6 und höher.
2. Installieren einer [Workload unterstützt](../reference/platform-support.md). (z.B. ASP.NET, .NET Core, C++ und/oder Node.js)
3. [Herunterladen](https://aka.ms/vsls-dl/vs) und Installieren der Visual Studio Live Share-Erweiterung über den Marketplace.

Durch das Herunterladen und die Nutzung von Visual Studio Live Share stimmen Sie den [Lizenzbedingungen](https://aka.ms/vsls-license) und den [Datenschutzbestimmungen](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx) zu. Wenn Probleme auftreten, lesen Sie [Troubleshooting](../troubleshooting.md).

[![Herunterladen](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Anmelden

Um zusammenarbeiten können, benötigen Sie SSO in Visual Studio Live Share damit jeder weiß, wer Sie sind. Dies ist nur eine Sicherheitsmaßnahme und **nicht** vorschaubuilds, dass Sie alle Marketing oder andere Research-Aktivitäten. Sie können mit einem persönlichen Microsoft-Konto anmelden (z. B. @outlook.com), Microsoft gestützte Geschäfts- oder schulkonto (AAD) oder ein GitHub-Konto. Anmeldung ist einfach.

Standardmäßig verwendet Visual Studio die Ihrer [personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) , wenn Sie bereits in Visual Studio angemeldet sind, Sie können also diesen Schritt überspringen können. Andernfalls melden Sie sich wie gewohnt.

![Schaltfläche zur Anmeldung im Vergleich](../media/vs-sign-in-button.png)

Wenn Sie eine andere Anmeldung als Ihrer Visual Studio verwenden möchten [personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), wechseln Sie zu **Tools &gt; Optionen &gt; Live Share &gt; Benutzerkonto** wechseln Anmeldeinformationen.

![Visual Studio-Tools-Optionen-Livefreigabe](../media/vs-tools-options.png)

Auswählen von **externes Konto** ermöglicht Ihnen die Auswahl ein Kontos, das von Visual Studio-Personalisierungsfunktion wie GitHub nicht unterstützt. Ein Browser wird automatisch beim ersten angezeigt, Sie eine Live Share-Funktion verwenden, sodass die Anmeldung durchgeführt werden kann.

Wenn Probleme auftreten, sehen Sie sich [Problembehandlung](../troubleshooting.md#sign-in) Weitere Tipps.

## <a name="share-a-project"></a>Projekt freigeben

Nach dem Herunterladen und Installieren von Visual Studio Live Share, befolgen Sie diese Schritte zum Starten einer zusammenarbeitssitzung und einladen von Kollegen mit Ihnen zusammenarbeiten.

1. **Anmelden**

    Nach der Installation der Erweiterungs Live Share sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Standardmäßig verwendet Visual Studio Ihrem personalisierungskonto, damit Sie diesen Schritt überspringen, vollständig möglicherweise.

    Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Öffnen Sie eine Lösung, Projekt oder Ordner**

    Verwenden Sie Ihren normalen Workflow um zu öffnen, einen Ordner, Projekt oder Projektmappe, die Sie für die Gäste freigeben möchten.

3. **[Optional] Ausgeblendete oder ausgeschlossene Dateien aktualisieren**

    Standardmäßig werden Live Share **blendet** Dateien/Ordner, die in der gitignore-Dateien in Ihrem Projekt daran, Gäste. **Ausblenden von** eine Datei verhindert, dass sie angezeigt werden, in der Dateistruktur beim **ausschließen** sie übertragen werden, selbst während der Vorgänge wie das Debuggen beendet. Wenn Sie möchten die ausblenden/verschiedene Dateien ausschließen einer **. vsls.json** Datei kann dem Projekt mit diesen Einstellungen hinzugefügt werden. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

4. **Starten Sie eine zusammenarbeitssitzung**

    Klicken Sie nun einfach auf die Schaltfläche "Freigeben" in der oberen rechten Ecke.

    ![Visual Studio-Schaltfläche "freigeben"](../media/vs-share-button.png)

    > [!NOTE]
    > Möglicherweise von Ihrem desktop-Firewall-Software werden Sie aufgefordert, ob der Live-Freigabe-Agent einen Port erstmalig öffnen, die Sie freigeben. Ist völlig optional, jedoch ermöglicht eine sichere "direct-Modus" akzeptieren diese zur Verbesserung der Leistung, wenn die Person, die mit dem Sie arbeiten im selben Netzwerk befindet, wie Sie sind. Finden Sie unter [ändern den Verbindungsmodus](../reference/connectivity.md#changing-the-connection-mode) Details.

    Ein Link zur freigabeeinladung werden automatisch in die Zwischenablage kopiert werden. Wenn in einem Browser geöffnet wird, können in diesen Link, andere Benutzer, eine neue zusammenarbeitssitzung beizutreten, die Inhalte dieser Ordner für sie freigegeben hat.

    Sie sehen auch den Übergang des "Share"-Schaltfläche "Sitzungszustand" übermitteln. Finden Sie unter [Sitzungszustand](#session-states) unten angegebenen Informationen zu, wie dies aussieht.

    Beachten Sie, dass wenn Sie den Link zur freigabeeinladung erneut abrufen, nachdem Sie begonnen haben, freigeben möchten, Sie darauf zugreifen können, durch Klicken auf die Freigabe /-Sitzungszustand Schaltfläche, und wählen "Link kopieren".

5. **[Optional] Nur-Lese Modus aktivieren**

    Sobald Sie Ihre zusammenarbeitssitzung starten, können Sie die Sitzung, um zu verhindern, dass Gäste Bearbeitungen an den freigegebenen Code schreibgeschützt sein festlegen.

    Nach der Freigabe erhalten Sie eine Benachrichtigung, dass der Link zur freigabeeinladung in die Zwischenablage kopiert wurde. Sie können dann die Option aus, um die Sitzung schreibgeschützt machen auswählen.

    ![VS-nur-Lese-Modus](../media/vs-read-only-notification.png)

6. **Senden Sie an andere Benutzer den link**

    Senden den Link per E-mail, Slack, Skype usw., die Sie einladen möchten. Beachten Sie, das mit der Ebene der Live-Freigabe zugreifen können Sitzungen für Gäste, bieten **sollten nur Freigabe für Personen, die Sie als vertrauenswürdig einstufen** und stellen Sie sich über die folgen, was Sie freigegeben haben.

    > **Security Tip:** Möchten Sie die Auswirkungen auf die Sicherheit einiger Live Share-Funktionen zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

    Wenn der Gast, Sie eingeladen Fragen haben, wurde die "[Schnellstart: Verknüpfen Sie Ihre erste Sitzung](../quickstart/join.md)"Artikel enthält einige weitere Informationen zu einrichten und als Gast ausgeführt wird.

7. **[Optional] Den Gast genehmigen**

    Standardmäßig Gäste werden automatisch Ihre zusammenarbeitssitzung verknüpfen, und Sie werden benachrichtigt, sobald sie bereit, mit Ihnen zusammenarbeiten haben. Während dieser Benachrichtigung Sie sie aus der Sitzung entfernen kann, können Sie auch entscheiden, dass stattdessen eine explizite "Genehmigung" für alle Benutzer verknüpfen müssen.

    Ändern Sie einfach **Tools > Optionen > Live Share > Gast Genehmigung** auf "true", um das Feature aktivieren. Nachdem Sie diese Einstellung aktiviert haben, fordert eine Benachrichtigung Sie auf den Gast zu genehmigen, bevor sie hinzugefügt werden können.

    ![Visual Studio-Join-genehmigungsanforderung](../media/vs-join-approval.png)

    Finden Sie unter [Einladungen und Join-Zugriff](../reference/security.md#invitations-and-join-access) Weitere Informationen zu Überlegungen zur Sicherheit der Einladung.

Das wars!!

### <a name="ending-the-collaboration-session"></a>Beenden der zusammenarbeitssitzung

Als Host, können Sie vollständig Freigabe beenden und der zusammenarbeitssitzung zu beenden, indem Sie auf die Freigabe /-Sitzungszustand Schaltfläche (in der oberen rechten Ecke) und wählen "End Zusammenarbeitssitzung".

![Freigabe beenden](../media/vs-stop-sharing.png)

Alle Gäste werden benachrichtigt, dass die Sitzung beendet wurde. Sobald die Sitzung beendet wurde, Gäste werden nicht mehr auf die Inhalte zugreifen, und alle temporären Dateien werden automatisch bereinigt.

Probleme mit dem Freigeben? Sehen Sie sich [Problembehandlung](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Beitreten Sie zu einer zusammenarbeitssitzung

Nach dem Herunterladen und Installieren von Visual Studio Live Share, müssen Gäste nur ein paar Schritte ausführen, um eine gehostete zusammenarbeitssitzung zu verknüpfen. Es gibt zwei Möglichkeiten, um zu verknüpfen: [über den Browser](#join-via-the-browser) und [manuell](#join-manually).

> **Security Tip:** Als Gast beitreten zu einer zusammenarbeitssitzung ist es wichtig zu verstehen, dass die Hosts den Zugriff auf bestimmte Dateien oder Funktionen beschränkt werden können. Möchten Sie die Auswirkungen auf die Sicherheit einiger Features und Einstellungen Live Share zu verstehen? Sehen Sie sich die [Sicherheit](../reference/security.md) Artikel.

### <a name="join-via-the-browser"></a>Verknüpfen Sie über den browser

Die einfachste Möglichkeit zum Verknüpfen einer zusammenarbeitssitzung ist auf den Link zur freigabeeinladung einfach in einem Webbrowser zu öffnen. Hier ist, was Sie erwarten können, wenn Sie diesen Flow ausführen.

1. **Anmelden**

    Nach der Installation der Erweiterungs Live Share sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Standardmäßig verwendet Visual Studio Ihrem personalisierungskonto, damit Sie diesen Schritt überspringen, vollständig möglicherweise.

    Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Klicken Sie auf den Link zur freigabeeinladung / die INVITE-Nachricht in Ihrem Browser geöffnet.**

    Der Link zur freigabeeinladung in einem Browser, öffnen Sie einfach (oder erneut zu öffnen Sie).

    > **Hinweis:** Wenn Sie die Live Share-Erweiterung noch nicht installiert haben, wird mit Links zu den Extension Marketplace angezeigt. Installieren Sie die Erweiterung, und starten Sie das Tool, und wiederholen Sie.

    Sie sollten eine Benachrichtigung über möchte, dass der Browser eine aktivierte Freigabe für die Live-Tool zu starten. Wenn Sie es in das ausgewählte Tool starten können, müssen Sie mit der zusammenarbeitssitzung Start verbunden sein.

    ![Verknüpfen Sie die Seite](../media/join-page.png)

    Wenn der Host offline ist, werden Sie an diesem Punkt stattdessen benachrichtigt werden. Sie können dann wenden Sie sich an den Host und bitten Sie ihn erneut freigeben.

    > [!NOTE]
    > Immer noch Probleme? Finden Sie unter [Manuelles Verknüpfen von](#join-manually).

3. **Zusammenarbeit**

    Das wars!! Nach wenigen Augenblicken es wird eine Verbindung, und Sie können beginnen, zusammenarbeiten.

    Sie sehen, dass der Übergang "Share" Schaltfläche "Sitzungszustand" übermitteln. Finden Sie unter [Sitzungszustand](#session-states) Informationen weiter unten aus, wie dies aussieht.

    Sie werden dann automatisch in die Datei weitergeleitet, die der Host derzeit bearbeitet wird, sobald die Verknüpfung abgeschlossen ist.

### <a name="join-manually"></a>Manuelles Verknüpfen von

Sie können auch manuell verknüpfen, ohne einen Webbrowser, der in Situationen nützlich sein kann, in dem das Tool, das Sie verwenden möchten wird bereits ausgeführt, Sie ein anderes Tool verwenden, als Sie in der Regel nicht, oder wenn Sie Probleme haben sollten einladen Probleme bei der Links aus irgendeinem Grund arbeiten möchten. Der Prozess ist einfach:

1. **Anmelden**

    Nach der Installation der Erweiterungs Live Share sollten Sie für die Anmeldung können Sie weitere Mitwirkende wissen, wer Sie sind. Standardmäßig verwendet Visual Studio Ihrem personalisierungskonto, damit Sie diesen Schritt überspringen, vollständig möglicherweise.

    Finden Sie unter [Anmeldung](#sign-in) Weitere Details.

2. **Verwenden Sie den joinbefehl**

    Wechseln Sie einfach zu **Datei > Zusammenarbeitssitzung verknüpfen**

    ![Visual Studio-Menü "Join"](../media/vs-join.png)

3. **Fügen Sie den Link für die INVITE-Nachricht**

    Fügen Sie die einladungs-URL, die Sie gesendet wurden, und bestätigen.

4. **Arbeiten Sie zusammen!**

    Das ist alles! Sie sollten mit der zusammenarbeitssitzung vorübergehend verbunden werden.

    Sie sehen, dass der Übergang "Share" Schaltfläche "Sitzungszustand" übermitteln. Finden Sie unter [Sitzungszustand](#session-states) Informationen weiter unten aus, wie dies aussieht.

    Sie werden dann automatisch weitergeleitet an, in dem der Host derzeit bearbeitet wird, nach Abschluss die Verknüpfung.

### <a name="leave-the-collaboration-session"></a>Lassen Sie die zusammenarbeitssitzung

Sie können der zusammenarbeitssitzung als Gast lassen, ohne für andere Benutzer zu beenden, indem Sie einfach schließen das Tool oder durch Klicken auf die Freigabe /-Sitzungszustand Schaltfläche, und wählen "Zusammenarbeitssitzung verlassen".

![Visual Studio-Menü "Join"](../media/vs-leave-session.png)

Alle temporären Dateien werden automatisch bereinigt, sodass keine weitere Aktion erforderlich ist.

Probleme mit dem Verknüpfen? Sehen Sie sich [Problembehandlung](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Gemeinsame Bearbeitung

Nach der Gast eine zusammenarbeitssitzung verknüpft ist, werden alle Mitarbeiter sofort anderer Änderungen und die Auswahl in Echtzeit angezeigt werden. Alles, was Sie tun müssen ist, wählen Sie eine Datei im Datei-Explorer, und mit der Bearbeitung beginnen. Sowohl Hosts und -Gäste sehen die Änderungen machen und sich somit leicht durchlaufen, und um die nach-unten-Lösungen schnell fixieren beitragen können.

> [!NOTE]
> Beitreten zu einer zusammenarbeitssitzung nur-Lese werden Gäste daran gehindert, werden Änderungen an Dateien vornehmen können. Ein Host kann [nur-Lese Modus zu aktivieren, bei der Freigabe](#share-a-project). Als Gast, können Sie feststellen, ob Sie eine nur-Lese Sitzung beigetreten sind, anhand Ihrer [Sitzungszustand](#session-states).

![Screenshot mit gemeinsam bearbeiten](../media/vs-coedit.png)

> [!NOTE]
> Gleichzeitig bearbeiten, gelten einige Einschränkungen für bestimmte Sprachen. Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Features je nach Sprache zu informieren.

Cursor und Änderungen werden die ausgewählten Optionen, die Sie vornehmen, auch an alle Teilnehmer in der gleichen Datei angezeigt. Dies erleichtert das hervorheben, in dem Probleme vorhanden sind oder Ideen vermitteln können.

![Screenshot mit Hervorhebung](../media/vs-highlight.png)

Besser noch, können Sie und andere Teilnehmer für jede Datei im freigegebenen Projekt navigieren. Sie können entweder bearbeiten, unabhängig voneinander oder zusammen, was bedeutet, dass Sie nahtlos zwischen Untersuchung durchführen kleine Anpassungen und vollständige gemeinsamen Bearbeitens wechseln können.

> [!NOTE]
> Standardmäßig geöffnet Live Share Freigaben Dateien außerhalb der freigegebenen Projektmappe auch. Wenn Sie diese Funktion deaktivieren möchten, aktualisieren Sie die externen Freigeben von Dateien in Tools &gt; Optionen &gt; Live Share auf "false".

Die daraus resultierenden Bearbeitungen werden auf dem Computer des Hosts auf beibehalten, speichern Sie es ist nicht erforderlich, synchronisieren, mithilfe von Push übertragen oder Dateien zu senden, sobald Sie fertig sind bearbeiten. Die Änderungen treten "nur."

> **Security Tip:** Bei allen Teilnehmern können unabhängig voneinander navigieren und Bearbeiten von Dateien, als Host, sollten Sie einschränken, welche Dateien in Ihrem Projekt über Zugriff auf Gäste sind eine. vsls.json-Datei. Als Gast ist es auch wichtig zu wissen, dass Sie bestimmte Dateien durch diese Einstellungen nicht sehen können. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

### <a name="changing-participant-flag-behaviors"></a>Ändern die Teilnehmer Flag-Verhalten

In der Standardeinstellung zeigt Visual Studio Live Share automatisch ein "Flag" neben den Teilnehmer-Cursor, wenn darauf gezeigt wird, oder wenn sie bearbeiten möchten, markieren Sie oder bewegen Sie ihren Cursor. In einigen Fällen empfiehlt es sich, dieses Verhalten ändern. Gehen Sie hierzu wie folgt vor:

1. Wechseln Sie zu **Tools > Optionen > Live Share**
2. Ändern der **Flag Sichtbarkeit** Option aus, um einen der folgenden:

| Option | Verhalten |
|--------|----------|
| OnHoverOnly | Das Flag wird nur angezeigt, wenn Sie über den Cursor bewegen. |
| OnHoverOrActivity | Dies ist die Standardeinstellung. Das Flag wird angezeigt, wenn darauf gezeigt wird oder wenn der Teilnehmer bearbeitet, hebt hervor, oder verschiebt den Cursor. |
| Always | Das Flag ist immer sichtbar.

## <a name="following"></a>Folgende

Wenn Sie eine zusammenarbeitssitzung nutzen, Sie werden sehen, dass jeder Teilnehmer der Initialen in der oberen rechten Ecke des Editors neben der Schaltfläche zur Anmeldung. Mit dem Mauszeiger auf die Initialen erfahren Sie vollständige Informationen des Teilnehmers.

![Screenshot mit Benutzer](../media/vs-person.png)

Manchmal müssen Sie möglicherweise zur Erläuterung eines Problems oder bei Entwurf, die mehrere Dateien oder stellen im Code umfasst. In diesen Fällen kann es sinnvoll sein, ein Kollege vorübergehend zu befolgen, wie er im gesamten Projekt verschieben. Aus diesem Grund werden als Gast, wenn Sie eine zusammenarbeitssitzung verknüpfen Sie automatisch "des Hosts folgen". Wenn einen Teilnehmer zu befolgen, bleibt Ihrem Editor abgestimmt werden, die derzeit geöffnete Datei, Cursor und Bildlaufposition.

> [!NOTE]
> Standardmäßig geöffnet Live Share Freigaben Dateien außerhalb der freigegebenen Projektmappe auch. Wenn Sie diese Funktion deaktivieren möchten, aktualisieren Sie die externen Freigeben von Dateien in Tools &gt; Optionen &gt; Live Share auf "false".

Um erleichtern Ihnen die Out-of "führen Sie im Modus" wechseln, und starten die Bearbeitung auf Ihren eigenen, müssen Sie beenden, folgenden, wenn Folgendes geschieht:

1. Sie bearbeiten, bewegen Sie den Cursor oder eine Auswahl treffen
2. Wählen Sie eine andere Datei

Sie können auch jederzeit durch Klicken auf die Initialen der Person ein, die Sie in der oberen rechten Ecke Folgen nach Beenden. Initialen der des Teilnehmers auf der Kreis, der angibt, dass Sie diese folgen wird dann wieder ausgeblendet.

![Visual Studio-Teilnehmer gefolgt wird.](../media/vs-pinned.png) ![Visual Studio-Teilnehmer nicht eingehalten werden](../media/vs-pin-hover.png)

Sie können auf alle Ihre Initialen am gleichen Ort auf jedem Host zu folgen oder vom Gast in der zusammenarbeitssitzung klicken. Beachten Sie, wenn Sie nur ein Standort statt, springen möchten einfach ihre Initialen auf das Doppelklicken.

## <a name="focusing"></a>Konzentrieren

Gelegentlich sollten Sie alle Benutzer in einer zusammenarbeitssitzung und sehen Sie sich etwas, das Sie ausführen. Live Share können Sie Fragen sich, dass jeder "ihre Aufmerksamkeit auf Sie eine Benachrichtigung, die Sie Sie wieder folgen erleichtert konzentrieren".

Nur klicken Sie auf der Sitzungszustand / -Schaltfläche in der oberen rechten Ecke und wählen Sie "Den Fokus Teilnehmer".

![Fokus-Menüoption](../media/vs-focus.png)

Alle Benutzer in der zusammenarbeitssitzung klicken Sie dann erhalten eine Benachrichtigung, dass Sie ihre Aufmerksamkeit angefordert wurden

![Fokus Toast-Benachrichtigung](../media/vs-focus-toast.png)

Sie können nur "Folgen" direkt über die Benachrichtigung klicken, wenn sie den Fokus auf die Sie speichern möchten.

## <a name="co-debugging"></a>Gemeinsames Debuggen

Visual Studio Live Share Zusammenarbeit debugging-Funktion ist eine leistungsstarke und eindeutige Möglichkeit, ein Problem debuggen können. Nach der Aktivierung einer Oberfläche zur Zusammenarbeit, um Probleme zu beheben, können es auch Sie und anderen Teilnehmern in der Sitzung, die die Möglichkeit, untersuchen Sie Probleme bei bestimmten Umgebung sein durch Bereitstellen einer gemeinsam genutzten debugging-Sitzungs auf dem Computer des Hosts.

> **Security Tip:** Bei allen Teilnehmern können unabhängig voneinander navigieren und Bearbeiten von Dateien, als Host, sollten Sie einschränken, welche Dateien in Ihrem Projekt über Zugriff auf Gäste sind eine. vsls.json-Datei. Sie sollten außerdem beachten, dass der Konsole/REPL-Zugriff bedeutet, dass die Teilnehmer Befehle auf Ihrem Computer ausführen können, sodass Sie nur mit diesen gemeinsam beheben sollten, denen, die Sie vertrauen. Als Gast ist es auch wichtig zu wissen, dass Sie möglicherweise nicht den Debugger zu folgen, wie sie bestimmte beschränkte Dateien-Dateien durch diese Einstellungen schrittweise. Finden Sie unter [steuern den Zugriff auf Dateien und Sichtbarkeit](../reference/security.md#controlling-file-access-and-visibility) Details.

Verwenden es einfach aus. Die Zusammenarbeit Sitzungshost muss lediglich zum Starten des Debuggings in Visual Studio die übliche Weise.

![Schaltfläche "VS-Debuggen"](../media/vs-debug-button.png)

Sobald aufseiten des Hosts der Debugger angefügt wurde, werden alle Gäste automatisch auch angefügt. Obwohl eine Debuggen "Sitzung", die auf dem Computer des Hosts ausgeführt wird, werden alle Teilnehmer verbunden sind und verfügen über eigene Ansicht.

> [!TIP]
> Wenn Sie ändern, wann und wie erfolgt gleichzeitig debuggen möchten, können Sie ändern, dass die Standardverhalten, über die Einstellungen in **Tools > Optionen > Live Share**.

![Visual Studio-Debugger angefügt](../media/vs-debugger.png)

Alle Benutzer kann des Debugprozesses schrittweise dadurch nahtlosen Wechsel zwischen Mitarbeitern, ohne zum Aushandeln der Kontrolle.

> [!NOTE]
> Lesen Sie [Plattformunterstützung](../reference/platform-support.md), um sich über den Status von Debuggingfeatures je nach Sprache oder Plattform zu informieren.

Jede Projektmitarbeiter kann verschiedene Variablen zu untersuchen, fahren Sie mit anderen Dateien in der Aufrufliste, untersuchen Sie Variablen, und auch hinzufügen oder entfernen Haltepunkte. Co-Bearbeitungsfeatures können dann jeder Teilnehmer Redner zu verfolgen, wo sich die anderen die einzigartige Möglichkeit, problemlos Wechseln zwischen gleichzeitig untersuchen verschiedene Aspekte des Problems und Debuggen gemeinsam zu befinden.

> [!NOTE]
> In einer zusammenarbeitssitzung nur-Lese werden Gast nicht des Debugprozesses schrittweise können. Sie können jedoch immer noch hinzufügen oder entfernen Haltepunkte, und untersuchen Sie Variablen.

> [!TIP]
> Sie können auch in Visual Studio Code Debugsitzungen in Visual Studio und umgekehrt teilnehmen! Sehen Sie sich die [Visual Studio-Anweisungen](vscode.md#co-debugging) gemeinsam Debugging für Weitere Informationen.

### <a name="automatic-web-app-sharing"></a>Automatische Web app-Freigabe

Noch besser ist, für ASP.NET Web-App-Projekte standardmäßig Wenn Host Projekt konfiguriert ist, für den automatischen start von einem Webbrowser für die Verbindung der ausgeführten Webanwendung beim Debuggen Live Share wird automatisch auf jedem Gast Computer gilt! Dies erfolgt auf sichere Weise aus, und die remote-Web-Anwendung ist während der Debugsitzung wird standardmäßig nur für Gäste verfügbar.

Finden Sie unter [freigeben ein Servers](#share-a-server) Informationen zum Freigeben von Server-Zugriff für andere Projekttypen und/oder für die Dauer der Sitzung.

> [!TIP]
> Wenn Sie nicht wie automatisierte Freigabeverhalten Browser, und es ändern möchten, können Sie Einstellungen aktualisieren **Tools > Optionen > Live Share**.

![Animation der gleichzeitigen Debuggen](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Ändern Sie bei Visual Studio-Joins Debugsitzungen

Standardmäßig werden als Gast Sie automatisch angefügt werden, Debugsitzungen erhalten, wenn sie von dem Host gemeinsam verwendet werden. Allerdings können in einigen Fällen Sie dieses Verhalten störend finden. Glücklicherweise können Sie sie wie folgt ändern:

1. Wechseln Sie zu **Tools > Optionen > Live Share**
2. Ändern der **Join-Debug-Sitzungsoption** auf einen der folgenden:

| Option | Verhalten |
|--------|----------|
| Automatisch | Der Standardwert. Als Gast werden Sie automatisch alle freigegebenen Debugsitzung verknüpfen, wenn der Host gestartet wird. |
| Aufgefordert | Als Gast werden Sie aufgefordert, eine freigegebene Debugsitzung zu verknüpfen, wenn sie vom Host gestartet wird, werden sollen. |
| Manuell | Als Gast müssen Sie manuell alle Debugsitzungen zu verknüpfen. Finden Sie unter [trennen und erneutes Anfügen](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Trennen und erneutes Anfügen

Als Gast möchten Sie möglicherweise Beenden des Debuggens vorübergehend. Glücklicherweise können Sie einfach das Symbol "Beenden", in der Debug-Symbolleiste, um den Debugger zu trennen, ohne Auswirkungen auf den Host oder andere Gäste klicken.

Wenn Sie Einstellungen aktualisiert haben, damit Sie nicht mehr das automatische Anhängen oder einfach später erneut anfügen möchten, können Sie einfach die gewünschten ausgeführt wird, die Debugsitzung für die "Wählen Sie beim Start Element..." auswählen Öffnen Sie die Dropdownliste...

![Schaltfläche "VS-Debuggen"](../media/vs-select-reattach.png)

... ein, und klicken Sie dann auf die sie anfügen.

![Schaltfläche "VS-Debuggen"](../media/vs-reattach.png)

## <a name="share-a-server"></a>Freigeben eines Servers

Von Zeit zu Zeit als Host für Zusammenarbeit Sitzung möglicherweise, dass Sie zusätzlichen lokalen Server oder Dienste für Gäste freigeben möchten. Diese reichen von anderen RESTful-Endpunkte in Datenbanken oder anderen Servern. Visual Studio Live gemeinsam nutzen, können Sie eine lokale Portnummer angeben, geben sie optional einen Namen und dann für alle Gäste freigeben.

Gäste werden auf den Server zugreifen, die, den Sie an diesem Port auf ihren eigenen lokalen Computer auf dem genau gleichen Port freigegeben. Z. B., wenn Sie einen Webserver freigegeben **an Port 3000**, der Gast kann auf dem gleichen ausgeführten Webserver zugreifen, auf deren **eigenen Computer** am http://localhost:3000! Dies ist über einen sicheren SSH oder SSL-Tunnel zwischen den Hosts und Gästen umgesetzt und über den Dienst authentifiziert werden, damit Sie sicher sein können, dass nur die in der zusammenarbeitssitzung zugreifen können.

> **Security Tip:** Als Host sollten Sie sehr selektiv an die Ports können, die Sie für Gäste freigeben, und bleiben Sie auf die Anwendung Ports (anstatt eines System-Ports). Für Gäste freigegebener Anschlüsse verhält sich genau so, wie sie würden, wenn der Server-Dienst auf ihrem eigenen Computer ausgeführt wurde. Dies ist sehr nützlich, aber wenn, dass Sie der falsche Port freigegeben ist kann auch riskant sein.

Aus Gründen der Sicherheit stehen nur Server, die Ports, die Sie angeben, unter anderer Gäste berücksichtigt. Glücklicherweise es einfach, als der zusammenarbeitssitzung hinzufügen **Host**. Gehen Sie dabei folgendermaßen vor:

1. Klicken Sie auf die Freigabe / Sitzungsstatus Schaltfläche in der oberen rechten Ecke, und wählen Sie "Freigegebene lokale Server verwalten"

    ![Verwalten Sie freigegebene lokale Server](../media/vs-share-local-servers.png)

2. Klicken Sie im Dialogfeld, das angezeigt wird, klicken Sie auf "Hinzufügen", und geben Sie die Portnummer, die der Server wird ausgeführt auf lokal, geben Sie einen Namen, die EINGABETASTE drücken, klicken Sie dann OK.

    ![Verwalten Sie freigegebene lokale Server](../media/vs-manage-local-shared-servers.png)

Das ist alles! Der Server, auf dem Port, den Sie angegeben haben wird nun des Gasts "localhost" auf dem gleichen Port zugeordnet werden (es sei denn, die diesen Port bereits belegt wurde).

Wenn der Port bereits auf der Gast-Computer verwendet wird, wird eine andere automatisch ausgewählt. Zum Glück als Gast Sie eine Liste der derzeit sehen Ports (nach Namen, falls angegeben) freigegebenen, durch Klicken auf die Freigabe / Sitzungsstatus-Schaltfläche in der oberen rechten Ecke und auswählen "anzeigen freigegebene lokale Server".

![Viw freigegebene lokale Server](../media/vs-view-shared-servers.png)

Beachten Sie, dass *Gäste können nicht* steuern, welche Ports auf dem Computer des Hosts aus Sicherheitsgründen gemeinsam genutzt werden.

Um **beenden** Freigeben von einem lokalen Server, muss der Host lediglich auf die Freigabe / Sitzungsstatus Schaltfläche oben rechts wie oben, wählen "freigegebene lokale Server verwalten", und wählen Sie den entsprechenden Port, und klicken Sie auf "Entfernen".

## <a name="share-a-terminal"></a>Teilen Sie einen terminal

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise können Live-Freigabe, die Sie als ein Host, um optional "einen Terminal für Gäste freigeben". Freigegebene Terminal kann nur-Lese oder vollständig Zusammenarbeit sein, damit sowohl Sie als auch die Gäste können, führen Sie Befehle aus, und die Ergebnisse anzuzeigen. Sie können terminalausgabe Gäste Sichtbarkeit gewähren, oder holen sich auf, und führen Sie Tests, Builds oder sogar "Selektierung" Umgebung spezifische Probleme, die nur auf Ihrem Computer auftreten können.

Terminale sind jedoch **nicht** standardmäßig freigegeben werden, da die Gäste bieten mindestens über Lesezugriff auf die Ausgabe der Befehle, die Sie ausführen (sofern nicht die Möglichkeit zum Ausführen von Befehlen selbst). Auf diese Weise können Sie kostenlos Befehle ausführen, lokalen stellte Terminals bereit, ohne das Risiko und nur dann freigeben, wenn tatsächlich müssen dies tun. Darüber hinaus können nur Hosts starten, freigegebener Terminals, um zu verhindern, dass Gäste aus einen Startvorgang und Aktionen, die Sie nicht erwartet oder überwacht werden.

Sie können als Host einen Terminal durch Klicken auf den Sitzungsstatus freigeben / Schaltfläche in der oberen rechten Ecke, und wählen eines der Elemente im Menü "Terminal freigeben" freigeben.

![Menü "Terminalserver"](../media/vs-terminal-menu.png)

An diesem Punkt können Sie wählen, einen schreibgeschützten oder Lese-/Schreibzugriff Terminal aus dem Menü. Wenn Terminal Lese-/Schreibzugriff ist, kann jeder Geben Sie im Terminal auch der Host, der sodass sie mühelos eingreifen, wenn der Gast zu maßgeblich zu verbessern, die Ihnen nicht gefallen. Merken Sie sich, Sie sollten jedoch **gewähren Sie Lese-/Schreibzugriff nur für Gäste, wenn Sie wissen sie tatsächlich benötigen** und bleiben Sie mit nur-Lese Terminals für Szenarien, in dem Sie einfach den Gast die Ausgabe von Befehlen finden Sie unter ausführen.

> [!NOTE]
> Wenn der zusammenarbeitssitzung im schreibgeschützten Modus ist, können nur schreibgeschützte Terminals vom Host freigegeben werden.

Nachdem Sie die Art der freigegebenes Terminal, die Sie starten möchten ausgewählt haben, wird ein neues freigegebenes Terminal für alle Teilnehmer mit den richtigen Berechtigungen angezeigt. Während Visual Studio Code integrierte terminal die Unterstützung hat Visual Studio eine standardmäßig keinen. Aus diesem Grund wird in der Standardeinstellung neues Fenster mit Terminal angezeigt. Aber wenn die [Whack-Terminal Whack-Erweiterung](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), Live Share erstellt stattdessen ein integriertes Terminal. Visual Studio bietet Ihnen einen Link zu der sie beim Starten oder verknüpfen ein freigegebenes Terminal zum ersten Mal installieren.

![Installieren Sie Terminalserver Toast-Benachrichtigung](../media/vs-terminal-install.png)

Um die terminal-Sitzung zu beenden, geben Sie einfach beenden oder schließen Sie die terminal-Fenster und alle werden getrennt.

## <a name="session-states"></a>Sitzungsstatus

Nachdem Sie gestartet haben, oder zusammenarbeitssitzung verknüpft und haben Zugriff auf den freigegebenen Inhalt, wird die Schaltfläche "Teilen", in der oberen rechten Ecke seine Darstellung entsprechend den Status von der aktiven zusammenarbeitssitzung aktualisiert.

Im folgenden sind die Zustände, die Sie in der Regel angezeigt werden:

| Zustand | Schaltfläche | Beschreibung |
|-------|--------|-------------|
| inaktiv | ![Visual Studio-Status: inaktiv](../media/vs-status-share.png) | Es ist keine aktive zusammenarbeitssitzung, und nichts wird freigegeben. |
| Host: Freigeben von In Bearbeitung | ![Visual Studio-Status: Freigeben von in Bearbeitung](../media/vs-status-sharing.png) | Eine zusammenarbeitssitzung beginnt und inhaltsfreigabe beginnt in Kürze. |
| Host: Freigabe | ![Visual Studio-Status: Freigabe active ](../media/vs-status-active.png) | Eine zusammenarbeitssitzung ist aktiv, und Inhalt wird freigegeben. |
| Host: Freigeben von nur-Lese | ![Visual Studio-Status: Freigeben von nur-Lese](../media/vs-status-sharing-read-only.png)| Freigeben einer nur-Lese zusammenarbeitssitzung an. |
| Gast: Beitreten zu Sitzung | ![VS Code-Status: Verknüpfen](../media/vs-status-joining.png) | Verknüpfen eine vorhandene zusammenarbeitssitzung. |
| Gast: Verknüpft | ![Visual Studio-Status: verknüpft](../media/vs-status-joined.png) | Verknüpft und mit einer active zusammenarbeitssitzung und der empfangende freigegebene Inhalte. |
| Gast: Verknüpft wird, schreibgeschützt | ![Visual Studio-Status: verknüpft nur-Lese](../media/vs-status-joined-read-only.png) | Verknüpft und mit einer aktiven schreibgeschützte zusammenarbeitssitzung verbunden sind. |

## <a name="guest-limitations"></a>Gast-Einschränkungen

Es gibt zurzeit einige Nachteile, die Gäste bei der Verwendung der oben beschriebenen Features auftreten, behalten Sitzungshosts Zusammenarbeit die vollständige Funktionalität Tool ihrer Wahl. Über die folgenden Links erhalten Sie weitere Informationen:

- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Unterstützung für Erweiterung](../reference/extensions.md)
- [Alle große Fehler, Features und Einschränkungen](https://aka.ms/vsls-issues)
- [Alle Anfragen zu Features und Einschränkungen](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich folgenden Artikel Weitere Informationen.

- [Schnellstart: Freigeben Sie Ihres ersten Projekts](../quickstart/share.md)
- [Schnellstart: Verknüpfen Sie Ihre erste Sitzung](../quickstart/join.md)
- [Gewusst wie: Zusammenarbeiten Sie mithilfe von Visual Studio Code](vscode.md)
- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

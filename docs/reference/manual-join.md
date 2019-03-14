---
title: Manuelle Joins – Visual Studio Live Share | Microsoft-Dokumentation
description: Informationen zum Verknüpfen mit einer zusammenarbeitssitzung manuell in Visual Studio Live freigeben.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 57d26c2c63bd5b92e62a72368f97bb8aee63313c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255934"
---
# <a name="join-a-session-manually"></a>Manuelles Verknüpfen von einer Sitzungs

Zusätzlich zum Öffnen von links in einem Browser, um eine zusammenarbeitssitzung verknüpfen, können Sie manuell beitreten, indem Sie den Link in einem bereits ausgeführten Tool einfügen. Dies kann nützlich sein, wenn Sie ein anderes Tool verwenden, als Sie in der Regel nicht, oder wenn Sie Probleme bei der Einladung Links aus irgendeinem Grund arbeiten möchten.

Die genauen Anweisungen unterschiedlich [Visual Studio](#join-from-visual-studio) und [Visual Studio Code](#join-from-visual-studio-code), also wählen Sie das Tool, das Sie für Weitere Informationen zu verwenden möchten.

## <a name="join-from-visual-studio-code"></a>Verbinden von Visual Studio-Code

### <a name="1-sign-in"></a>1. Anmelden

>**Hinweis**: Wenn Sie eine zusammenarbeitssitzung als nur-Lese Gast verknüpfen möchten, können Sie die Anmeldung überspringen. Sie haben Zugriff auf die Anzeige und Navigation, um den Code, der freigegeben ist aber nicht in der Lage, Änderungen vornehmen.

![Toast-Benachrichtigung, die für die Anmeldung mit einem Webbrowser aufgefordert](../media/vscode-sign-in-toast.png)

Um zusammenarbeiten können, benötigen Sie SSO in Visual Studio Live Share damit jeder weiß, wer Sie sind. **Klicken Sie auf** auf der "Live Share" Statusleiste Element, oder drücken Sie **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** , und wählen Sie die "Live-Freigabe: Melden Sie sich mit Browser"-Befehl.

![VS Code-Anmeldung auf die Schaltfläche](../media/vscode-sign-in-button.png)

Ihr Browser wird gestartet, während eine Benachrichtigung, starten Sie aufgefordert werden, melden Sie sich bei angezeigt wird. Schließen Sie des Anmeldevorgangs in Ihrem Browser ab, und dann schließen Sie einfach den Browser, wenn fertig.

Wenn Sie Probleme mit Visual Studio Code ausführen, nicht um eine erfolgreiche Anmeldung auswählen, klicken Sie auf den Link "Probleme" auf dem erfolgsbildschirm "im Browser, und befolgen Sie die Anweisungen. Sehen Sie sich [Problembehandlung](../troubleshooting.md#sign-in) Weitere Tipps.

### <a name="2-use-the-join-command"></a>2. Verwenden Sie den joinbefehl

Öffnen Sie die Viewlet Live Share in der Aktivitätsleiste von VS Code, und wählen Sie die "Join zusammenarbeitssitzung..." Symbol "oder der Eintrag.

![Symbol "Viewlet" verknüpfen](../media/vscode-join-viewlet.png)

>**Hinweis**: Wenn Sie als nur-Lese Gast verknüpfen, werden klicken Sie dann aufgefordert, geben Sie einen Anzeigenamen ein, die Teilnehmer, die Sie in der Sitzung identifiziert werden können.

### <a name="3-paste-the-invite-link"></a>3. Fügen Sie den Link für die INVITE-Nachricht

Fügen Sie in der einladungs-URL, die Sie gesendet wurden, und drücken EINGABETASTE, um zu bestätigen.

Das ist alles! Sie sollten mit der zusammenarbeitssitzung vorübergehend verbunden werden.

## <a name="join-from-visual-studio"></a>Verbinden von Visual Studio

### <a name="1-sign-in"></a>1. Anmelden

Nach Abschluss der Installation starten Sie Visual Studio, und melden Sie sich, wenn Sie noch nicht getan haben. Wenn Sie eine andere Anmeldung für Visual Studio als verwenden müssen Ihre [personalisierungskonto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), wechseln Sie zu **Tools &gt; Optionen &gt; Live Share &gt; Benutzerkonto**.

![Melden Sie sich bei Visual Studio](../media/vs-sign-in-button.png)

Immer noch Probleme? Finden Sie unter [Problembehandlung](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. Verwenden Sie den joinbefehl

Wechseln Sie einfach zu **Datei > Join Zusammenarbeitssitzung**.

![Visual Studio-Menü "Join"](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. Fügen Sie den Link für die INVITE-Nachricht

Fügen Sie in der einladungs-URL, die Sie gesendet wurden, und drücken EINGABETASTE, um zu bestätigen.

Das ist alles! Sie sollten mit der zusammenarbeitssitzung vorübergehend verbunden werden.

## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Schnellstart: Freigeben Sie Ihres ersten Projekts](../quickstart/share.md)
- [Schnellstart: Verknüpfen Sie Ihre erste Sitzung](../quickstart/join.md)

Gewusst wie

- [Gewusst wie: Zusammenarbeiten Sie mithilfe von Visual Studio Code](../use/vscode.md)
- [Gewusst wie: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
- [Gewusst wie: Bereitstellen von feedback](../support.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Details zur Linux-Installation](linux.md)
- [Sprach- und Plattformunterstützung](platform-support.md)
- [Unterstützung für Erweiterung](extensions.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

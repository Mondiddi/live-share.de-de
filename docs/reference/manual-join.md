---
title: Manueller Join-Visual Studio Live Share | Microsoft-Dokumentation
description: Informationen zum manuellen beitreten einer Zusammenarbeits Sitzung in Visual Studio Live share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d46cb53a28bfac1c088371ff5eecdb6af0c8420
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019789"
---
# <a name="join-a-session-manually"></a>Manuelles Hinzufügen einer Sitzung

Zusätzlich zum Öffnen eines Links in einem Browser zum beitreten zu einer Zusammenarbeits Sitzung können Sie manuell beitreten, indem Sie den Link in ein bereits ablaufendes Tool einfügen. Dies kann hilfreich sein, wenn Sie ein anderes Tool verwenden möchten als in der Regel, oder wenn Sie Probleme mit dem Aufrufen von Einladungs Links haben, die aus irgendeinem Grund funktionieren.

Die genauen Anweisungen unterscheiden sich zwischen [Visual Studio](#join-from-visual-studio) und [Visual Studio Code](#join-from-visual-studio-code). Wählen Sie also das Tool aus, das Sie verwenden möchten, um weitere Informationen zu erhalten.

## <a name="join-from-visual-studio-code"></a>Join von Visual Studio Code

### <a name="1-sign-in"></a>1. anmelden

>**Hinweis:** Wenn Sie eine Zusammenarbeits Sitzung als Schreib geschütztes "guesasdsat" beitreten möchten, können Sie die Anmeldung überspringen. Sie haben Zugriff auf das Anzeigen und Navigieren in dem Code, der freigegeben ist, aber nicht in der Lage ist, Änderungen vorzunehmen.

![Popupbenachrichtigung mit der Aufforderung, sich über einen Webbrowser anzumelden](../media/vscode-sign-in-toast.png)

Wenn Sie mit anderen Personen zusammenarbeiten möchten, müssen Sie sich in Visual Studio Live Share anmelden, damit diese wissen, wer Sie sind. **Klicken Sie** auf das Element "Live Share" Statusleiste, oder drücken Sie **STRG + UMSCHALT + p/cmd + UMSCHALT + p** , und wählen Sie den Befehl "Live Share: Anmelden mit Browser" aus.

![Schaltfläche zum Anmelden in Visual Studio Code](../media/vscode-sign-in-button.png)

Ihr Browser wird gestartet, während eine Benachrichtigung angezeigt wird, in der Sie aufgefordert werden, sich anzumelden. Schließen Sie den Anmeldevorgang in Ihrem Browser ab. Wenn Sie fertig sind, schließen Sie einfach den Browser.

Wenn beim Auftreten von Problemen vs Code die erfolgreiche Anmeldung nicht erfolgreich ist, klicken Sie auf dem Bildschirm Erfolg im Browser auf den Link "fehlerhaft", und befolgen Sie die Anweisungen. Weitere Tipps finden Sie in der [Problem](../troubleshooting.md#sign-in) Behandlung.

### <a name="2-use-the-join-command"></a>2. verwenden Sie den Join-Befehl.

Öffnen Sie das Live Share Viewlet in der vs Code Aktivitäts Leiste, und wählen Sie die Sitzung "Zusammenarbeits Sitzung beitreten..." aus. Symbol oder Eintrag.

![Viewlet-Symbol für den Beitritt](../media/vscode-join-viewlet.png)

>**Hinweis:** Wenn Sie als Schreib geschützter Gast beitreten, werden Sie aufgefordert, einen anzeigen Amen einzugeben, damit Teilnehmer Sie in der Sitzung identifizieren können.

### <a name="3-paste-the-invite-link"></a>3. Fügen Sie den Einladungslink ein.

Fügen Sie die gesendete Einladungs-URL ein, und drücken Sie die EINGABETASTE, um dies zu bestätigen.

Das ist alles! Nach einigen Augenblicken sollte eine Verbindung mit der Zusammenarbeitssitzung hergestellt werden.

## <a name="join-from-visual-studio"></a>Join aus Visual Studio

### <a name="1-sign-in"></a>1. anmelden

Starten Sie Visual Studio nach der Installation, und melden Sie sich an, falls Sie dies noch nicht getan haben. Wenn Sie eine andere Anmeldung als Ihr [Personalisierungs Konto](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)für Visual Studio verwenden müssen, wechseln Sie zu Extras **&gt; Optionen &gt; Live Share &gt; Benutzerkontos**.

![VS-Anmeldung](../media/vs-sign-in-button.png)

Noch immer Probleme? Siehe [Problem](../troubleshooting.md#sign-in)Behandlung.

### <a name="2-use-the-join-command"></a>2. verwenden Sie den Join-Befehl.

Wechseln Sie einfach zu **Datei > Sitzung Zusammenarbeit beitreten**.

![Beitrittsmenü in Visual Studio](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. Fügen Sie den Einladungslink ein.

Fügen Sie die gesendete Einladungs-URL ein, und drücken Sie die EINGABETASTE, um dies zu bestätigen.

Das ist alles! Nach einigen Augenblicken sollte eine Verbindung mit der Zusammenarbeitssitzung hergestellt werden.

## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Schnellstart: Freigeben des ersten Projekts](../quickstart/share.md)
- [Schnellstart: beitreten zur ersten Sitzung](../quickstart/join.md)

Gewusst wie

- [Gewusst wie: zusammenarbeiten mit Visual Studio Code](../use/vscode.md)
- [Gewusst wie: zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
- [Gewusst wie: Bereitstellen von Feedback](../support.md)

Referenz

- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Details zur Linux-Installation](linux.md)
- [Sprach- und Plattformunterstützung](platform-support.md)
- [Unterstützung für Erweiterung](extensions.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

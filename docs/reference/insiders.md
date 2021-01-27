---
title: Insider | Microsoft-Dokumentation
description: Eine Beschreibung des Kanals ' Insider ' in Visual Studio Live share.
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: a58bf30ad1c6f4c4cecedb1a07ca0482a67f5ec7
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870720"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Insider

Im Visual Studio Live Share Team geht es um das schnelle durchlaufen, das Ausprobieren neuer Ideen und das lauschen an unsere Kunden! Insider bieten unseren Benutzern die Möglichkeit, zunächst alle neuen Features auszuprobieren und Ihr nützliches Feedback zu geben! Erfahren Sie, wie Sie unten [Insider werden](#BecomeanInsider) , und helfen Sie uns dabei, die Zukunft der Entwickler Zusammenarbeit zu gestalten. 

## <a name="new-to-insiders"></a>✨ Von Insider ✨

### <a name="planned-sessions-vs-code"></a>**Geplante Sitzungen (vs Code)**
Wiederverwendbare Sitzungen verfügen jetzt über eine Stelle im Live Share Viewlet. Geplante Sitzungen ermöglichen Ihnen das Erstellen eines Live Share Sitzungs Links im Voraus als Host einer Live Share Sitzung. 


![Geplantes-Session-- ](../media/planned-session-creation-vscode.png)
 *Image mit der Erstellung einer neuen geplanten Sitzung aus dem Viewlet*

Auf diese Weise können Sie diesen Link als Teil ihrer regelmäßig geplanten Besprechungen mit ihren Teams, ihren Interviews oder Ihren paarweise Verknüpfungen freigeben.
Sobald eine solche Sitzung im Voraus geplant ist, können Sie über das Live Share Viewlet direkt darauf zugreifen. 

![das Image "planned-Session-vscode ](../media/planned-session-copylink-vscode.png) *" zeigt "geplante Sitzungen" im Live Share Viewlet an.

>[!TIP]
>Aktivieren Sie Insider für Live share in vs Code, um "geplante >Sitzungen" zu verwenden. Erfahren Sie, wie Sie unten Insider werden. 

' Geplante Sitzungen ' in Visual Studio ist zurzeit nur ein internes Feature. Überprüfen Sie, ob Updates für die Insider-Phase fortgesetzt werden. 


# <a name="pushed-to-public"></a>Per pushübertragung an Public 

Die folgenden Insider-Features wurden per pushübertragung an Public übermittelt.

### <a name="reusable-sessions-vs-code"></a>**Wiederverwendbare Sitzungen (vs Code)**

Live Share können jetzt wiederverwendbare Sitzungen hosten. Wiederverwendbare Sitzungen bieten Ihnen die Möglichkeit, eine Live Share Sitzung für verschiedene Szenarien wiederzuverwenden. Dies bedeutet, dass Sie eine Live Share Sitzung im Voraus für Ihre technischen Interviews planen können, eine wöchentliche Mob-Programming-Sitzung, die gleiche Sitzung verwenden, während Sie einen Freund betreuen, und vieles mehr!

Gehen Sie zum Erstellen einer wiederverwendbaren Sitzung folgendermaßen vor:
1. Wechseln Sie zur `Command Palette` Verwendung von. `Ctrl+Shift+P`
1. Geben Sie "Live SHA..." ein. und klicken Sie auf den Befehl "**_Live Share: wiederverwendbarer Sitzungs Link erstellen_**".

![vscode-Reus ablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Dadurch wird eine wiederverwendbare Sitzung erstellt, und es wird ein Link zu der Datei in die Zwischenablage kopiert. In der unteren rechten Ecke des Editors wird eine Benachrichtigung angezeigt.

![vscode-Reus ablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Ihre wiederverwendbare Sitzung wurde erstellt! Geben Sie den Link für Ihre Sitzungs-Mate frei, und verwenden Sie ihn jedes Mal für den Zugriff auf die Sitzung.

> [!TIP] 
>Eine wiederverwendbare Sitzungs Verknüpfung ist dauerhaft und wird 30 Tage nach dem Erstellungsdatum oder dem Datum der letzten Verwendung beibehalten. Dies bedeutet, dass Sie sich nicht darum kümmern müssen, wenn Sie Ihre Sitzung mindestens einmal alle 30 Tage nutzen. Speichern Sie einfach den Link an einem sicheren Ort, auf den Sie problemlos zugreifen können.
 


## <a name="become-an-insider"></a>Werden Sie Insider <a name="BecomeanInsider"></a>

Standardmäßig verwenden Sie nach der Installation der Visual Studio Live Share Erweiterung den `Stable` Featuresatz, der alle Funktionen für die Bereitstellung (z. b. Co-Bearbeitung, frei gegebenes Debuggen, Terminals) umfasst. Wenn Sie jedoch einen frühen Zugriff auf das Feature erhalten möchten, an dem wir arbeiten, können Sie die featuremenge abonnieren, `Insiders` indem Sie die folgende Einstellung in Ihrer IDE ändern:

* Visual Studio

    ![Feature-Set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![Feature-Set-vscode](../media/feature-set-vscode.png)

In den folgenden Abschnitten werden die Funktionen beschrieben, die derzeit in der `Insiders` Featuregruppe enthalten sind und daher zur Auswertung bereit sind, sobald Sie die oben genannte Einstellung ändern:



## <a name="see-also"></a>Weitere Informationen

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

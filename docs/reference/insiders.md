---
title: Insider-Visual Studio Live Share | Microsoft-Dokumentation
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
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062285"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Insider

Im Visual Studio Live Share Team geht es um das schnelle durchlaufen, das Ausprobieren neuer Ideen und das lauschen an unsere Kunden! Insider bieten unseren Benutzern die Möglichkeit, zunächst alle neuen Features auszuprobieren und Ihr nützliches Feedback zu geben! Erfahren Sie, wie Sie unten [Insider werden](#BecomeanInsider) , und helfen Sie uns dabei, die Zukunft der Entwickler Zusammenarbeit zu gestalten. 

## <a name="new-to-insiders"></a>✨ Von Insider ✨


### <a name="reusable-sessions-vs-code"></a>**Wiederverwendbare Sitzungen (vs Code)**

Live Share können jetzt wiederverwendbare Sitzungen hosten. Wiederverwendbare Sitzungen bieten Ihnen die Möglichkeit, eine Live Share Sitzung für verschiedene Szenarien wiederzuverwenden. Dies bedeutet, dass Sie eine Live Share Sitzung im Voraus für Ihre technischen Interviews planen können, eine wöchentliche Mob-Programming-Sitzung, die gleiche Sitzung verwenden, während Sie einen Freund betreuen, und vieles mehr!

Gehen Sie zum Erstellen einer wiederverwendbaren Sitzung folgendermaßen vor:
1. Wechseln Sie zur `Command Palette` Verwendung von.`Ctrl+Shift+P`
1. Geben Sie "Live SHA..." ein. und klicken Sie auf**die_Live Share: Befehl zum Erstellen eines_wiederverwendbaren Sitzungs Links**.

![vscode-Reus ablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Dadurch wird eine wiederverwendbare Sitzung erstellt, und es wird ein Link zu der Datei in die Zwischenablage kopiert. In der unteren rechten Ecke des Editors wird eine Benachrichtigung angezeigt.

![vscode-Reus ablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Ihre wiederverwendbare Sitzung wurde erstellt! Geben Sie den Link für Ihre Sitzungs-Mate frei, und verwenden Sie ihn jedes Mal für den Zugriff auf die Sitzung.

> [!TIP] 
>Eine wiederverwendbare Sitzungs Verknüpfung ist dauerhaft und wird 30 Tage nach dem Erstellungsdatum oder dem Datum der letzten Verwendung beibehalten. Dies bedeutet, dass Sie sich nicht darum kümmern müssen, wenn Sie Ihre Sitzung mindestens einmal alle 30 Tage nutzen. Speichern Sie einfach den Link an einem sicheren Ort, auf den Sie problemlos zugreifen können.
 

### <a name="direct-user-invitations"></a>**Direkte Benutzer Einladungen**

Derzeit stellen sowohl Visual Studio als auch Visual Studio Code einen `Contacts` Bereich bereit, der zwei wichtige Funktionen ermöglicht:

1. Anzeigen einer Liste von `Suggested Contacts`, bei denen es sich um Entwickler handelt, die in den letzten 30 Tagen zu Ihrem aktuell geöffneten Projekt beigetragen haben. In der Praxis sind dies die Personen, mit denen Sie wahrscheinlich zusammenarbeiten möchten. Daher empfehlen wir Ihnen, die ersten Schritte zu erleichtern.

2. Bereitstellen der Liste `Recent Contacts`von, bei denen es sich um Entwickler handelt, mit denen Sie zuvor zusammengearbeitet haben Live share. In der Praxis arbeiten die meisten Entwickler häufig mit denselben Personen zusammen, und aus diesem Grund ermöglicht die aktuelle Liste eine wiederholbare Methode der Arbeit mit Ihrem Team/Classroom/usw.

Allerdings können `Contacts` Sie mit der Liste zurzeit nur aktuelle/vorgeschlagene Kontakte per e-Mail einladen, was wir gelernt haben, ist nicht so effizient wie möglich. Wenn Sie das neueste Live Share Update installieren und aktivieren `Insiders` (wie oben beschrieben), können Sie Entwickler jetzt **direkt aus der IDE in eine Zusammenarbeits Sitzung einladen**. Beachten Sie Folgendes: Wenn Sie Visual Studio Code verwenden, müssen Sie den Insider- [Build](https://code.visualstudio.com/insiders/) installieren, damit dieses Feature funktioniert.

![Direct invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Ein Live Share Host (links), der einen Peer (rechts) direkt in eine Sitzung lädt.</em>

Nachdem sich die Entwickler mit Live Share angemeldet haben, wird Ihr Verfügbarkeitsstatus auf Ihren Peers veröffentlicht. Demzufolge können Sie sehen, dass jemand in Ihrem Team Online ist, und dann sofort mit der Zusammenarbeit beginnen. Sie erhalten eine Popup Benachrichtigung, die Ihnen die Möglichkeit gibt, der Sitzung beizutreten. Dadurch ist es nicht mehr erforderlich, Sitzungs-URLs vollständig auszutauschen.

Nach 5 Minuten Inaktivität wechselt der Status automatisch zu `Away`, und wenn Sie sich in einer Live Share Sitzung befinden, wechselt der Status automatisch zu (der die Benachrichtigungs Popup Benachrichtigungen unter `Do not disturb` stützt). Nachdem Sie erneut aktiviert und/oder eine Live Share Sitzung verlassen haben, wechselt der Status automatisch zurück zu `Available`. Mit diesem Verhalten müssen Sie den Live Share Status nicht tatsächlich verwalten. Es ist einfach, direkte Einladungen zu ermöglichen und ihren Peers mitzuteilen, ob Sie für die Zusammenarbeit verfügbar sind oder nicht. Sie können Ihren Status jedoch immer manuell festlegen, wenn Sie dies bevorzugen.

Wenn Sie dieses Feature deaktivieren möchten, können Sie die `Presence` Einstellung einfach in den Live Share Einstellungen in Visual Studio und Visual Studio Code deaktivieren. Nach der Deaktivierung sind Sie weiterhin in der Lage, den Status anderer anzuzeigen und zu laden, Ihr Status wird jedoch nicht veröffentlicht, und andere Benutzer können Sie nicht direkt einladen.

 

## Werden Sie Insider <a name="BecomeanInsider"></a>

Standardmäßig verwenden Sie nach der Installation der Visual Studio Live Share Erweiterung den `Stable` Featuresatz, der alle Funktionen für die Bereitstellung (z. b. Co-Bearbeitung, frei gegebenes Debuggen, Terminals) umfasst. Wenn Sie jedoch einen frühen Zugriff auf das Feature erhalten möchten, an dem wir arbeiten, können Sie die `Insiders` featuremenge abonnieren, indem Sie die folgende Einstellung in Ihrer IDE ändern:

* Visual Studio

    ![Feature-Set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![Feature-Set-vscode](../media/feature-set-vscode.png)

In den folgenden Abschnitten werden die Funktionen beschrieben, die derzeit in der `Insiders` Featuregruppe enthalten sind und daher zur Auswertung bereit sind, sobald Sie die oben genannte Einstellung ändern:



## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

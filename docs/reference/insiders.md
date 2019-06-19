---
title: 'Visual Studio-Livefreigabe-Insider: | Microsoft-Dokumentation'
description: Eine Beschreibung des Kanals "Insider" in Visual Studio Live Share.
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192722"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Insider

Das Visual Studio Live Share-Team versucht, in der Reihenfolge auf Benutzerfeedback schnell durchlaufen und als Teil eines solchen bieten wir zwei separate Funktion "Kanälen", mit denen Sie festlegen, wie schnell Sie neue Funktionen erhalten. Standardmäßig nach der Installation der Visual Studio Live Share-Erweiterungs, Sie verwenden die `Stable` Funktion festgelegt ist, enthält alle Funktionen bereit für die Produktion (z. B. gleichzeitig bearbeiten, freigegebene Terminals Debuggen). Aber wenn Sie möchten, um frühen Zugriff auf die Funktion zu erhalten, arbeiten wir an, Sie können sich für die `Insiders` Funktionen durch Ändern der folgenden Einstellung in Ihrer IDE:

* Visual Studio

    ![feature-set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

Die folgenden Abschnitte beschreiben den Satz von Funktionen, die derzeit in der `Insiders` Funktionsumfang und aus diesem Grund können bewerten, nachdem Sie die oben genannte Einstellung zu ändern:

## <a name="direct-user-invitations"></a>Leiten Sie Benutzer Einladungen

Bieten Sie derzeit Visual Studio und Visual Studio Code eine `Contacts` Bereich, in dem zwei wichtige Funktionen ermöglicht:

1. Zeigt eine Liste der `Suggested Contacts`, die Entwickler, die dem aktuell geöffneten Projekt, innerhalb der letzten 30 Tage beigetragen haben sind. Klicken Sie in der Praxis Hierbei handelt es sich um den Leuten, die Sie möglicherweise eine Zusammenarbeit ermöglichen möchten, und aus diesem Grund sollten sie damit für den Einstieg erleichtern.

2. Bereitstellung einer Liste der `Recent Contacts`, die Sie zuvor mit der Verwendung von Live Share zusammengearbeitet haben Entwickler sind. Die meisten Entwickler zusammenarbeiten häufig die gleichen Personen, und aus diesem Grund kann die Liste der zuletzt verwendeten eine mehr wiederholbar bedeutet, dass für die Arbeit mit Ihrem Team, Classroom usw., in der Praxis.

Allerdings die `Contacts` Liste derzeit lässt nur dazu einladen, aktuelle/vorgeschlagenen Kontakte per E-mail, die wir gelernt haben ist nicht so effizient wie möglich ausfällt. Wenn Sie das neueste Live Share-Update zu installieren, und aktivieren `Insiders` (wie oben beschrieben), Sie werden nun möglicherweise **einladen von Entwicklern in einer zusammenarbeitssitzung direkt aus der IDE**! Beachten Sie, dass wenn Sie Visual Studio Code verwenden, Sie zum Installieren müssen der [Insiders-Build](https://code.visualstudio.com/insiders/) in der Reihenfolge für dieses Feature funktioniert.

![Direkte Invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Eine Live Share-Host (links) direkt einladen von einem Peer (rechts) in einer Sitzung</em>

Wenn Entwickler mit Live-Freigabe, Anmeldung ihren Verfügbarkeitsstatus Kollegen veröffentlicht werden. Daher sehen Sie sich, dass jemand in Ihrem Team ist online, und klicken Sie dann sofort mit ihnen zusammenarbeiten. Sie erhalten eine Popupbenachrichtigung, die ihnen die Möglichkeit, die der Sitzung beizutreten, oder nicht gewährt werden. Dadurch wird die Notwendigkeit zum Austauschen von Sitzung URLs vollständig entfernt.

Nach 5 Minuten der Inaktivität, Ihren Status wechselt automatisch zum `Away`, und wenn Sie innerhalb einer Live Share-Sitzung sind, Ihren Status wechselt automatisch zum `Do not disturb` (die Einladung-Popupbenachrichtigungen von Suprresses). Nachdem Sie erneut aktiv, und/oder hinterlassen Sie eine Live Share-Sitzung, Ihren Status wechselt automatisch an `Available`. Mit diesem Verhalten müssen Sie nicht den Status Ihres Live Share tatsächlich zu verwalten. Es dient lediglich dazu, aktivieren direkte Einladungen und kommunizieren Sie mit Ihren Kollegen, unabhängig davon, ob Sie für die Zusammenarbeit verfügbar oder nicht. Allerdings können Sie Ihren studentenstatus immer manuell festlegen, falls gewünscht.

Wenn Sie diese Funktion deaktivieren möchten, können Sie einfach Deaktivieren der `Presence` in den Live Share-Einstellungen in Visual Studio und Visual Studio Code festlegen. Laden Sie Sie, sobald deaktiviert, Sie werden weiterhin in der Lage zu anderen Status angezeigt, die sie einladen, aber Ihr Status wird nicht veröffentlicht werden, und andere jedoch nicht direkt.

## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

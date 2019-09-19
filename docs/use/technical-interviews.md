---
title: Zusammenarbeiten in Visual Studio Code – Visual Studio Live Share | Microsoft-Dokumentation
description: Vorgehensweisen zur Zusammenarbeit in Visual Studio Code und Live Share
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fishah
ms.author: fishah
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: ba2fd7558df2658efffda1c8578450f9c678d35d
ms.sourcegitcommit: 21e564ac23293e373b515892fa881d049f333cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127419"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Vorgehensweise: Technische Interviews mithilfe von Live Share

Bevor Sie mit der Verwendung von Live Share für technische Interviews beginnen, müssen Sie einen integralen Schritt ausführen: **Laden Sie Visual Studio Code und das Live Share Extension Pack aus seinem Marketplace herunter, indem Sie die** folgenden [Schritte ausführen.](../use/vscode.md#Installation)

Live Share bietet Ihnen die Möglichkeit, wiederverwendbare Sitzungen zu hosten. Dies bedeutet, dass Sie eine Live Share Sitzung im Voraus für Ihre technischen Interviews planen können und sich keine Gedanken über den Verbindungs Ablauf machen können.

> [!TIP] 
>Eine wiederverwendbare Sitzungs Verknüpfung ist dauerhaft und wird 30 Tage nach dem Erstellungsdatum oder dem Datum der letzten Verwendung beibehalten. Stellen Sie beim Erstellen einer wiederverwendbaren Sitzungs Verknüpfung für Ihr Interview sicher, dass das Gespräch innerhalb von 30 Tagen nach dem Datum der Erstellung des Links liegt. Wenn der Link abläuft, erstellen Sie einfach eine neue wiederverwendbare Sitzung. (Es gibt eine Möglichkeit, um sicherzustellen, dass der Link nie abläuft, aber dies ist für Interviews einfacher!)

### <a name="what-to-do-as-an-interviewer"></a>**Was muss ich als Interviewer tun?**

Als Interviewer fungieren Sie als Host der Live Share Sitzung. Wenn Sie mit Live Share nicht vertraut sind, empfehlen wir Ihnen, sich im Abschnitt [Freigeben eines Projekts](../use/vscode.md) dieses Handbuchs zu informieren.

Nachdem Sie nun eine Live Share Sitzung für Ihr technisches Interview erstellt haben, erstellen Sie anstelle der regulären Zusammenarbeits Sitzung eine spezielle "wiederverwendbare Sitzung". Dadurch haben Sie die Möglichkeit, eine Live Share Sitzung zu verwenden, die im Voraus geplant und dann jederzeit verwendet werden kann.

Gehen Sie zum Erstellen einer wiederverwendbaren Sitzung folgendermaßen vor:

1. Wechseln Sie zur `Command Palette` Verwendung von.`Ctrl+Shift+P`
1. Geben Sie "Live SHA..." ein. und klicken Sie auf**die_Live Share: Befehl zum Erstellen eines_wiederverwendbaren Sitzungs Links**.

![vscode-Reus ablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Dadurch wird eine wiederverwendbare Sitzung erstellt, und es wird ein Link zu der Datei in die Zwischenablage kopiert. In der unteren rechten Ecke des Editors wird eine Benachrichtigung angezeigt.

![vscode-Reus ablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Ihre wiederverwendbare Sitzung wurde erstellt! Geben Sie den Link für Ihre Sitzungs-Mate frei, und verwenden Sie ihn jedes Mal für den Zugriff auf die Sitzung.

Wenn Sie über diesen Link verfügen, geben Sie ihn einfach über eine e-Mail oder den gewählten planungsmechanismus für das Interview frei. Alles, was Sie tun müssen, ist, dass Sie zum Zeitpunkt des Interviews auf diesen Link klicken, und Sie befinden sich in einer Live Share Sitzung. 

### <a name="what-to-do-as-the-interviewee"></a>**Was ist mit dem Interviewten zu tun?**

Wenn Sie mit Live Share ein technisches Interview erwarten möchten, haben Sie Glück! Wir möchten sicherstellen, dass Sie mit den grundlegenden Live Share Features vertraut sind, damit Sie sich während Ihres Interviews zufrieden sind.

1. Nehmen Sie sich vor dem Vorstellungsgespräch etwas Zeit, und überprüfen Sie das Handbuch, um [zu](../use/vscode.md) verstehen, wie Live Share funktioniert.

1. Möglicherweise möchten Sie Visual Studio Code vorab installieren, damit Sie nicht auf den Abschluss der Installation warten, nachdem Sie Ihr Interview gestartet haben.

1. Wenn Sie nicht über die Zeit verfügen, machen Sie sich keine Sorgen. Sie benötigen lediglich einen Link zu einer Live Share Sitzung, die ihr Interviewer bei der Planung des Interviews sendet. Wenn Sie einfach auf den Link klicken, werden Sie automatisch alle erforderlichen Schritte durchführen.

1. Klicken Sie zum Zeitpunkt des Interviews einfach auf den Link, und befolgen Sie die Schritte, die Sie durchführen. Wenn Sie früh dran sind oder Ihr Interviewer das Gespräch zu spät ist, machen Sie sich keine Sorgen! Sie befinden sich einfach in der "Lobby", die darauf wartet, dass Ihr Interviewer beitreten kann. Es sind keine weiteren Schritte erforderlich, und sobald der Interviewer an der Sitzung teilnimmt, wird er automatisch gestartet.

>[!NOTE]
>Wenn Sie feststellen, dass die Sitzung vor oder nach dem Beitritt des Interviewers getrennt wurde, machen Sie sich keine Sorgen. Beenden Sie diese Sitzung, wenn Sie nicht bereits geschlossen ist, und klicken Sie erneut auf denselben Link.

Sie sind jetzt für die Verwendung von Live Share für Ihr Interview festgelegt! 

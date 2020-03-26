---
title: Zusammenarbeiten in Visual Studio Code – Visual Studio Live Share | Microsoft-Dokumentation
description: Vorgehensweisen zur Zusammenarbeit in Visual Studio Code und Live Share
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: 0ac1ba213c59df2dc3b1d05d89e4186c823a250f
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295958"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Vorgehensweise: technische Interviews mithilfe von Live Share

Die Verwendung von Live Share für Interviews ermöglicht es dem Interviewer und dem Kandidaten, eine schnelle und zuverlässige Interview Sitzung mit einer vollständig präzisen IDE oder einem Editor zu haben. 


## <a name="setup-for-interviewer"></a>Setup für den Interviewer 
Wenn Sie einen Kandidaten mit Live Share interviewen möchten, müssen Sie zunächst einen der beiden Desktop Clients:

Installieren Sie [Visual Studio](../use/vs.md) , das mit der Live Share-Erweiterung integriert ist.

>[!TIP] 
> Stellen Sie sicher, dass Sie Insider für Live Share aktivieren, indem Sie zu Extras *> Optionen > Live Share > Erweiterte > Features*wechseln. Dies ermöglicht es Ihnen, unsere integrierte audioaufruf-Unterstützung für Interviews zu verwenden.

Oder installieren Sie [Visual Studio Code](../.use/vscode.md) , und laden Sie das [Live Share Extension Pack]() aus dem Marketplace herunter. Das Erweiterungspaket stellt Ihnen unsere Audiounterstützung für Interviews bereit. 

## <a name="scheduling-an-interview"></a>Planen eines Interviews 

**Live share in vs Code** bietet Ihnen die Möglichkeit, Live Share Sitzungen im Voraus zu erstellen. Sie können die folgenden Schritte ausführen, um eine Sitzung im Voraus zu erstellen:

1. Wechseln Sie mit `Ctrl+Shift+P` zum `Command Palette`.
1. Geben Sie "Live SHA..." ein. und klicken Sie auf den Befehl "_Live Share: wiederverwendbarer Sitzungs Link erstellen_".

![vscode-Reus ablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Dadurch wird eine wiederverwendbare Sitzung erstellt, und es wird ein Link zu der Datei in die Zwischenablage kopiert. In der unteren rechten Ecke des Editors wird eine Benachrichtigung angezeigt.

![vscode-Reus ablesessionnotif](../media/vscode-notification-resuablesession.png)

4. senden Sie den Link.

Wenn Sie über diesen Link verfügen, geben Sie ihn einfach über eine e-Mail oder den gewählten planungsmechanismus für das Interview frei. Alles, was Sie tun müssen, ist, dass Sie zum Zeitpunkt des Interviews auf diesen Link klicken, und Sie befinden sich in einer Live Share Sitzung. 
> [!TIP] 
>Eine wiederverwendbare Sitzungs Verknüpfung ist dauerhaft und wird 30 Tage nach dem Erstellungsdatum oder dem Datum der letzten Verwendung beibehalten. Stellen Sie beim Erstellen einer wiederverwendbaren Sitzungs Verknüpfung für Ihr Interview sicher, dass das Gespräch innerhalb von 30 Tagen nach dem Datum der Erstellung des Links liegt. Wenn der Link abläuft, erstellen Sie einfach eine neue wiederverwendbare Sitzung. (Es gibt eine Möglichkeit, um sicherzustellen, dass der Link nie abläuft, aber dies ist für Interviews einfacher!)

**Hinweis:** Derzeit ist Live share in Visual Studio nicht in der Lage, Sitzungen im Voraus zu erstellen. Bei Interviews, die Sie mithilfe von Live share in Visual Studio durchführen, können Sie in unserem Leitfaden zum Starten einer sofortigen [Live Share Sitzung finden](../quickstart/share.md) .



## <a name="setup-for-candidate"></a>Setup für Kandidaten
Obwohl ein Kandidat immer entweder Visual Studio oder Visual Studio Code installieren kann, um dem Gespräch beizutreten, ist dies nicht erforderlich. **Live Share interviewsitzungen können ohne vorherige Einrichtung über Kandidaten verknüpft werden.** Sie können zum Zeitpunkt der Sitzung auf den Link zum Gespräch klicken und sich über **den Browser anmelden**. Weitere Informationen [finden Sie hier.](../quickstart/browser-join.md)



<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->
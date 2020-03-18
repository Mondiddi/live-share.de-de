---
title: Beitreten aus dem Browser-Visual Studio Live Share | Microsoft-Dokumentation
description: Einführung in den Wei-Browser
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510636"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Vorschau] ✨ beitreten zu einer Live Share Sitzung über den Browser

Alle Live Share Zusammenarbeits Sitzungen können nun aus dem Browser verknüpft werden. Dies bedeutet, dass ein Gast ihrer Sitzung nicht mehr vs Code oder Visual Studio installieren muss, um der Sitzung beizutreten. Dies ist besonders hilfreich für alle diese Instanzen, wenn Sie möchten, dass ein Benutzer schnell in Ihre Sitzung gelangt, oder für Studenten, die die Desktop Clients oft nicht installiert haben.

> [!TIP]
> Weitere Informationen zu den häufigsten Fragen zum beitreten aus dem Browser finden Sie unten im Abschnitt mit den häufig gestellten Fragen.

# <a name="how-to-join-a-live-share-session-from-the-browser"></a>Beitreten zu einer Live Share Sitzung über den Browser 

### <a name="1-host-starts-session"></a>1. Host: startet die Sitzung. 
Zunächst sollte der Host entweder in Visual Studio oder vs Code wechseln, um eine Zusammenarbeits Sitzung zu starten. Wenn der Host einen Ordner oder ein Projekt freigibt.

![Animation der Sitzung wird gestartet](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. Gast: verwendet freigegebenen Link zum beitreten aus dem Browser. 
Live Share generiert einen joinlink, der für den Gast freigegeben werden kann. Der Gast kann nun mithilfe dieses Links zu einer Webseite navigieren, die ihm nun die Möglichkeit bietet, mit dem Browser fortzufahren.

![Animation für das beitreten zu einer Sitzung](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. Gast: genießen Sie die Zusammenarbeit mit voller Treue in Browser 
Nachdem der Gast der Sitzung beigetreten ist, kann er genauso wie bei der Zusammenarbeit mit den Desktop Clients weiter gehen.

![Animation der vollständigen Treue](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. gibt es eine Umgebung, die im Hintergrund ausgeführt wird, die meine Sitzung im Browser gehostet?
Wenn Sie eine Live Share Sitzung über den Browser hinzufügen, wird keine neue Umgebung hochgefahren. Dabei handelt es sich um einen Server losen Dienst. 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. muss ich für den Dienst zum beitreten aus dem Browser bezahlen?
Das beitreten aus dem Browser ist kostenlos, ähnlich wie alle Live share.

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. wie unterscheidet sich dies von Visual Studio Online?
Wenn Sie über den Browser beitreten, greifen Sie während der Sitzung nur über den Browser auf den vs Code-Client zu. Sobald die Sitzung beendet ist, werden alle Dateien und Ordner zusammen mit den Editorfunktionen geschlossen. Wenn Sie einen Editor im Browser verwenden möchten, der in ihrer eigenen Umgebung zum Bearbeiten Ihrer eigenen Dateien gesichert ist, müssen Sie [Visual Studio Online verwenden.](aka.ms/vso)

##### <a name="4-does-this-work-for-all-browsers"></a>4. funktioniert das für alle Browser?
Ja. Dies funktioniert für alle Browser. 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. gibt es einen vs-Client, der im Browser verwendet werden kann?
Das ist noch nicht verfügbar. 

# <a name="feedback-and-issues"></a>Feedback und Probleme 
Dies ist ein Vorschau Feature, und wir hoffen, dass Sie Benutzer Feedback erhalten, um die Benutzer Funktionalität zu verbessern. Füllen Sie hier Feedback oder Probleme aus, die Sie in unserem GitHub-Repository sehen [.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)
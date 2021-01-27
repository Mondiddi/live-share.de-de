---
title: Beitreten aus dem Browser | Microsoft-Dokumentation
description: Einführung in den Browser
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 277ad0296c453a0220c500abc1754ebabab53638
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870763"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Vorschau] ✨ beitreten zu einer Live Share Sitzung über den Browser

Alle Live Share Zusammenarbeits Sitzungen können nun über den Browser verknüpft werden. Dies bedeutet, dass ein Gast ihrer Sitzung nicht mehr vs Code oder Visual Studio installieren muss, um der Sitzung beizutreten. Dies ist besonders hilfreich für alle diese Instanzen, wenn Sie möchten, dass ein Benutzer schnell in Ihre Sitzung gelangt, oder für Studenten, die die Desktop Clients oft nicht installiert haben.


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

<!---
# Frequently asked questions 

##### 1. Is there an environment running in the background, that is hosting my session in the browser?
When you join a Live Share session from the browser, there is no new environment spun up. It is a serverless service. 
##### 2. Do I have to pay for the service of joining from the browser?
Joining from the browser is free, much like all of Live Share.

##### 3. How is this different from Visual Studio Online?
When you join from the browser, you only access the VS Code client from the browser during the session. Once the session ends, all the files and folders along with editor capabilities will close. To use an editor in the browser, backed with your own environment to edit your own files, you must use [Visual Studio Online.](aka.ms/vso)

##### 4. Does this work for all browsers?
Yes. This works on all browsers. 
##### 5. Is there a VS client that I can use in the browser?
We do not have this available yet. 

# Feedback and issues 
This is a preview feature, and we hope to get user feedback to improve the experience. Please fill out any feedback or issues you see on our GitHub repo [here.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)

--->

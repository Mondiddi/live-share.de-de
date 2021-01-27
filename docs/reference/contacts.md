---
title: Anwesenheit | Microsoft-Dokumentation
description: Informationen zum Anwesenheits Dienst für Kontakte für Visual Studio Live share.
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: b13acd28ac7a13d90633bfdb6427a87c1c47609a
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870750"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Kontakte in Live Share 

Sie haben Live Share verwendet und bemerken, dass das Senden von Links über eine externe Anwendung (z. b. Chat oder e-Mail) wirklich schnell ist? Wir wissen, dass Sie, wenn wir die Zusammenarbeit fördern möchten, die geringste Menge an Reibung benötigen, damit Sie Sie schätzen können. Dies ist der Grund, warum Live Share jetzt **Kontakte** mit dem **Status** hat.

>Kontakte werden automatisch für alle Versionen von **Live Share v 1.0.950** oder höher aktiviert.

Kontakte werden in Ihrem Live Share Fenster als separater Bereich angezeigt, wie in der folgenden Abbildung gezeigt: 

![Kontakte](../media/vscode-contacts-intro.png)

<em> Anzeige von Kontakten im Fenster "Live Share"</em>
## <a name="who-shows-up-in-my-contacts"></a>Wer wird in meinen Kontakten angezeigt?

In Ihrem Kontaktbereich werden zwei Arten von Kontakten angezeigt, die die natürlichen Workflows von Entwicklern bei der Arbeit unterstützen.
### <a name="1-recent-contacts"></a>1. aktuelle Kontakte  
 Dabei handelt es sich um Entwickler, die Sie zuvor mit Live Share zusammengearbeitet haben. In der Praxis arbeiten die meisten Entwickler häufig mit denselben Personen zusammen, und aus diesem Grund ermöglicht die aktuelle Liste eine wiederholbare Methode der Arbeit mit Ihrem Team/Classroom/usw.
### <a name="2-suggested-contacts"></a>2. vorgeschlagene Kontakte
Dabei handelt es sich um Entwickler, die innerhalb der letzten 30 Tage zu Ihrem aktuell geöffneten Projekt beigetragen haben. In der Praxis sind dies die Personen, mit denen Sie wahrscheinlich zusammenarbeiten möchten. Daher empfehlen wir Ihnen, die ersten Schritte zu erleichtern.

## <a name="direct-user-invitations"></a>Direkte Benutzer Einladungen 
Alle Kontakte können im Editor direkt zu einer Live Share Sitzung eingeladen werden. Sie erhalten eine Popup Benachrichtigung, die Ihnen die Möglichkeit gibt, der Sitzung beizutreten. Dadurch ist es nicht mehr erforderlich, Sitzungs-URLs vollständig auszutauschen.
![Directinvitationvscode ](https://user-images.githubusercontent.com/51928518/66443914-e59c5d00-e9f5-11e9-957a-b1a92949d660.gif)
 <em>a Live Share Host (links) lädt einen Peer (rechts) direkt in eine Sitzung</em> ein.

## <a name="how-does-status-for-contacts-work"></a>Wie funktioniert der Status für Kontakte?
Nachdem sich die Entwickler mit Live Share angemeldet haben, **wird Ihr Verfügbarkeitsstatus auf Ihren Peers veröffentlicht.** Demzufolge können Sie sehen, dass jemand in Ihrem Team Online ist, und dann sofort mit der Zusammenarbeit mit Ihnen beginnen, wie oben gezeigt.
Der Status kann direkt innerhalb des Editors festgelegt werden, sodass Sie Ihnen die Verfügbarkeit für das Team signalisieren können, ohne dass ein Kontextwechsel erforderlich ist. Live Share Kontakte haben derzeit vier Status:

**1. verfügbar:** der Standardstatus lautet `Available` , wenn Sie über die Live Share-Erweiterung verfügen und den Editor aktiv verwenden, während Sie sich nicht in einer Sitzung befinden.

**2. nicht stören:** Ihr Status ist auf festgelegt, `Do not disturb` Wenn Sie sich derzeit in einer aktiven Live Share Sitzung befinden und alle Einladungs Benachrichtigungen unterdrückt werden.

**3. Entfernung:** nach 5 Minuten Inaktivität wechselt der Status automatisch zu `Away` .

**4. offline:** Sie werden offline geschaltet, sobald Sie für einen längeren Zeitraum nicht mehr ausreichen, oder wenn Sie sich für den [Freigabe Status entscheiden](##ManagingPresence) .


## <a name="managing-contacts-and-sharing-status"></a>Verwalten von Kontakten und Freigabe<a name="ManagingPresence"> </a> Status

Wenn Sie dieses Feature ablehnen möchten, können Sie es auf zweierlei Weise tun.
1. Sie können die Statuseinstellung deaktivieren, indem Sie auswählen `offline` . Nach der Deaktivierung sind Sie weiterhin in der Lage, den Status anderer anzuzeigen und zu laden, Ihr Status wird jedoch nicht veröffentlicht, und andere Benutzer können Sie nicht direkt einladen.
Sie können offline schalten, indem Sie auf den Status Kreis klicken. Daraufhin wird das folgende Dropdown Menü angezeigt:

![dropdownstatus ](../media/vscode-presence-opt-out.png)
 <em> mit einer Dropdown Liste von Anwesenheits Zuständen</em>

2. Sie können öffnen `user settings` und zu *Erweiterungen > Visual Studio Live Share > Live Share: Anwesenheit* wechseln und den Anwesenheits Dienst deaktivieren. Nach der Deaktivierung sind Sie weiterhin in der Lage, den Status anderer anzuzeigen und zu laden, Ihr Status wird jedoch nicht veröffentlicht, und andere Benutzer können Sie nicht direkt einladen.

![presencesettings](../media/vscode-presence-setting.png)

## <a name="faqs"></a>FAQ 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. wird der Freigabe Status automatisch verwendet, wenn ich Live Share v 1.0.950 und höher verwende?

Beim ersten Mal, wenn Sie Kontakte sehen, werden Sie mit einem Toast benachrichtigt, und Sie können die Freigabe Ihres Status ablehnen. Danach geben Sie Ihren Kontakt automatisch mit Ihren Kontakten frei, es sei denn, Sie entscheiden sich dafür, wie oben gezeigt.

###### <a name="2-can-i-add-my-own-contacts"></a>2. kann ich meine eigenen Kontakte hinzufügen?

Zurzeit erkennt unser Contacts-Dienst automatisch die Mitarbeiter, die Sie häufig mit dem Code gemeinsam nutzen, und bietet Ihnen nicht die Möglichkeit, ihre eigenen Kontakte hinzuzufügen. 


>Stellen Sie sich vor, dass Sie Kontakte manuell hinzufügen können. Helfen Sie uns, dies zu priorisieren, indem Sie hier eine GitHub-Funktions Anforderung öffnen [.](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 
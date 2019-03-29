---
title: Benutzerprofil – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Eine Übersicht über das Anzeigen und entfernen Ihr Visual Studio Live Share-Benutzerprofil.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 38fb6fada1030bddac8f3437f19f0ae259f5626e
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640028"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Benutzerprofil

Wenn Sie mit Visual Studio Live Share authentifizieren, es wird ein Benutzerprofil erstellt, dadurch alle Teilnehmer können Sie mit zusammenarbeiten, um festzustellen, wer Sie sind (z. B. Ihre e-Mail-Adresse, ein Avatar). Zu jedem Zeitpunkt ist können Sie die Profilinformationen anzeigen, die Live Share in Ihrem Namen durch Navigieren zu einer der folgenden Seiten (abhängig vom verwendeten Identitätsanbieter) gespeichert ist:

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

Die Seite, Sie werden aufgefordert, anmelden, um Ihre Identität überprüfen und angezeigt klicken Sie dann die unformatierte JSON-Ausgabe Ihres Benutzerprofils.

<img width="500px" src="media/user-profile.png" />

Wenn Visual Studio Live Share derzeit über ein Profil für die Identität, die mit dem Sie angemeldet gespeicherten verfügt, wird es Sie auch wissen, dass können.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Entfernen Ihr Profil

Wenn Sie Ihr Benutzerprofil entfernen möchten, können Sie den Link, mit der Bezeichnung klicken `Click here to get your data removed from our systems` auf die [Benutzerprofilseite](#user-profile). Alternativ können Sie besuchen die folgenden Seiten direkt (je nach den Identitätsanbieter, die, den Sie verwendet, wird):

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

Anderenfalls wird Visual Studio Live Share automatisch Ihr Profil 30 Tage nach der letzten erfolgreichen Anmeldung löschen. In diesem Kontext bezieht sich ein "erfolgreichen Anmeldung bei" die folgende (abhängig von dem Tool, das Sie verwenden):

| IDEs/Editoren | Ihr Benutzerprofil gelöscht werden 30 Tage nach Ihrer letzten... |
|-|-|
| Visual Studio | Starten Sie eine neue Instanz der IDE. Damit einmaliges Anmelden unterstützt wird, aktualisiert Visual Studio Live Share Ihr authentifizierungssitzung jedes Mal, wenn Sie eine neue Instanz von Visual Studio öffnen. |
| Visual Studio Code | Führen Sie den Workflow für die browserbasierte Authentifizierung (z. B. auf die `Sign In` Schaltfläche oder das Ausführen der `Live Share: Sign in with browser` Befehl). Visual Studio Live-Freigabe, speichert die authentifizierungssitzung auf dem Client, um zu verhindern, dass Sie zur Anmeldung jedes Mal, wenn Sie freigeben müssen. Allerdings wird dieser Sitzung läuft nach 30 Tagen und wird nie automatisch aktualisiert, bis Sie explizit anmelden über den Browser erneut. |

## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

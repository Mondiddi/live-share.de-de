---
title: Benutzerprofil-Visual Studio Live Share | Microsoft-Dokumentation
description: Eine Übersicht darüber, wie Sie Ihr Visual Studio Live Share Benutzerprofil anzeigen und entfernen.
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
ms.openlocfilehash: 2f9f496b47db7efe260c1f09a2906c68c07762d5
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295939"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Benutzerprofil

Wenn Sie sich bei Visual Studio Live Share authentifizieren, wird ein Benutzerprofil erstellt, mit dem die Teilnehmer, mit denen Sie zusammenarbeiten, einfach erkennen können, wer Sie sind (z. b. Ihre e-Mail-Adresse, Avatar). Zu einem beliebigen Zeitpunkt können Sie die Profilinformationen anzeigen, die Live share in Ihrem Auftrag gespeichert haben, indem Sie zu einer der folgenden Seiten navigieren (abhängig vom verwendeten Identitäts Anbieter):

- [Microsoft-Konto/-Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

Auf dieser Seite werden Sie aufgefordert, sich anzumelden (um Ihre Identität zu überprüfen), und dann wird die unformatierte JSON-Ausgabe für Ihr Benutzerprofil angezeigt.

<img width="500px" src="media/user-profile.png" />

Wenn Visual Studio Live Share derzeit nicht über ein Profil für die Identität verfügt, mit der Sie sich angemeldet haben, werden Sie darüber informiert.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Das Profil wird entfernt.

Wenn Sie Ihr Benutzerprofil entfernen möchten, können Sie auf der [Seite "Benutzerprofil](#user-profile)" auf die Schaltfläche "`Delete your account`" klicken. Andernfalls löschen Visual Studio Live Share das Profil 30 Tage nach der letzten erfolgreichen Anmeldung automatisch. In diesem Kontext bezieht sich ein "erfolgreiches anmelden" auf Folgendes (abhängig vom verwendeten Tool):

| IDE/Editor | Ihr Benutzerprofil wird 30 Tage nach dem letzten Mal gelöscht... |
|-|-|
| Visual Studio | Starten Sie eine neue Instanz der IDE. Um Single Sign-on zu unterstützen, aktualisiert Visual Studio Live Share Ihre Authentifizierungs Sitzung jedes Mal, wenn Sie eine neue Instanz von Visual Studio öffnen. |
| Visual Studio Code | Vervollständigen Sie den browserbasierten Authentifizierungs Workflow (z. b. durch Klicken auf die Schaltfläche "`Sign In`" oder durch Ausführen des `Live Share: Sign in with browser` Befehls). Visual Studio Live Share merken sich Ihre Authentifizierungs Sitzung auf dem Client, um zu verhindern, dass Sie sich bei jeder Freigabe von anmelden müssen. Diese Sitzung läuft jedoch nach 30 Tagen ab und wird nie automatisch aktualisiert, bis Sie sich explizit über den Browser anmelden. |

## <a name="see-also"></a>Weitere Informationen

- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

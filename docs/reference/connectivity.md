---
title: Konnektivität – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Informationen zu den Modi für Konnektivität und die Verbindung von für Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c685df798fc10b449c3e73db678e3b5d34e73ef0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640080"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Anforderungen an die Konnektivität für Live Share

Dieser Artikel beschreibt die Anforderungen an die Konnektivität für Visual Studio Live Share verfügbaren Verbindungsoptionen und bekannten Lösungen bei Verwendung von anwendbar.

## <a name="sign-in"></a>Anmelden

Können Sie sich in der Live-Freigabe, die mit einer [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) unterstützt Geschäfts-, Schul- oder unikonto ein [Microsoft-Konto](https://account.microsoft.com/account), oder ein [GitHub-Profil](https://github.com/). In der Regel Anmeldung URLs für diese sind in den meisten Organisationen, die angesichts der Anzahl von öffentlichen mit Internetzugriff Produkte, die, außer wenn nicht der Fall, öffnen Sie vom Netzwerkadministrator zum Öffnen `login.microsoftonline.com` und/oder `github.com` zusätzlich zu den Domänen [unten aufgeführten](#requirements-for-connection-modes).

> [!NOTE]
> Für lokale Active Directory (AD FS) und einem lokalen GitHub Enterprise-Konten werden derzeit nicht unterstützt [(abstimmen 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Verbindungsmodi

Um sicherzustellen, dass eine optimale erkannt Leistung zu erzielen, standardmäßig Visual Studio Live Share automatisch, ob eine Zusammenarbeit Sitzung-Hostcomputer und Gastcomputer können direkt über ein Netzwerk kommunizieren und nur über die Cloud überträgt, wenn keine Route zwischen ihnen vorhanden ist. Dieser Modus gemischten "Auto" ist flexibel und kann auch einige Gäste Relay über die Cloud, während andere direkt für die gleiche Sitzung eine Verbindung herstellen.

Die direkte Verbindungen erfolgt über einen cloudbasierten-Mechanismus, um die Sicherheit zu gewährleisten, jedoch erforderlich, ein Port zwischen 5990 und 5999 geöffnet werden, um die Konnektivität zu aktivieren. Daher bei der Freigabe zum ersten Mal Ihre desktop-Firewalls auffordern können Sie einen Port öffnen. Annahme, dass dies optional, da diese ignorieren sie bewirkt einfach Live Share immer das Relay im Auto-Modus verwenden.

Alle Verbindungen in Visual Studio Live Share sind SSH oder SSL verschlüsselt und authentifiziert ein zentraler Dienst, um sicherzustellen, dass nur die in der zusammenarbeitssitzung den Inhalt zugreifen können. Darüber hinaus Live Share Cloud Relay weitergeleitet, damit Datenverkehr nicht beibehalten und nicht "snoop" den Datenverkehr in keiner Weise.

## <a name="changing-the-connection-mode"></a>Ändern den Verbindungsmodus

Wenn Sie lieber direkte oder Relay-Verbindungen zu deaktivieren oder werden einfach Behandeln von Konnektivitätsproblemen, können Sie andere Verbindungsmodi erzwingen.

| Modus | Hostverhalten | Gast-Verhalten |
|------|----------------|----------------------|
| Auto | Zusammenarbeitssitzung des Hosts werden direkte Verbindungen von geschützten, authentifizierten oder cloudbasierte relaykommunikation Verbindungen akzeptiert. | Versucht, eine direkte Verbindung zu verwenden, und greift zurück, über die Cloud übertragen werden, wenn dies nicht möglich ist. |
| Direkt | Zusammenarbeitssitzung des Hosts akzeptiert nur authentifizierte, sichere direkte Verbindungen. | Versucht, eine direkte Verbindung zu verwenden, und wird beendet, wenn sie keine Verbindung herstellen kann. |
| Relay | Zusammenarbeitssitzung des Hosts lässt keine direkten Verbindungen zu. Klicken Sie auf dem Computer des Hosts wird kein Port geöffnet. | Immer eine Verbindung über die Cloud. |

So ändern Sie den Modus:

**VS:**

1. Wechseln Sie zu Extras > Optionen > Live Share.
2. Wählen Sie den Modus, in der Dropdownliste "Verbindungsmodus".
3. Starten Sie Visual Studio neu.

**Visual Studio Code:**

1. Bearbeiten Sie "Settings.JSON" (Datei > Voreinstellungen > Einstellungen).
2. Legen Sie `"liveshare.connectionMode"` zu `"auto"`, `"direct"`, oder `"relay"` je nach Bedarf.
3. Starten Sie Visual Studio Code neu.

## <a name="requirements-for-connection-modes"></a>Anforderungen für die Verbindungsmodi

Der Verbindungsmodus ab bestimmen, die bestimmte Ports und URLs, die für Live Share-Funktion verfügbar sein müssen.

| Modus | Client-Zugriff als Voraussetzung | Problembehandlung |
|------|--------------|-----------------|
| Beliebig | Ausgehender Zugriff auf `*.liveshare.vsengsaas.visualstudio.com:443` | Stellen Sie sicher Ihre Unternehmens oder persönlichen Netzwerkfirewall können Sie mit dieser Domäne zu verbinden. Geben Sie https://insiders.liveshare.vsengsaas.visualstudio.com in einem Browser und stellen Sie sicher, gelangen Sie auf der Visual Studio Live Share-Homepage. Sie können auch in ausgeführt werden [Proxyprobleme](#proxies) , die aufgelöst werden müssen.|
| (VS Code) | Ausgehender Zugriff auf `download.microsoft.com:443` | Stellen Sie sicher Ihre Unternehmens oder persönlichen Netzwerkfirewall können Sie mit dieser Domäne zu verbinden. Sie können auch in ausgeführt werden [Proxyprobleme](#proxies) , die aufgelöst werden müssen. |
| Auto | Auto-Switches. Finden Sie direkte und Relay-Modi. | Wechseln Sie zum direkten oder relay-Modus zur Problembehandlung. |
| Direkt | Hosts: Ein Port in der Bereich 5990-5999 muss geöffnet werden, um eingehende LAN-Verbindungen zu akzeptieren.<br /><br />Gäste: Ein Netzwerk und die ausgehenden Zugriff auf den Host auf diese gleichen Port. | Überprüfen Sie "Vsls-Agent" nicht von Ihrer desktop-Firewall-Software für diesen Portbereich blockiert wird, und Sie gegenseitig pingen können. Während Windows und anderer Desktopsoftware beim ersten aufgefordert, sollte der Agent wird gestartet, wir haben gesehen, Instanzen, in dem Gruppenrichtlinien zu verhindern, dass dies geschieht, und Sie müssen [fügen Sie den Eintrag manuell](#manually-adding-a-firewall-entry). Sie können auch in ausgeführt werden [Proxyprobleme](#proxies) , die aufgelöst werden müssen. |
| Relay | Ausgehender Zugriff auf `*.servicebus.windows.net:443`. | Stellen Sie sicher Ihre Unternehmens oder persönlichen Netzwerkfirewall können Sie mit dieser Domäne zu verbinden. Sie können auch in ausgeführt werden [Proxyprobleme](#proxies) , die aufgelöst werden müssen.|

## <a name="manually-adding-a-firewall-entry"></a>Einen Firewall-Eintrag hinzufügen manuell.

Wie oben beschrieben, direkten Modus erfordert, dass Ihre persönliche Firewall zulassen **Vsls-Agent** , akzeptieren Verbindungen im Port liegen 5990-5999. Wenn Sie möchten die direkten Modus verwenden, aber haben festgestellt, dass Ihre Firewall kein Vsls-Agent-Eintrag vorhanden ist, können Sie sie manuell hinzufügen. Die Vorgehensweise von Firewall-Software variieren, doch finden Sie Informationen über  **[Konfigurieren der Windows-Firewall](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Wenn Sie einen Eintrag für Vsls-Agent nicht angezeigt werden, finden den Agent ausführbare Sie in einem der folgenden Speicherorte.

### <a name="vs-code-agent-location"></a>Speicherort des VS Code-Agents

Ersatz **VERSION** für die Versionsnummer der Erweiterung in einer der folgenden Pfade:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Speicherort der Visual Studio-Agents

Der Speicherort von Visual Studio ist dynamischer, aber Sie können diese Schritte zum Suchen der ausführbaren Datei:

1. Navigieren Sie zu das Visual Studio-Installationsverzeichnis. Dies ist normalerweise `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` , in denen **EDITION** ist Community, Enterprise usw.

2. Eine Suche nach `vsls-agent.exe` in unter dem **IDE\Extensions** Unterordner.

Leider müssen Sie diesen Schritt nicht ausführen **jedes Mal aktualisieren Sie Visual Studio Live Share.**

## <a name="proxies"></a>Proxys

Visual Studio Live Share weist derzeit einige Einschränkungen für den Proxy verwenden. Während die automatische Proxy-Einstellungen für Windows, MacOS oder Linux-Verwendung (und mit bestimmten Proxykonfigurationen auf Windows) funktioniert die **"http_proxy"** und **HTTPS_PROXY** Umgebungsvariablen müssen nastavit *Global*.

Wenn Ihr Proxy automatisch für Sie nicht festlegt, können Sie die Variablen manuell in der folgenden Form festlegen:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Wenn Sie einen Authentifizierungsproxy und/oder verfügen, können Sie Ihre Benutzer und Kennwort wie folgt hinzufügen:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Wenn diese Einstellungen, die Sie über eine Lösung des Problems nicht [informieren Sie uns](https://github.com/MicrosoftDocs/live-share/issues/86) die Einzelheiten der Proxy einrichten, damit wir einen Blick auf die Verbesserung des Supports entfernen können.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
- [Sicherheitsfeatures von Live Share](security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

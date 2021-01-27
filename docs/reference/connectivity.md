---
title: Konnektivität | Microsoft-Dokumentation
description: Informationen zu Konnektivität und Verbindungs Modi für Visual Studio Live share.
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
ms.openlocfilehash: e1a2567b18e7dbd30d86e49a22950d300fb0a95b
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870525"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Anforderungen an die Konnektivität für Live Share

In diesem Artikel werden die Konnektivitätsanforderungen für Visual Studio Live Share, verfügbare Konnektivitätsoptionen und ggf. bekannte Problem Umgehungen zusammengefasst.

## <a name="sign-in"></a>Anmelden

Sie können sich mit einem beliebigen [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) gesicherten Geschäfts-, Schul-oder unikonto, einem [Microsoft-Konto](https://account.microsoft.com/account)oder einem [GitHub-Profil](https://github.com/)bei Live Share anmelden. In den meisten Organisationen sind in der Regel Anmelde-URLs geöffnet, die über die Anzahl der öffentlichen Produkte verfügen, von denen Sie verwendet werden. Falls nicht, wenden Sie sich an den Netzwerkadministrator, um `login.microsoftonline.com` `github.com` die [unten aufgeführten](#requirements-for-connection-modes)Domänen zu öffnen und/oder zusätzlich zu diesen zu öffnen.

> [!NOTE]
> AD FS-Konten (lokales AD) und lokale GitHub Enterprise-Konten werden zurzeit nicht unterstützt [(up-Voting 👍 )](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Verbindungs Modi

Um eine optimale Leistung zu gewährleisten, erkennt standardmäßig Visual Studio Live Share automatisch, ob ein Zusammenarbeits Sitzung-Host Computer und Gastcomputer direkt über ein Netzwerk und nur Relays über die Cloud kommunizieren können, wenn keine Verbindung besteht. Dieser gemischte "Auto"-Modus ist flexibel und ermöglicht es einigen Gästen sogar, über die Cloud zu übertragen, während andere direkt für dieselbe Sitzung eine Verbindung herstellen.

Die direkten Verbindungen werden über einen cloudbasierten Mechanismus authentifiziert, um die Sicherheit sicherzustellen, aber es ist erforderlich, dass ein Port zwischen 5990 und 5999 geöffnet wird, um die Konnektivität zu ermöglichen. Dies hat zur Folge, dass Sie bei der erstmaligen Freigabe von der Desktop Firewall aufgefordert werden, einen Port zu öffnen. Das akzeptieren ist optional, da das ignorieren lediglich dazu führt, dass Live Share immer das Relay verwendet, wenn es sich im Auto-Modus befindet.

Alle Verbindungen in Visual Studio Live Share werden per SSH oder SSL verschlüsselt und für einen zentralen Dienst authentifiziert, um sicherzustellen, dass nur die in der Zusammenarbeits Sitzung Zugriff auf den Inhalt erhalten. Außerdem speichert das cloudrelay von Live Share keinen Datenverkehr, der durch ihn weitergeleitet wird, und führt den Datenverkehr nicht in irgendeiner Weise aus.

## <a name="changing-the-connection-mode"></a>Ändern des Verbindungs Modus

Wenn Sie vorziehen, direkte oder relaor-Verbindungen zu deaktivieren oder einfach Verbindungsprobleme zu beheben, können Sie andere Verbindungs Modi erzwingen.

| Mode | Host Verhalten | Gast Verhalten |
|------|----------------|----------------------|
| Automatisch | Die Zusammenarbeits Sitzung des Hosts nimmt sichere, authentifizierte direkte Verbindungen oder cloudrelawayverbindungen an. | Versucht, eine direkte Verbindung zu verwenden, und greift auf die Cloud zurück, wenn dies fehlschlägt. |
| Direkt | Die Zusammenarbeits Sitzung des Hosts akzeptiert nur authentifizierte, sichere direkte Verbindungen. | Versucht, eine direkte Verbindung zu verwenden, und wird beendet, wenn keine Verbindung hergestellt werden kann. |
| Relay | Die Zusammenarbeits Sitzung des Hosts lässt keine direkten Verbindungen zu. Auf dem Computer des Hosts wird kein Port geöffnet. | Stellt immer eine Verbindung über die Cloud her. |

So ändern Sie den Modus

**Jews**

1. Wechseln Sie zu Extras > Optionen > Live share.
2. Wählen Sie den Modus aus der Dropdown Liste "Verbindungs Modus" aus.
3. Neu starten im Vergleich zu

**VS Code:**

1. Bearbeiten Sie settings.jsfür (Datei > Einstellungen > Einstellungen).
2. Legen `"liveshare.connectionMode"` Sie `"auto"` `"direct"` `"relay"` abhängig von Ihrer Präferenz auf, oder fest.
3. Starten Sie vs Code neu.

## <a name="requirements-for-connection-modes"></a>Anforderungen für Verbindungs Modi

Der Verbindungs Modus, in dem Sie sich befinden, bestimmt die spezifischen Ports und URLs, die für die Funktion Live Share verfügbar sein müssen.

| Mode | Client Zugriffs Anforderung | Problembehandlung |
|------|--------------|-----------------|
| Any | Ausgehender Zugriff auf `*.liveshare.vsengsaas.visualstudio.com:443` | Stellen Sie sicher, dass Ihre unternehmenseigene oder persönliche Netzwerk Firewall Ihnen ermöglicht, eine Verbindung mit dieser Domäne herzustellen. Geben https://insiders.liveshare.vsengsaas.visualstudio.com Sie in einem Browser ein, und überprüfen Sie, ob Sie auf der Startseite Visual Studio Live share. Möglicherweise treten auch [Proxy Probleme](#proxies) auf, die aufgelöst werden müssen.|
| Any (vs Code) | Ausgehender Zugriff auf `download.microsoft.com:443` | Stellen Sie sicher, dass Ihre unternehmenseigene oder persönliche Netzwerk Firewall Ihnen ermöglicht, eine Verbindung mit dieser Domäne herzustellen. Möglicherweise treten auch [Proxy Probleme](#proxies) auf, die aufgelöst werden müssen. |
| Automatisch | Automatische Switches. Weitere Informationen finden Sie unter den Modi Direct und Relay | Wechseln Sie zur Problembehandlung in den Direct-oder Relay-Modus. |
| Direkt | Hosts: ein Port im Bereich 5990 bis 5999 muss geöffnet werden, um eingehende lokale Netzwerkverbindungen zu akzeptieren.<br /><br />Gäste: eine Netzwerk Route und ein ausgehender Zugriff auf den Host auf demselben Port. | Vergewissern Sie sich, dass "vsls-Agent" nicht durch Ihre Desktop-Firewallsoftware für diesen Port Bereich blockiert wird und Sie einen Ping gegen einen anderen durchsetzen können. Während Windows und andere Desktop Software Sie beim ersten Start des Agents auffordern sollten, haben wir Instanzen gesehen, die dies verhindern, und Sie müssen [den Eintrag manuell hinzufügen](#manually-adding-a-firewall-entry). Möglicherweise treten auch [Proxy Probleme](#proxies) auf, die aufgelöst werden müssen. |
| Relay | Ausgehender Zugriff auf `*.servicebus.windows.net:443` . | Stellen Sie sicher, dass Ihre unternehmenseigene oder persönliche Netzwerk Firewall Ihnen ermöglicht, eine Verbindung mit dieser Domäne herzustellen. Möglicherweise treten auch [Proxy Probleme](#proxies) auf, die aufgelöst werden müssen.|

## <a name="manually-adding-a-firewall-entry"></a>Manuelles Hinzufügen von firewalleinträgen

Wie oben beschrieben, erfordert die persönliche Firewall, dass die persönliche Firewall den **vsls-Agent** erlaubt, Verbindungen im Port Bereich 5990-5999 zu akzeptieren. Wenn Sie den direkten Modus verwenden möchten, aber festgestellt haben, dass die Firewall nicht über einen vsls-Agent-Eintrag verfügt, können Sie ihn manuell hinzufügen. Wie Sie dies tun, hängt von der Firewallsoftware ab, aber hier finden Sie Informationen zum **[Konfigurieren der Windows-Firewall](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Wenn kein Eintrag für vsls-Agent angezeigt wird, finden Sie die ausführbare Agent-Datei an einem der folgenden Speicherorte.

### <a name="vs-code-agent-location"></a>Speicherort des vs Code Agents

Ersetzen Sie die **Versions** Nummer der Erweiterung in einem der folgenden Pfade:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Speicherort von Visual Studio-Agent

Der Visual Studio-Speicherort ist dynamischer, aber Sie können die folgenden Schritte ausführen, um die ausführbare Datei zu finden:

1. Navigieren Sie zu Ihrem Visual Studio-Installationsort. In der Regel `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` ist die **Edition** "Community", "Enterprise" usw.

2. Führen Sie eine Suche nach `vsls-agent.exe` in unter dem Unterordner **ide\extensions** aus.

Leider müssen Sie diesen Schritt möglicherweise **jedes Mal ausführen, wenn Sie Visual Studio Live Share aktualisieren.**

## <a name="proxies"></a>Proxys

Visual Studio Live Share weist derzeit einige Einschränkungen bezüglich der Proxy Verwendung auf. Während die automatischen Proxy Einstellungen unter Windows verwendet werden sollen, müssen bei Verwendung von macOS oder Linux (und mit bestimmten Proxy Konfigurationen unter Windows) die Umgebungsvariablen **HTTP_PROXY** und **HTTPS_PROXY** *Global* festgelegt werden.

Wenn Ihr Proxy diese nicht automatisch für Sie festgelegt hat, können Sie die Variablen manuell in der folgenden Form festlegen:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Wenn Sie über einen authentifizier enden Proxy verfügen, können Sie den Benutzer und das Kennwort wie folgt hinzufügen:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Wenn diese Einstellungen das Problem nicht lösen, informieren Sie [uns](https://github.com/MicrosoftDocs/live-share/issues/86) über die Besonderheiten ihres proxysetups, damit wir uns mit der Verbesserung des Supports beschäftigen können.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
- [Sicherheitsfeatures von Live Share](security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

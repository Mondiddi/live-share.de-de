---
title: Problembehandlung – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Zur Problembehandlung, Tipps und Tricks für Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8d20ec73d9cadfefced65c04b1ef18f6e844167d
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255877"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Problembehandlung bei Visual Studio-Livefreigabe

Dieser Artikel behandelt die Problembehandlung Tipps, problemumgehungen und Antworten auf häufige Probleme und Fragen. Sie sollten auch einen Blick auf die [– häufig gestellte Fragen](faq.md).

## <a name="installation--tool-requirements"></a>Installation / Anforderungen-tool

Die folgenden Tipps, die im Zusammenhang mit der Installation von Visual Studio Live Share eine Problembehandlung durchführen.

| Tool | Problem | Lösung / Problemumgehung |
|------|---------|------------|
| VS | Das Erweiterungsinstallationsprogramm <strong>eine Version von Visual Studio wurde nicht gefunden</strong> mit, dass beim Installieren der Visual Studio Live Share-Erweiterung. | Erfordert Visual Studio Live Share **Visual Studio 2017 Version 15.6** oder höher für Hosts und Gästen. Installieren Sie die neueste stabile [Update von Visual Studio 2017](https://visualstudio.com/vs/) , und wiederholen Sie.|
| VS Code | Beim Versuch, Visual Studio Live Share unter MacOS mit Visual Studio Code zu verwenden, wird ein Fehler angezeigt <strong>El Capitan oder niedriger</strong>. | Visual Studio Live Share Unterstützung des Betriebssystems kann, hängt von .NET Core die derzeit [unterstützt nur MacOS Sierra oder höher.]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | Ein "**Abhängigkeiten konnten nicht installiert werden**" Fehler wird angezeigt, die While-Erweiterung ist **Fertigstellen der Installation** auf dem ersten Start oder Fehler zu erhalten **fehlt oder ist bereits vorhanden Dateien**. | Überprüfen Sie, ob Sie auf eine **gute Netzwerkverbindung**. Wenn Sie sind, können Sie in ausgeführt werden eine **Proxy oder Ihrer Firewall** Problem. Finden Sie unter [Behandlung von Konnektivitätsproblemen](#connectivity). <br /><br />|
| VS Code | Installation der Visual Studio Live Share-Erweiterung aus dem Marketplace <strong>wird in der Stable/Insider-Version von Visual Studio Code installiert</strong> anstelle der Version, ich möchte. | Starten Sie VS Code stabil oder Insider je nach Bedarf, klicken Sie auf der Registerkarte "Erweiterungen", suchen Sie nach "Visual Studio Live Share" ein, und von dort aus zu installieren. |
| Visual Studio Code (**Linux**) | Die Live Share-Erweiterung wird nicht aktiviert und **keine Status Menüelemente** nach der Installation der Erweiterungs auf **Linux**. | Visual Studio Live Share hängt von .NET Core 2.0, mit dem eine Anzahl von Linux-Voraussetzungen, die standardmäßig in bestimmten Distributionen von Linux nicht erfüllt werden kann. Finden Sie unter [hier, um Informationen](reference/linux.md#install-linux-prerequisites) auf was installiert werden soll. |

## <a name="sign-in"></a>Anmelden

Die folgenden Tipps für die Anmeldung bei Problemen eine Problembehandlung durchführen.

| Tool | Problem | Lösung / Problemumgehung |
|------|---------|------------|
| VS | Sie müssen zum Anmelden bei Visual Studio Live Share mit einer <strong>andere Identität</strong> als Sie zum Anmelden bei Visual Studio verwenden. | Wechseln Sie zu Extras > Optionen > Live Share > Benutzerkontos ein, wählen Sie ein alternatives Konto. |
| VS Code | Während Sie im Fenster angezeigten einen Browser während der Anmeldung und den Prozess <strong>angezeigt wird, auf der Webseite erfolgreich</strong>, der Statusleiste <strong>weiterhin angezeigt wird, "Anmelden"</strong> nach Schließen des Browsers. | Klicken Sie nach der Anmeldung auf "Probleme"? ein, und befolgen Sie die Anweisungen, um einen temporären Benutzers-Code in das Tool eingeben.<br /><br />Wir freuen uns auch angezeigt, was möglicherweise auftreten, so Sie [Fehler protokollieren](https://aka.ms/vsls-problem). |
| Alle | Sie werden immer eine <strong>Timeout-oder Verbindungsfehlers</strong>. | Finden Sie unter [Behandlung von Konnektivitätsproblemen](#connectivity). |
| Alle | Wenn die Anmeldung mit einem Microsoft gesichert **Geschäfts-, Schul- oder UNI-e-Mail-Adresse** daraufhin wird eine Meldung angezeigt, **"Administratorgenehmigung"**. | Ihre Azure AD-Grundsatzes ist dafür eingerichtet, die "administratorzustimmung" für neue Anwendungen, die Zugriff auf den Inhalt des Verzeichnisses erforderlich ist. Finden Sie unter [hier](reference/security.md) Weitere Details. |
| Visual Studio Code (**MacOS**) | Wenn Sie Anmeldung finden Sie eine Fehlermeldung erhalten **SecKeychainAddGenericPassword() Fehler**. | Dies ist fast immer aufgrund eines allgemeinen Problems mit MacOS, in denen kennwortänderungen in der Keychain Anmeldung nicht widergespiegelt. Versuchen Sie es jetzt in "Keychain-Zugriff", Anmeldung Schlüsselbund sperren und entsperren es noch mal. Dies ist möglicherweise ausreichend, um das Problem zu beheben, aber wenn Sie keine Verbindung mit Ihrem Kennwort entsperren können, versuchen Sie es Ihrer vorherigen Beispiel. Wenn dies funktioniert, ändern Sie das Anmeldekennwort für den Schlüsselbund in Ihr aktuelles Kennwort ein. Finden Sie unter [hier](https://support.apple.com/en-us/HT201609) Details. |
| Visual Studio Code (**Linux**) | Wenn im Benutzercode eingeben, nach der Anmeldung über den Browser sehen Sie die Fehlermeldung **secret_password_store_sync() Fehlercode XX**. | Grund hierfür ist in der Regel `gnome-keyring` und/oder `libsecret-1-0` /  `libsecret` nicht installiert. Sie können überprüfen, Gnome-Schlüsselbund ist ordnungsgemäß konfiguriert, durch die Installation von `seahorse` und anschließend die Anwendung "Kennwörter und Schlüssel" in Ihrer desktopumgebung. Erfahren Sie mehr über [Linux-Voraussetzungen hier](reference/linux.md#install-linux-prerequisites). |
| Visual Studio Code (**Linux**) | Sie sind <strong>aufgefordert, einen Benutzercode einzugeben</strong> mit Live Share v0.3.295 oder einer früheren Version, jedoch kein Browser angezeigt wird, damit Sie einen erhalten können. | Wir arbeiten, um die Code-Anforderung unter Linux zu entfernen. In der Zwischenzeit sollte ein Browserfenster für die Verwendung für die Anmeldung angezeigt werden. Wenn dies nicht der Fall ist, kann das Browserfenster VS Code verborgen. Finden Sie im nächsten Tipp aus, wenn dies nicht der Fall ist.  |
| VS Code | Nach dem Klicken auf "Anmelden" (oder mithilfe der "Live-Freigabe: Melden Sie sich an"-Befehl), <strong>kein Browserfenster angezeigt wird, damit Sie Ihre Anmeldeinformationen eingeben können</strong>. | 1. [Melden Sie sich hier](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. Klicken Sie nach der Anmeldung auf "Probleme"?<br /> 3. Führen Sie die Anweisungen aus, um einen temporären Benutzers-Code in das Tool eingeben. |
| Alle | Sie möchten <strong>Join</strong> eine zusammenarbeitssitzung</strong> aber <strong>nicht / nicht-e-Mail-Updates erhalten möchten</strong>. | Anmelden bei der Live Share-Erweiterungs in Visual Studio/Visual Studio Code ist <strong>nicht</strong> vorschaubuilds, dass Sie Updates per e-Mail empfangen.<br /><br />Livefreigabe erfordert Gäste für die Anmeldung als Sicherheitsmaßnahme, damit der Host Einblicke in die Identität dieser verfügt, die hinzugefügt wurden. [Stimmen Sie dieser Funktion bis](https://github.com/MicrosoftDocs/live-share/issues/3) bei Bedarf die Option zum Zulassen des anonymer Benutzern den Beitritt zu (z. B. ein Benutzer ohne Namen / ein benutzerdefinierter Name). |

## <a name="share-and-join"></a>Teilen und verknüpfen

Die folgenden Tipps für die Anmeldung bei Problemen eine Problembehandlung durchführen.

| Tool | Problem | Lösung / Problemumgehung |
|------|----------------|------------|
| Alle | <strong>Freigeben/Zusammenführung:</strong> Sie erhalten ein Timeout oder Fehler nicht, eine Verbindung herstellen können. | Finden Sie unter [Behandlung von Konnektivitätsproblemen](#connectivity). |
| VS Code | <strong>Join:</strong> Sie wurden <strong>keine Aufforderung zur Eingabe / Starten von Visual Studio Code</strong> nach dem Öffnen der Seite "Verknüpfung" in einem Browser. |  Tipps: <ul><li>Achten Sie darauf haben Sie <i>VS Code mindestens einmal gestartet und die Installation in der Statusleiste der Abschluss gewartet.</i></li><li>Wenn dies nicht funktioniert, führen Sie die "Live-Freigabe: Setup für Startfeld"-Befehl.</li><li>**Linux-Benutzer**: Wenn Sie aufgefordert, Ihr Administratorkennwort ("sudo") geben beim Ausführen des obigen Befehls, ist dies erwünscht.</li><li>Schließlich finden Sie unter [manuell verknüpfen](reference/manual-join.md) dieses Problem zu umgehen.</li></ul> Wenn dieses Problem auftritt, wir würden uns freuen, Woran könnte das sein, also bitte [Fehler protokollieren](https://aka.ms/vsls-new-issue). |
| VS | <strong>Join:</strong> Sie wurden <strong>keine Aufforderung zur Eingabe / starten Sie Visual Studio möglich</strong>  nach dem Öffnen der Seite "Verknüpfung" in einem Browser. |  Finden Sie unter [Manuelles Verknüpfen von](reference/manual-join.md).<br /><br /> Wir freuen uns auch, Ihre Protokolle so sehen Sie [Fehler protokollieren](https://aka.ms/vsls-problem) mithilfe von Visual Studio "Bericht ein Problem..." -Funktion. |
| Alle | <strong>Join:</strong> Lieber <strong>fügen Sie der Join-Verknüpfung direkt in Visual Studio / Visual Studio Code</strong> anstatt auf den Weblink. | Finden Sie unter [Manuelles Verknüpfen von](reference/manual-join.md). |
| Alle | <strong>Join:</strong> Sie sehen eine Meldung angezeigt wird, "**der Besitzer des Arbeitsbereichs offline zu sein scheint**," bei der Verknüpfung mit dem Browser. | Mögliche problemumgehungen:<br /><ul><li>Versuchen Sie es [manuell verknüpfen](reference/manual-join.md). Wir haben gesehen, dass Probleme mit regionsübergreifenden (z. B. Osten und Westen USA) Joins aufgrund von Problemen, die nicht auf manuelle Joins auswirken.</li><li>Live-Freigabe kann kann nicht direkt an den Host weitergeleitet werden soll, bei der Ausführung im Modus für die Verbindung von "Auto" sein. Versuchen Sie es [Relay Modus](reference/connectivity.md).</li></ul>Finden Sie unter [Behandlung von Konnektivitätsproblemen](#connectivity) weitere Möglichkeiten |
| VS Code | <strong>Join:</strong> Sie verknüpft, über den Browser <strong>vor der Anmeldung</strong>, wurden nicht zur Anmeldung aufgefordert</strong>, und die Verknüpfung nicht abgeschlossen wurde. |  Dies ist eine [bekannter Fehler](https://github.com/MicrosoftDocs/live-share/issues/167). Klicken Sie auf der Anmeldeseite Statuselement für die Anmeldung, und klicken Sie dann erneut beitreten. |

## <a name="connectivity"></a>Konnektivität

Die folgenden Informationen können Sie die Problembehandlung, wenn Sie Probleme im Zusammenhang mit Konnektivität oder Timeouts beim Anmelden bei, freigeben oder verknüpft haben.

Wie in der [Konnektivitätsanforderungen Live Share](reference/connectivity.md) Artikel verschiedene Verbindungsmodi haben unterschiedliche Anforderungen an, funktionieren daher gibt es einige andere Probleme auf.

| Tool | Problem | Mögliche Ursache |
|------|------|----------------|
| Alle | Sie verwenden eine <strong>Proxy</strong> und eine Reihe von Verbindungsproblemen werden angezeigt. | Proxy-Einstellungen können schwierig sein.  Versuchen Sie die **"http_proxy"** und **HTTPS_PROXY** Umgebungsvariablen **Global** und starten Sie das Tool anschließend neu. Finden Sie unter [Proxyeinstellungen](reference/connectivity.md#proxies) Weitere Details. Es gibt wahrscheinlich einige Konfigurationen, die wir noch nicht unterstützen, damit [Teilen Sie uns](https://github.com/MicrosoftDocs/live-share/issues/86) Wenn dies nicht für Sie funktioniert. |
| VS Code | Nach der Installation der Erweiterung und Visual Studio Code zum ersten Mal gestartet wird, die Sie erhalten eine <strong>einen Fehler, wenn "Abschließen der Installation" wird, in der Statusleiste angezeigt</strong>. |  Sie können nicht auf das Internet oder Zugriff auf download.visualstudio.microsoft.com zugreifen bzw. download.microsoft.com an Port 443 wird durch Ihre Firewall oder blockiert. Finden Sie unter [hier](https://github.com/MicrosoftDocs/live-share/issues/58) Informationen darüber, warum Live Share etwas zu diesem Zeitpunkt herunterladen soll. |
| Alle | Sie sind <strong>kann nicht zum Anmelden bei Visual Studio Live Share</strong> | Sie können nicht auf das Internet zugreifen oder Zugriff auf *. liveshare.vsengsaas.visualstudio.com auf Port 80/443 durch Ihre Firewall oder blockiert wird. Geben Sie https://insiders.liveshare.vsengsaas.visualstudio.com in einem Browser und stellen Sie sicher, gelangen Sie auf der Visual Studio Live Share-Homepage. |
| Alle | Sie befinden sich im <strong>Auto-Modus</strong> (Standardeinstellung), melden Sie sich, aber sehen, können eine <strong>Timeout-oder Verbindungsfehlers</strong> entweder freigeben oder verknüpfen. | Entweder sowohl direkte als auch relay-Modi konnte eine Verbindung herstellen, oder es ist ein Fehler im Auto-Modus. Wenn Sie nach dem verbinden können [wechseln, um direkte oder Relay-Modus](reference/connectivity.md#changing-the-connection-mode), [auslösen ein Fehlers](https://aka.ms/vsls-problem). |
| Alle | Sie befinden sich im <strong>Direktmodus</strong>, melden Sie sich, aber sehen, können eine <strong>Timeout-oder Verbindungsfehlers</strong> entweder freigeben oder verknüpfen. | Der Gast und Host können nicht direkt miteinander verbinden. Versuchen Sie es [Modus "automatisch" oder "Relay"](reference/connectivity.md#changing-the-connection-mode) um festzustellen, ob das Problem weiterhin besteht. Sie müssen möglicherweise [manuell über die persönliche Firewall zulassen Live Share](reference/connectivity.md#manually-adding-a-firewall-entry) oder verwenden Sie einfach die Relay-Modus. |
| Alle | Sie befinden sich im <strong>Relay Modus</strong>, angemeldet sind, aber benachrichtigt werden sollen eine <strong>Timeout-oder Verbindungsfehlers</strong> entweder freigeben oder verknüpfen. | Der Zugriff auf *. *.Servicebus.Windows.NET auf Port 80/443 blockiert wird, die von Ihrer persönlichen und Unternehmensdaten Firewall blockiert wird. Versuchen Sie es [Direktmodus](reference/connectivity.md#changing-the-connection-mode). |

Finden Sie unter den [Konnektivitätsanforderungen Live Share](reference/connectivity.md) Artikel Weitere Informationen zu Anforderungen an die Konnektivität.

## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Freigeben Ihres ersten Projekts](quickstart/share.md)
- [Beitreten zu Ihrer ersten Sitzung](quickstart/join.md)

Gewusst wie

- [Zusammenarbeiten mithilfe von Visual Studio Code](use/vscode.md)
- [Zusammenarbeiten mithilfe von Visual Studio](use/vs.md)

Referenz

- [Alle große Fehler, Features und Einschränkungen](https://aka.ms/vsls-issues)
- [Alle Anfragen zu Features und Einschränkungen](https://aka.ms/vsls-feature-requests)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Details zur Linux-Installation](reference/linux.md)
- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Unterstützung für Erweiterung](reference/extensions.md)

Immer noch Probleme? Sie können [Feedback geben](support.md).

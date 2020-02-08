---
title: 'Problembehandlung: Visual Studio Live Share | Microsoft-Dokumentation'
description: Tipps und Tricks zur Problembehandlung für Visual Studio Live share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5d18c8487bbc280c14c4d4c17e47af02dd89266e
ms.sourcegitcommit: 8579c04aa4c8ec5d32a4987cb2b95708affec318
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "77055528"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Problembehandlung Visual Studio Live Share

In diesem Artikel werden Tipps zur Problembehandlung, Problem Umgehungen und Antworten auf häufige Probleme und Fragen behandelt. Sie können sich auch die häufig gestellten Fragen [ansehen.](faq.md) 

## <a name="installation--tool-requirements"></a>Installations-/Tool-Anforderungen

Im folgenden finden Sie Tipps zur Problembehandlung bei der Installation von Visual Studio Live share.

| Tool | Problem | Lösung/Problem Umgehung |
|------|---------|------------|
|VS Code <strong>(macOS)</strong>| Es wird eine Warnung mit dem Hinweis angezeigt, dass Ihr <strong>macOS von .net Core nicht mehr unterstützt wird <strong>| Diese Warnung wird durch ein Aktuelles [Update von .net Core](https://docs.microsoft.com/en-us/dotnet/core/install/dependencies?tabs=netcore31&pivots=os-macos) angezeigt, das keine Versionen mehr unterstützt, die niedriger sind als <strong>High Sierra (10.13 +).</strong> Aktualisieren Sie Ihr Betriebssystem, um die Live Share Erweiterung zu aktivieren.
| VS | Das Erweiterungs Installationsprogramm <strong>kann keine Version von Visual Studio finden</strong> , die bei der Installation der Visual Studio Live Share Erweiterung verwendet werden soll. | Visual Studio Live Share ist für Hosts und Gäste **Visual Studio 2017 Version 15,6** oder höher erforderlich. Installieren Sie das neueste stabile [Update von Visual Studio 2017](https://visualstudio.com/vs/) , und wiederholen Sie den Vorgang. |
| VS Code | Der Fehler "**Abhängigkeiten konnten nicht installiert werden**" wird angezeigt, wenn die **Installation** beim ersten Start abgeschlossen ist, oder wenn Sie Fehler über **fehlende oder bereits vorhandene Dateien**erhalten. | Vergewissern Sie sich, dass Sie über eine **gute Netzwerkverbindung**verfügen. Wenn dies der Fall ist, können Sie einen **Proxy-oder** Firewallfehler ausführen. Siehe [Verbindungsproblem](#connectivity)Behandlung. <br /><br />|
| VS Code | Wenn Sie die Visual Studio Live Share Erweiterung aus dem Marketplace installieren, wird <strong>Sie in der stabilen/Insider-Version von vs Code</strong> anstelle der gewünschten Version installiert. | Starten Sie vs Code stable oder Insider abhängig von Ihrer Präferenz, klicken Sie auf die Registerkarte "Erweiterungen", suchen Sie nach "Visual Studio Live Share", und installieren Sie von dort aus. |
| VS Code (**Linux**) | Die Live Share Erweiterung wird nicht aktiviert, und nach der Installation der Erweiterung unter **Linux**werden **keine Status leisten Elemente angezeigt** . | Visual Studio Live Share ist von .net Core 2,0 abhängig, das über eine Reihe von Linux-Voraussetzungen verfügt, die für bestimmte Distributionen von Linux standardmäßig nicht erfüllt werden können. Weitere [Informationen](reference/linux.md#install-linux-prerequisites) zu den zu installierenden Informationen finden Sie hier. |

## <a name="sign-in"></a>Anmelden

Im folgenden finden Sie Tipps zur Problembehandlung bei Anmelde Problemen.

| Tool | Problem | Lösung/Problem Umgehung |
|------|---------|------------|
| VS | Sie müssen sich bei Visual Studio Live Share mit einer <strong>anderen Identität</strong> anmelden, als Sie sich bei Visual Studio anmelden. | Wechseln Sie zu Extras > Optionen > Live Share > Benutzerkonto, um ein alternatives Konto auszuwählen. |
| VS Code | Wenn während der Anmeldung ein Browserfenster angezeigt wird und der Vorgang <strong>auf der Webseite erfolgreich</strong>ist, wird in der Statusleiste nach dem Schließen des Browsers <strong>weiterhin "Anmelden"</strong> angezeigt. | Wenn Sie sich angemeldet haben, klicken Sie auf "Problem?". und befolgen Sie die Anweisungen, um einen temporären Benutzercode in das Tool einzugeben.<br /><br />Wir würden uns auch freuen, was passieren kann, wenn Sie [einen Fehler protokollieren](https://aka.ms/vsls-problem). |
| Alle | Sie erhalten einen <strong>Timeout-oder Verbindungsfehler</strong>. | Siehe [Verbindungsproblem](#connectivity)Behandlung. |
| Alle | Wenn Sie sich mit einer von Microsoft gesicherten Geschäfts **-, Schul-oder Uni-e-Mail-Adresse** anmelden, wird die Meldung **"Administrator Genehmigung erforderlich"** angezeigt. | Ihr Azure AD Grundsatz ist so eingerichtet, dass für neue Anwendungen, die auf den Inhalt des Verzeichnisses zugreifen, "Administrator Zustimmung" erforderlich ist. Weitere Informationen finden Sie [hier](reference/security.md) . |
| VS Code (**macOS**) | Wenn Sie sich anmelden, wird ein Fehler mit dem Hinweis angezeigt, dass die Fehlermeldung "Fehler bei" Fehler bei "Fehler bei der **Fehlermeldung"** | Dies liegt fast immer an einem häufigen Problem mit macOS, bei dem Kenn Wort Änderungen nicht in der Anmeldungs-Keychain widergespiegelt werden. Versuchen Sie, "Keychain-Zugriff" zu sperren, die Anmelde-Keychain zu sperren und dann erneut zu entsperren. Dies kann ausreichen, um das Problem zu beheben. Wenn Sie es jedoch nicht mit Ihrem aktuellen Kennwort entsperren können, versuchen Sie es mit dem vorherigen. Wenn dies funktioniert, ändern Sie das Kennwort für die Anmelde-keychain in Ihr aktuelles Kennwort. Ausführliche Informationen finden Sie [hier](https://support.apple.com/en-us/HT201609). |
| VS Code (**Linux**) | Wenn Sie den Benutzercode nach der Anmeldung über den Browser eingeben, wird eine Fehlermeldung mit dem Hinweis angezeigt, dass **secret_password_store_sync () mit Fehlercode XX fehlgeschlagen**ist. | Dies ist in der Regel darauf zurückzuführen, dass `gnome-keyring` und/oder `libsecret-1-0`/ nicht installiert `libsecret`. Sie können überprüfen, ob der gnome-keybund ordnungsgemäß konfiguriert ist, indem Sie `seahorse` installieren und anschließend die Anwendung "Kenn Wörter und Schlüssel" in ihrer Desktopumgebung verwenden. Weitere Informationen zu den [Voraussetzungen für Linux](reference/linux.md#install-linux-prerequisites)finden Sie hier. |
| VS Code (**Linux**) | Sie werden <strong>aufgefordert, einen Benutzercode</strong> mit Live Share v 0.3.295 oder unten einzugeben, aber es wird kein Browser angezeigt, in dem Sie einen Benutzercode erhalten können. | Wir arbeiten daran, die Benutzercode Anforderungen unter Linux auszuschließen. In der mittleren Zeit sollte ein Browserfenster angezeigt werden, mit dem Sie sich anmelden können. Andernfalls wird das Browserfenster unter vs Code möglicherweise ausgeblendet. Wenn dies nicht der Fall ist, sehen Sie den nächsten Tipp.  |
| VS Code | Nachdem Sie auf "Anmelden" geklickt haben (oder indem Sie den Befehl "Live Share: Anmelden" verwenden), wird <strong>kein Browserfenster angezeigt, in dem Sie Ihre Anmelde Informationen eingeben können</strong>. | 1. [melden Sie sich hier an](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) .<br />2. Klicken Sie nach der Anmeldung auf "Problem?".<br /> 3. Befolgen Sie die Anweisungen, um einen temporären Benutzercode in das Tool einzugeben. |
| Alle | Sie möchten einer Zusammenarbeits Sitzung <strong>beitreten</strong> ,</strong> aber <strong>keine e-Mail-Updates erhalten</strong>. | Wenn Sie sich bei der Live Share-Erweiterung in vs/vs Code anmelden, können Sie <strong>keine</strong> e-Mail-Updates erhalten.<br /><br />Live Share müssen sich Gäste als Sicherheitsmaßnahme anmelden, damit der Host eine Sichtbarkeit der Identität der verbundenen hat. [Wählen Sie diese Funktion](https://github.com/MicrosoftDocs/live-share/issues/3) aus, wenn Sie die Option gestatten möchten, anonymen Benutzern beizutreten (z. b. Benutzer ohne Namen/benutzerdefinierter Name). |

## <a name="share-and-join"></a>Freigeben und beitreten

Im folgenden finden Sie Tipps zur Problembehandlung bei Anmelde Problemen.

| Tool | Problem | Lösung/Problem Umgehung |
|------|----------------|------------|
| Alle | <strong>Freigabe/Join:</strong> Sie erhalten ein Timeout oder einen Fehler, wenn keine Verbindung hergestellt werden kann. | Siehe [Verbindungsproblem](#connectivity)Behandlung. |
| VS Code | <strong>Beitreten:</strong> Nachdem Sie die joinseite in einem Browser geöffnet haben, wurden Sie <strong>nicht mehr dazu aufgefordert, vs Code zu starten</strong> . |  Tipps: <ul><li>Stellen Sie sicher <i>, dass Sie die vs Code mindestens einmal gestartet haben, und warten Sie auf den Abschluss der Installation in der Statusleiste.</i></li><li>Wenn dies nicht funktioniert, führen Sie den Befehl "Live Share: Start Programm Setup" aus.</li><li>**Linux-Benutzer**: Wenn Sie aufgefordert werden, Ihr Administrator Kennwort einzugeben (sudo), wenn Sie den obigen Befehl ausführen, verwenden Sie dies.</li><li>Weitere Informationen finden Sie unter [Manuelles zusammenfügen](reference/manual-join.md) als Problem Umgehung.</li></ul> Wenn Sie dieses Problem erreichen, würden wir gerne sehen, was passieren kann, also [Protokollieren Sie einen Fehler](https://aka.ms/vsls-new-issue). |
| VS | <strong>Beitreten:</strong> Sie wurden nach dem Öffnen der joinseite in einem Browser <strong>nicht zur Eingabe von vs aufgefordert/sind nicht</strong> in der Lage. |  Unter [Manuelles Beitreten](reference/manual-join.md) finden Sie weitere Informationen.<br /><br /> Wir freuen uns auch, ihre Protokolle zu sehen. [melden](https://aka.ms/vsls-problem) Sie sich daher mit Visual Studio "Problem melden..." an. befinden. |
| Alle | <strong>Beitreten:</strong> Sie sollten <strong>den joinlink lieber direkt in Visual Studio/vs Code einfügen</strong> , anstatt auf den Weblink zu klicken. | Unter [Manuelles Beitreten](reference/manual-join.md) finden Sie weitere Informationen. |
| Alle | <strong>Beitreten:</strong> Wenn Sie über den Browser beitreten, sehen Sie eine Meldung, die besagt, dass**der Besitzer des Arbeitsbereichs Offline**ist. | Mögliche Problem Umgehungen:<br /><ul><li>Versuchen Sie, [manuell beizutreten](reference/manual-join.md). Aufgrund von Dienst Problemen, die sich nicht auf manuelle Joins auswirken, haben wir Probleme mit Regions übergreifenden Joins (z. b. "USA, Osten" und "USA, Westen").</li><li>Live share kann bei Ausführung im Verbindungs Modus "automatisch" nicht direkt an den Host weitergeleitet werden. [Relaymodus](reference/connectivity.md)testen.</li></ul>Weitere Möglichkeiten finden Sie unter Problembehandlung bei der [Konnektivität](#connectivity) |
| VS Code | <strong>Beitreten:</strong> Sie haben sich vor der <strong>Anmeldung</strong>über den Browser verknüpft, wurden nicht aufgefordert, sich</strong>anzumelden, und der Join wurde nie abgeschlossen. |  Dies ist ein [bekannter Fehler](https://github.com/MicrosoftDocs/live-share/issues/167). Klicken Sie auf das Element Anmeldestatus Leiste, um sich anzumelden und dann erneut beizutreten. |

## <a name="connectivity"></a>Konnektivitäts-

Die folgenden Informationen können Ihnen bei der Problembehandlung helfen, wenn beim anmelden, bei der Freigabe oder beim beitreten Probleme im Zusammenhang mit Konnektivität oder Timeouts auftreten.

Wie in den [Konnektivitätsanforderungen für Live Share](reference/connectivity.md) Artikel beschrieben, unterscheiden sich verschiedene Verbindungs Modi von verschiedenen Anforderungen, damit einige unterschiedliche potenzielle Probleme auftreten können.

| Tool | Problem | Mögliche Ursache |
|------|------|----------------|
| Alle | Sie verwenden einen <strong>Proxy</strong> und sehen eine Reihe von Konnektivitätsproblemen. | Proxy Einstellungen können knifflig sein.  Legen Sie die Umgebungsvariablen **HTTP_PROXY** und **HTTPS_PROXY** **Global** fest, und starten Sie dann das Tool neu. Weitere Informationen finden Sie unter [Proxy Einstellungen](reference/connectivity.md#proxies) . Es gibt wahrscheinlich einige Konfigurationen, die wir noch nicht unterstützen, und [lassen Sie uns wissen](https://github.com/MicrosoftDocs/live-share/issues/86) , wenn dies für Sie nicht funktioniert. |
| VS Code | Wenn Sie nach der Installation der Erweiterung und beim ersten Starten vs Code eine <strong>Fehlermeldung angezeigt wird, wenn die Installation abgeschlossen ist, wird in der Statusleiste angezeigt</strong>. |  Sie können nicht auf das Internet zugreifen, oder der Zugriff auf Download.VisualStudio.Microsoft.com und/oder Download.Microsoft.com auf Port 443 wird von Ihrer persönlichen oder Unternehmens Firewall blockiert. Informationen dazu, warum Live Share an dieser Stelle etwas herunterladen muss, finden Sie [hier](https://github.com/MicrosoftDocs/live-share/issues/58) . |
| Alle | Sie <strong>können sich nicht bei Visual Studio Live Share anmelden</strong> . | Sie können nicht auf das Internet zugreifen, oder der Zugriff auf *. LiveShare.vsengsaas.VisualStudio.com an Port 80/443 wird von Ihrer persönlichen oder Unternehmens Firewall blockiert. Geben Sie https://insiders.liveshare.vsengsaas.visualstudio.com in einem Browser ein, und überprüfen Sie, ob Sie auf der Startseite Visual Studio Live share. |
| Alle | Sie befinden sich im <strong>Auto-Modus</strong> (Standardeinstellung), können sich anmelden, sehen aber einen <strong>Timeout-oder Verbindungsfehler</strong> , wenn Sie eine Freigabe oder einen Verbindungsfehler anzeigen. | Entweder der Direct-und der Relay-Modus können keine Verbindung herstellen, oder es gibt einen Fehler im Auto-Modus. Wenn Sie nach dem [Wechsel zum direkt-oder Relaymodus](reference/connectivity.md#changing-the-connection-mode)eine Verbindung herstellen können, führen Sie [einen Fehler](https://aka.ms/vsls-problem)aus. |
| Alle | Sie befinden sich im <strong>direkt Modus</strong>und sind in der Lage, sich anzumelden, aber es wird ein <strong>Timeout oder ein Verbindungsfehler</strong> angezeigt, wenn Sie Freigabe oder Beitritt. | Der Gast und der Host können nicht direkt eine Verbindung herstellen. Verwenden Sie den [Auto-oder Relaymodus](reference/connectivity.md#changing-the-connection-mode) , um festzustellen, ob das Problem ausfällt. Möglicherweise müssen Sie [Live Share über Ihre persönliche Firewall manuell zulassen](reference/connectivity.md#manually-adding-a-firewall-entry) oder einfach den Relaymodus verwenden. |
| Alle | Sie befinden sich im <strong>Relaymodus</strong>und sind in der Lage, sich anzumelden, werden jedoch über einen <strong>Timeout-oder Verbindungsfehler</strong> benachrichtigt, wenn eine Freigabe oder ein Verbindungsfehler auftritt. | Der Zugriff auf *.Servicebus.Windows.NET auf Port 80/443 blockiert wird, die von Ihrer persönlichen und Unternehmensdaten Firewall blockiert wird. [Direkter Modus](reference/connectivity.md#changing-the-connection-mode)testen. |

Weitere Informationen zu Konnektivitätsanforderungen finden Sie im Artikel [Verbindungsanforderungen für Live Share](reference/connectivity.md) .

## <a name="see-also"></a>Siehe auch

Schnellstarts

- [Freigeben Ihres ersten Projekts](quickstart/share.md)
- [Beitreten zu Ihrer ersten Sitzung](quickstart/join.md)

Gewusst wie

- [Zusammenarbeiten mithilfe von Visual Studio Code](use/vscode.md)
- [Zusammenarbeiten mithilfe von Visual Studio](use/vs.md)

Verweis

- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Details zur Linux-Installation](reference/linux.md)
- [Sprach- und Plattformunterstützung](reference/platform-support.md)
- [Unterstützung für Erweiterung](reference/extensions.md)

Treten weiterhin Probleme auf? Sie können [Feedback bereitstellen](support.md).

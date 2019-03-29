---
title: Sicherheit – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Informationen zu den Sicherheitsfeatures von Visual Studio Live Share.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 754a740118ef9e6de2463fb3bb0537af350409aa
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640197"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Sicherheitsfeatures von Live Share

Zusammenarbeitssitzungen in Visual Studio Live Share sind leistungsstarke, da sie ermöglichen eine beliebige Anzahl von Personen in einer Sitzung beitreten und gemeinsam zu bearbeiten, Debuggen und vieles mehr. Allerdings ist diese Zugriffsebene wird angegeben, Sie zweifellos die Sicherheitsfunktionen interessant, die Live Share bietet. In diesem Artikel stellen wir einige Empfehlungen und die Optionen zum Sichern Ihrer Umgebung aus, je nach Bedarf bereit.

**Wie bei jedem Tool für die Zusammenarbeit, denken Sie daran, dass Sie nur von Code, den Inhalt und die Anwendungen für Personen freigeben sollten, denen Sie vertrauen.**

## <a name="connectivity"></a>Konnektivität

Alle Verbindungen in Visual Studio Live Share sind SSH oder SSL verschlüsselt und authentifiziert ein zentraler Dienst, um sicherzustellen, dass nur die in der zusammenarbeitssitzung den Inhalt zugreifen können. Standardmäßig werden Live Share versucht, eine direkte Verbindung und fällt zurück auf einem Cloud-Relay, wenn eine Verbindung zwischen dem Gast und dem Host hergestellt werden kann. Beachten Sie, dass Live Share-Cloud-Relay keiner Datenverkehr, die über ihn weitergeleitet behält und nicht "" den Datenverkehr in keiner Weise snoop. Wenn Sie lieber nicht das Relay verwenden können Sie Einstellungen für immer direkt eine Verbindung ändern.

Weitere Informationen zum Ändern dieses Verhalten und Anforderungen an die Live Share-Konnektivität, finden Sie unter  **[Konnektivitätsanforderungen Live Share](connectivity.md)**.

## <a name="invitations-and-join-access"></a>Einladungen und Join-Zugriff

Jedes Mal, Sie starten eine neue zusammenarbeitssitzung, Live Share generiert eine **neuen eindeutigen Bezeichner** , die in den Einladungslink platziert wird. Diese Links erhalten Sie eine solide, sichere Grundlage für diese laden Sie vertrauen, da der Bezeichner in der Verknüpfung "nicht-zu erraten" und _nur gültig für die Dauer einer Sitzung für die einzelnen Zusammenarbeit_.

### <a name="removing-an-unexpected-guest"></a>Entfernen eine unerwartete Gast

Als Host werden Sie automatisch benachrichtigt, wenn ein Gast der zusammenarbeitssitzung verknüpft.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Die Benachrichtigung erhalten Sie noch besser: die Möglichkeit, einen Gast zu entfernen, der hinzugefügt wurde, wenn aus irgendeinem Grund diese Ihnen nicht bekannt ist. (Z. B., wenn Sie versehentlich-Link Ihrer auf einem unternehmensweiten Chatsystem gesendet und ein zufälliger Mitarbeiter verknüpft.) Klicken Sie einfach auf die Schaltfläche "Entfernen" in der Benachrichtigung, die angezeigt wird, und sie aus der zusammenarbeitssitzung ausgeworfen.

In **VS Code**, auch wenn Sie eine Join-Benachrichtigung geschlossen haben, haben auch die Möglichkeit, einen Teilnehmer, zu entfernen. Indem Sie die Live Share-Ansicht im Explorer oder in der benutzerdefinierten Registerkarte in der Aktivitätsleiste von VS Code öffnen, können Sie zeigen oder mit der rechten Maustaste den Teilnehmer-Namen und wählen Sie das Symbol für "Remove-Teilnehmer" oder die Option.

![Entfernen Sie die Teilnehmer in Visual Studio Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Eine Gast-Genehmigung

Teilnehmer, die eine zusammenarbeitssitzung verknüpfen werden in der Regel **Live Share angemeldet** mithilfe einer Microsoft-Geschäfts- oder schulkonto (AAD), persönlichen Microsoft-Konto oder GitHub-Konto. Während "Benachrichtigung + entfernen" Standardeinstellung für angemeldeten Benutzer bietet eine gute Mix Geschwindigkeit und Steuerelement für diese Gastbetriebssysteme, Sie möchten **Dinge Sperren** ein wenig mehr, wenn Sie etwas vertrauliche durchführen.

Darüber hinaus kann unter bestimmten Umständen, die alle Gäste anmelden, um eine Zusammenarbeit beizutreten erzwingen Sitzung problematisch sein. Beispiele hierfür sind, fordert den Benutzer noch nicht mit Live Share als Gast schulungsumgebung/Szenarien, verknüpfen, oder wenn Sie mit jemand zusammenarbeiten, die nicht eine der unterstützten Kontotypen ist. Aus diesen Gründen Live Share können Benutzern, die **nicht angemeldet** zusammenarbeitssitzungen als verknüpfen **schreibgeschützte** Gäste. Während der Host muss **genehmigen** diese Gäste, bevor sie in der Standardeinstellung hinzugefügt werden können, Sie möchten diese Gäste "Anonym" unterbinden, oder stattdessen immer genehmigen.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Erfordern Gast Genehmigung für Anmeldung von Benutzer

Wenn Sie möchten zu verhindern, dass Gäste Beitritt Ihrer Zusammenarbeit Sitzungen, bis Sie "Diese genehmigt haben" angemeldet, ändern Sie die folgende Einstellung:

* In **VS Code**, fügen Sie Folgendes "Settings.JSON" (Datei > Voreinstellungen > Einstellungen):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* In **Visual Studio**, legen Sie Extras > Optionen > Live Share > "Gast-Genehmigung erforderlich" auf "true".

    ![Visual Studio-Einstellungen-Fenster mit dem Gast die Genehmigung festlegen hervorgehobenen](../media/vs-setting-guestapproval.png)

Ab diesem Punkt werden Sie gefragt werden, jedem Gast zu genehmigen, die verknüpft.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

Als Gast, wenn Sie eine Sitzung beitreten, in denen diese Einstellung aktiviert ist muss der Host, Sie werden benachrichtigt, in der Statusleiste oder Verknüpfen von Dialogfeld mit dem Live Share auf dem Host auf Genehmigung wartet.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Automatisch ablehnen oder akzeptieren Benutzer, die nicht (anonym) angemeldet sind

Wie oben beschrieben, Live Share können konfiguriert **Benutzer, die nicht angemeldet sind** verknüpfen eine zusammenarbeitssitzung als **schreibgeschützte** Gäste.  Zwar sind All dies **"Anonym" Gäste müssen einen Namen eingeben** bei der Teilnahme an ein einfacher Namen nicht bietet das gleiche Maß an Sicherheit als eine echte Anmeldung. Aus diesem Grund **in der Standardeinstellung wird der Host genehmigen aufgefordert** anonymen Gast unabhängig von der "Genehmigung Gast" oben beschriebenen Einstellung.

Sie können **immer abgelehnt** (anonyme Gäste deaktivieren) oder **immer annehmen** anonyme Benutzer stattdessen wie folgt:

* In **VS Code**legen `liveshare.anonymousGuestApproval` in "Settings.JSON" (Datei > Voreinstellungen > Einstellungen) auf `accept`, `reject`, oder `prompt` (Standard) nach Bedarf.

* In **Visual Studio**, legen Sie Extras > Optionen > Live Share > "anonyme Gast-Genehmigung" zu akzeptieren, ablehnen oder die Eingabeaufforderung (Standard) als geeignet.

 **Unabhängig davon, denken Sie daran, dass Sie nur Live Share senden soll Einladung-Links zu Personen, die Sie vertrauen.**

## <a name="controlling-file-access-and-visibility"></a>Steuern den Zugriff auf Dateien und Sichtbarkeit

Als Gast erhalten Sie Live Share remote Modell schnelle Lese-/Schreibzugriff auf Dateien und Ordner, die der Host für Sie freigegeben haben, ohne den gesamten Inhalt eines Projekts zu synchronisieren. Sie können daher unabhängig navigieren und Bearbeiten von Dateien in der Struktur für die gesamte freigegebene Datei. **Allerdings diese Freiheit einige Risiken auf dem Host darstellen.** Konzept kann Entwickler entscheiden, und Quellcode, ohne Ihr Wissen ändern oder finden Sie unter vertrauliche Quellcode oder "Geheimnisse" an einer beliebigen Stelle in der Struktur freigegebene Datei gefunden. Als Host, daher sollten Sie nicht immer den Gast den Zugriff auf die gesamte eines Projekts, die Sie freigegeben haben. Glücklicherweise ist ein weiteren Vorteil dieses Modells remote an, dass Sie entscheiden können, um "Ausschließen von Dateien, die Sie nicht für andere freigeben, ohne auf Funktionalität verzichten möchten". Von Gästen können immer noch an Dinge wie Debugsitzungen erhalten, die normalerweise Zugriff auf diese Dateien erfordern bei Bedarf in so ihre eigenen teilnehmen.

Sie erreichen dies durch das Hinzufügen einer **. vsls.json** zu dem Ordner oder das Projekt, die Sie teilen sich die Datei. Alle Einstellungen, die Sie diese JSON-formatierte Datei hinzufügen, ändert wie Live Share-Dateien verarbeitet. Abgesehen von der Sie direkt steuern, können diese Dateien auch übergeben werden, an die quellcodeverwaltung damit jeder Benutzer beim Klonen eines Projekts werden diese Regeln durch ohne zusätzlichen Aufwand ihrerseits nutzen können.

Es folgt ein Beispiel. vsls.json-Datei:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> Sie können auch die alle Dateien/Ordner Sie freigeben, **schreibgeschützte** beim Starten einer zusammenarbeitssitzung. Finden Sie unter [unten](#read-only-mode) Details.

Betrachten Sie diese Eigenschaften wie zu ändern, welche Gäste Möglichkeiten.

### <a name="properties"></a>Eigenschaften

Die **ExcludeFiles** Eigenschaft können Sie eine Liste von (sehr ähnlich wie die gitignore-Dateien gefunden) Datei-globmuster angeben, die verhindert, dass Live Share bestimmte Dateien oder Ordner für Gäste öffnen. Beachten Sie, dass dies einschließlich Szenarien wie Gast ist _befolgen oder das Springen zu Ihrem bearbeiten-Speicherort, in eine Datei während des Debuggens Zusammenarbeit stepping alle Funktionen für die codenavigation wie zur Definition und vieles mehr zu wechseln._ Es ist für Dateien vorgesehen, die Sie nie unter keinen Umständen ähneln, enthält die geheimen Schlüssel, Zertifikate oder Kennwörter freigeben möchten. Da sie z. B. Sicherheit steuern. vsls.json-Dateien sind immer ausgeschlossen.

Die **HideFiles** Eigenschaft entspricht, ist jedoch nicht so streng. Diese Dateien werden aus der Dateistruktur einfach ausgeblendet. Angenommen, Sie aufgetreten sind. eine dieser Dateien während des Debuggens schrittweise, ist es immer noch im Editor geöffnet. Diese Eigenschaft ist vor allem nützlich, wenn Sie keine gitignore-Datei-Setup verfügen (wie der Fall wäre, wenn Sie einen anderen Quellcodeverwaltungssystem verwenden), oder wenn Sie möchten einfach zu erweitern, was bereits vorhanden ist, überladen oder Verwirrung zu vermeiden.

Die **Gitignore** Einstellung legt fest, wie der Inhalt der gitignore-Dateien in freigegebenen Ordnern von Live Share verarbeitet werden soll. Standardmäßig werden alle Globs finden Sie in der gitignore-Dateien behandelt, als ob sie in der Eigenschaft "HideFiles" angegeben wurden. Sie können jedoch ein anderes Verhalten mithilfe einer der folgenden Werte:

| Option    | Ergebnis                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | ".gitignore" Inhalt ist sichtbar für Gäste, die in der Dateistruktur (vorausgesetzt, dass sie von einem Gast-Editor-Einstellung nicht gefiltert werden). |
| `hide`    | **Der Standardwert.** Globs in ".gitignore" werden verarbeitet, als wären sie in der Eigenschaft "HideFiles".                   |
| `exclude` | Globs in ".gitignore" werden verarbeitet, als wären sie in der Eigenschaft "ExcludeFiles".                                 |

Ein Nachteil der `exclude` Einstellung ist, dass die Inhalte der Ordner wie "node_modules" häufig in ".gitignore sind", jedoch können während des Debuggens schrittweise hilfreich sein. Live Share unterstützt daher die Möglichkeit, eine Regel mit reverse "!" in der ExcludeFiles-Eigenschaft. Beispielsweise. vsls.json-Datei würde alles in ".gitignore", mit Ausnahme von "node_modules" ausschließen:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Die ein- und ausschließen Regeln werden getrennt verarbeitet, wenn Sie weiterhin "node_modules", um die Übersichtlichkeit, ohne sie tatsächlich ausgeschlossen ausblenden möchten, Sie einfach die Datei wie folgt bearbeiten können:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>. vsls.json-Dateien in Unterordnern

Zum Schluss wie gitignore-Datei. vsls.json-Dateien in Unterordner eingefügt werden können. Ausblenden/Exclude-Regeln werden anhand der ab dem. vsls.json-Datei in den Stammordner, die Sie freigegeben haben (sofern vorhanden), und klicken Sie dann durchlaufen an jeden Unterordner von dort führende für eine bestimmte Datei, suchen Sie nach. vsls.json-Dateien verarbeiten. Der Inhalt der. vsls.json-Dateien in Ordnern, je weiter unten in der Dateistruktur dann ergänzen (oder Außerkraftsetzung) auf höheren Ebenen bestehenden Regeln.

### <a name="disabling-external-file-sharing"></a>Deaktivieren die externe Dateifreigabe

In der Standardeinstellung Live-Freigabe wird auch freigeben, der Host öffnet, Dateien, die extern auf den freigegebenen Ordner sind / Lösung. Dies erleichtert Ihnen, schnell um andere zugehörigen Dateien öffnen können, ohne sich erneut freigeben.

Wenn Sie diese Funktion deaktivieren möchten:

* In **VS Code**, fügen Sie "Settings.JSON" Folgendes:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* In **Visual Studio**, legen Sie die Tools &gt; Optionen &gt; Live Share &gt; "Freigabe externe Dateien" auf "false"

## <a name="read-only-mode"></a>Nur-Lese Modus

Manchmal, wenn Sie Ihren Code als Host gemeinsam verwenden, möchten Sie nicht die Gäste Änderungen vornehmen. Sie benötigen den Gast auf einen Blick auf einige der Code, oder Sie Ihr Projekt für einer großen Anzahl von Gästen angezeigt werden, und möchten nicht, dass unnötigen oder versehentlichen Änderungen vorgenommen werden. Live-Freigabe bietet die Möglichkeit zur Freigabe von Projekten im schreibgeschützten Modus.

Als Host, bei der Freigabe müssen Sie die Option zum Aktivieren von nur-Lese Modus für eine Zusammenarbeit. Bei Gast beitritt, werden, werden keine Änderungen an den Code vornehmen, obwohl Sie weiterhin des jeweils anderen Cursor angezeigt und hervorgehoben sowie navigieren Sie durch das Projekt.

Sie können weiterhin zusammen mit Gästen im schreibgeschützten Modus debuggen. Gäste müssen nicht die Möglichkeit, schrittweise Durchlaufen des Debugvorgangs zur Verfügung, jedoch können immer noch hinzufügen oder entfernen Haltepunkte, und untersuchen Sie Variablen. Darüber hinaus können Sie immer noch Server und -Terminals (schreibgeschützt) für Gäste freigeben.

Erfahren Sie mehr über das Starten einer zusammenarbeitssitzung nur-Lese: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Gemeinsames Debuggen

Wenn Sie schwierige coding Probleme oder Fehler geht, kann die müssen eines zusätzlichen Paars Augen beim Debuggen sehr nützlich sein. Visual Studio Live Share ermöglicht "collaborative debugging" oder "gleichzeitig Debuggen", indem alle Gäste die Debugsitzung freigeben, wenn der Host Debuggen startet.

Als Host haben Sie vollständige Kontrolle über eine Debugsitzung gestartet oder beendet, aber gleichzeitig zu debuggen darstellen, einige Risiken Wenn Sie gemeinsam mit einer anderen Person, die Sie nicht vertrauen. Live Share ermöglicht Gäste Sie einladen, Konsole/REPL-Befehle auszuführen, und es ist daher **ein Risiko des Ausführens eines Befehls, die Sie nicht möchten, führen sie von einem böswilligen Akteur**.

Daher sollten Sie **Debuggen nur zusammen mit denen Sie vertrauen.**

Weitere Informationen: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Freigeben von einem lokalen server

Beim gemeinsamen Debuggen kann es sehr hilfreich sein, Zugriff auf verschiedene Teile der Anwendung zu erhalten, die den Gästen vom Gastgeber für die Debugsitzung „serviert“ werden. Sie möchten möglicherweise Zugriff auf die app in einem Browser, auf eine lokale Datenbank zugreifen oder einen REST-Endpunkt in den Tools erreicht. Live Share können Sie "Share a Server" der genau denselben Port der Gastcomputer einen anderen lokalen Port auf dem Computer des Hosts zugeordnet ist. Als Gast, können Sie dann eine Interaktion mit der Anwendung genau so, als ob es lokal auf Ihrem Computer ausgeführt wurde (z. B. Host und Gast können sowohl Zugriff auf eine Web-app unter http://localhost:3000).

Als Host und Sie sollten jedoch **werden mit den Ports, die Sie freigeben sehr selektiven** mit Gäste und nur-Anwendung stattdessen Systemports ports. Für Gäste verhalten sich freigegebene Ports so, als würde der Server oder Dienst auf dem lokalen Gastcomputer ausgeführt werden. Dies ist zwar sehr nützlich, kann aber auch riskant sein, wenn der falsche Port freigegeben wird. Aus diesem Grund ist Live Share keine Annahmen über Was soll, oder sollte nicht freigegeben werden, ohne eine Konfigurationseinstellung und dem Host, der eine Aktion.

In Visual Studio die **web Anwendungsport** angegeben in ASP.NET-Projekten ist **automatisch während des Debuggens nur freigegebene** um Gastzugriff für die Web-app zu ermöglichen, bei der Ausführung. Allerdings können Sie diese Automatisierung deaktivieren, indem Sie die Einstellung Tools > Optionen > Live Share > "Freigabe Web-app Debuggen" auf "False", falls gewünscht.

In Visual Studio Code, Live-Freigabe versucht, **erkennen die richtigen Anwendungsports** und teilen Sie sie. Allerdings können Sie diese deaktivieren, indem Sie "Settings.JSON" Folgendes hinzufügen:

        liveshare.autoShareServers: false

Walten Sie in beiden Fällen Sorgfalt, wenn zusätzliche Ports freigeben.

Erfahren Sie mehr über das Konfigurieren dieser Funktion: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Freigeben von einem terminal

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise ermöglicht Live Share es Ihnen als Gastgeber, für Gäste optional „ein Terminal freizugeben“. Das freigegebene Terminal kann schreibgeschützt oder vollständig für die Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Als Host fungiert können Sie um weitere Mitwirkende entweder nur die Ausgabe anzuzeigen oder um eine beliebige Anzahl von der Befehlszeile verwenden Tools zum Ausführen von Builds, Tests oder sogar selektieren Sie umgebungsspezifische-Probleme zu ermöglichen.

Nur Hosts können beginnen, freigegebener Terminals, um zu verhindern, dass Gäste aus einen Startvorgang und Aktionen, die Sie nicht erwartet oder überwacht werden. Wenn Sie ein freigegebenes Terminal als Host starten, können Sie angeben, ob er sollte schreibgeschützt sein oder Lese-/Schreibzugriff. Im zweiten Fall kann jede Person einschließlich des Gastgebers Befehle im Terminal eingeben. Dadurch können unerwünschte Gastaktionen leicht unterbunden werden. **Die Lese- und Schreibberechtigungen sollten Sie aus Sicherheitsgründen ausschließlich Gästen bereitstellen, die darauf angewiesen sind**. Terminals mit Leseberechtigungen sollten Sie in Szenarios einsetzen, in denen Gäste nur die Ausgabe der von Ihnen ausgeführten Befehle sehen dürfen.

In Visual Studio werden Terminals standardmäßig nicht freigegeben. In VS Code Terminals werden automatisch freigegeben **schreibgeschützte** standardmäßig. Allerdings können Sie diese deaktivieren, indem Sie "Settings.JSON" Folgendes hinzufügen:

```json
"liveshare.autoShareTerminals": false
```

Weitere Informationen: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD-Administratorzustimmung

Bei der Anmeldung mit einem Microsoft gesichert **Geschäfts-, Schul- oder UNI-e-Mail-Adresse** möglicherweise folgende Meldung angezeigt, **"Administratorgenehmigung"** bei der Anmeldung. Dies ist da Live Share Lesezugriff auf Benutzerinformationen für seine Sicherheitsfunktionen erfordert und der Azure AD-Mandanten erforderlich "administratorzustimmung" für neue Anwendungen, die Zugriff auf den Inhalt des Verzeichnisses.

Ihr AD-Administrator müssen zum Beheben dieses Problems für Sie mit den folgenden Informationen:

* **Anwendungsname**: Visual Studio-Livefreigabe (Insider)
* **Anwendungstyp**: Webanwendung
* **Anwendungsstatus**: Produktion
* **Delegierte Berechtigungen**: User.Read
* **Anwendungs-URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **Antwort-URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Dies müsste nur einmal für jede Person, die Live Share ausgeführt werden. Finden Sie unter [hier](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) und [hier](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) Details.

## <a name="see-also"></a>Siehe auch

* [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
* [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
* [Anforderungen an die Konnektivität für Live Share](connectivity.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

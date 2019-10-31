---
title: 'Sicherheit: Visual Studio Live Share | Microsoft-Dokumentation'
description: Informationen zu den Sicherheitsfeatures von Visual Studio Live share.
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
ms.openlocfilehash: 2f3a2adf0be13071f22a8ea7e33800af6f9099b5
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170103"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Sicherheitsfeatures von Live Share

Zusammenarbeits Sitzungen in Visual Studio Live Share sind so leistungsfähig, dass Sie eine beliebige Anzahl von Benutzern in einer Sitzung einbinden und kollaborative Bearbeitung, Debuggen usw. durcharbeiten können. Bei dieser Zugriffsebene sind Sie jedoch zweifellos an den Sicherheitsfeatures interessiert, die Live Share bereitstellt. In diesem Artikel werden einige Empfehlungen und Optionen zum Sichern Ihrer Umgebung nach Bedarf bereitgestellt.

**Beachten Sie, wie bei jedem Tool für die Zusammenarbeit, dass Sie Code, Inhalte und Anwendungen nur für Personen freigeben sollten, denen Sie vertrauen.**

## <a name="connectivity"></a>Konnektivität

Alle Verbindungen in Visual Studio Live Share werden per SSH oder SSL verschlüsselt und für einen zentralen Dienst authentifiziert, um sicherzustellen, dass nur die in der Zusammenarbeits Sitzung Zugriff auf den Inhalt erhalten. Standardmäßig versucht Live Share, eine direkte Verbindung herzustellen, und greift auf ein cloudrelay zurück, wenn keine Verbindung zwischen dem Gast und dem Host hergestellt werden kann. Beachten Sie, dass das cloudrelay von Live Share keinen Datenverkehr beibehält, der durch ihn weitergeleitet wird, und den Datenverkehr in keiner Weise "durchläuft. Wenn Sie jedoch lieber das Relay nicht verwenden möchten, können Sie die Einstellungen so ändern, dass Sie immer direkt eine Verbindung herstellen.

Weitere Informationen zum Ändern dieser Verhaltensweisen und Live Share der Konnektivitätsanforderungen finden Sie unter **[Konnektivitätsanforderungen für Live Share](connectivity.md)** .

## <a name="invitations-and-join-access"></a>Einladungen und joinzugriff

Jedes Mal, wenn Sie eine neue Zusammenarbeits Sitzung starten, generiert Live Share einen **neuen eindeutigen Bezeichner** , der in den Einladungslink eingefügt wird. Diese Links stellen eine solide, sichere Grundlage dar, um die vertrauenswürdigen Personen einzuladen, da der Bezeichner in der Verknüpfung "nicht ausstellbar" ist und _nur für die Dauer einer einzelnen Zusammenarbeits Sitzung gültig_ist.

### <a name="removing-an-unexpected-guest"></a>Entfernen eines unerwarteten Gasts

Als Host werden Sie automatisch benachrichtigt, wenn ein Gast der Zusammenarbeits Sitzung Beitritt.

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

Die Benachrichtigung bietet Ihnen die Möglichkeit, einen Gast, der verknüpft ist, zu entfernen, wenn Sie ihn aus irgendeinem Grund nicht kennen. (Wenn Sie z. b. versehentlich Ihren Link in einem unternehmensweiten Chat-System gepostet haben und ein zufälliger Mitarbeiter beigetreten ist.) Klicken Sie einfach auf die Schaltfläche "entfernen" in der Benachrichtigung, die angezeigt wird und aus der Zusammenarbeits Sitzung aussteht.

In **vs Code**, auch wenn Sie eine joinbenachrichtigung verworfen haben, können Sie auch einen Teilnehmer entfernen. Wenn Sie die Live Share Ansicht im Explorer oder auf der Registerkarte Benutzer definiert in der vs Code Aktivitäts Leiste öffnen, können Sie mit dem Mauszeiger auf den Namen eines Teilnehmers klicken oder mit der rechten Maustaste darauf klicken und das Symbol bzw. die Option "Teilnehmer entfernen" auswählen.

![Teilnehmer in vs Code entfernen](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Genehmigung der Gast Genehmigung erforderlich

In der Regel werden Teilnehmer, die einer Zusammenarbeits Sitzung beitreten, bei Live Share mithilfe eines Geschäfts-, Schul-oder unikontos (AAD), eines persönlichen Microsoft-Konto oder eines GitHub-Kontos **angemeldet** . Obwohl der Standardwert "Notification + Remove" für angemeldete Benutzer eine gute Kombination aus Geschwindigkeit und Kontrolle für diese Gäste darstellt, sollten Sie die Dinge etwas genauer **Sperren** , wenn Sie einen sensiblen Vorgang ausführen.

Außerdem kann es unter bestimmten Umständen problematisch sein, dass sich alle Gäste bei der Teilnahme an einer Zusammenarbeits Sitzung anmelden. Beispiele hierfür sind das Anfordern einer neuen Live Share, um als Gast-, Classroom-/Lernszenarios oder bei der Zusammenarbeit mit Personen, die nicht über einen der unterstützten Konto Typen verfügen, teilzunehmen. Aus diesen Gründen können Live Share zulassen, dass Benutzer, die **nicht angemeldet** sind, als schreibgeschützte **Gäste an** Zusammenarbeits Sitzungen teilnehmen. Obwohl der Host diese Gäste **genehmigen** muss, bevor diese standardmäßig beitreten können, sollten Sie diese anonymen Gäste entweder nicht zulassen oder stattdessen immer genehmigen.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Anforderung der Gast Genehmigung für angemeldete Benutzer

Wenn Sie verhindern möchten, dass angemeldete Gäste ihren Zusammenarbeits Sitzungen beitreten, bis Sie Sie genehmigt haben, ändern Sie die folgende Einstellung:

* Fügen Sie in **vs Code**Folgendes zu "Settings. JSON" (Datei > Einstellungen > Einstellungen) hinzu:

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* Legen Sie in **Visual Studio**Extras > Optionen > Live Share > "Gast Genehmigung erforderlich" auf "true" fest.

    ![Visual Studio-Fenster "Einstellungen" mit hervorgehobener Gast Genehmigungs Einstellung](../media/vs-setting-guestapproval.png)

Ab diesem Zeitpunkt werden Sie aufgefordert, jeden Gast zu genehmigen, der mit verbunden ist.

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

Wenn Sie als Gast eine Sitzung beitreten, bei der diese Einstellung für den Host aktiviert ist, werden Sie in der Statusleiste oder im Dialogfeld "beitreten" benachrichtigt, die Live Share auf den Host wartet, um Sie zu genehmigen.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Automatisches ablehnen oder akzeptieren von Benutzern, die nicht angemeldet sind (anonym)

Wie oben beschrieben, können Live Share so konfiguriert werden, **dass Benutzer, die nicht angemeldet sind** , als Schreib **geschützte Gäste an** einer Zusammenarbeits Sitzung teilnehmen können.  Obwohl diese **"anonymen" Gäste beim beitreten einen Namen eingeben müssen** , bietet ein einfacher Name nicht denselben Grad an Sicherheit wie eine tatsächliche Anmeldung. Daher **wird der Host standardmäßig aufgefordert** , alle anonymen Gäste zu genehmigen, unabhängig von der oben beschriebenen Einstellung "Genehmigung der Gast Genehmigung anfordern".

Sie können die anonymen Gäste **jederzeit ablehnen** (deaktivieren) oder anonyme Benutzer immer wie folgt **akzeptieren** :

* Legen Sie in **vs Code**`liveshare.anonymousGuestApproval` in "Settings. JSON" (Datei > Einstellungen > Einstellungen) auf `accept`, `reject`oder `prompt` (Standardeinstellung) fest.

* Legen Sie in **Visual Studio**Extras > Optionen > Live Share > "anonyme Gast Genehmigung" fest, um nach Bedarf zu akzeptieren, abzulehnen oder einzugeben (Standardeinstellung).

 **Denken Sie daran, dass Sie nur Live Share Einladungs Links an Personen senden sollten, denen Sie vertrauen.**

## <a name="controlling-file-access-and-visibility"></a>Steuern des Datei Zugriffs und der Sichtbarkeit

Als Gast bietet das Remote Modell von Live Share schnellen Lese-/Schreibzugriff auf Dateien und Ordner, die der Host für Sie freigegeben hat, ohne dass der gesamte Inhalt eines Projekts synchronisiert werden muss. Sie können daher unabhängig von Dateien in der gesamten freigegebenen Dateistruktur navigieren und diese bearbeiten. **Diese Freiheit stellt jedoch einige Risiken für den Host dar.** Im Konzept könnte ein Entwickler den Quellcode ohne Ihr Wissen ändern oder den vertraulichen Quellcode oder "geheime Schlüssel" an einer beliebigen Stelle in der freigegebenen Dateistruktur sehen. Folglich möchten Sie als Host möglicherweise nicht immer, dass der Gast Zugriff auf das gesamte Projekt hat, das Sie freigeben. Ein zusätzlicher Vorteil dieses Remote Modells besteht darin, dass Sie Dateien ausschließen können, die Sie nicht für andere Benutzer freigeben möchten, ohne die Funktionalität zu beeinträchtigen. Ihre Gäste können weiterhin an Dingen wie dem Debuggen von Sitzungen teilnehmen, die normalerweise den Zugriff auf diese Dateien benötigen, wenn Sie dies selbst durchführen möchten.

Hierzu können Sie eine **vsls. JSON** -Datei zum Ordner oder Projekt hinzufügen, den Sie freigeben. Alle Einstellungen, die Sie dieser JSON-formatierten Datei hinzufügen, ändern, wie Live Share Dateien verarbeitet. Diese Dateien können nicht nur direkt gesteuert werden, sondern Sie können auch in die Quell Code Verwaltung übernommen werden, damit alle Benutzer, die ein Projekt Klonen, diese Regeln ohne zusätzlichen Aufwand nutzen können.

Im folgenden finden Sie eine Beispieldatei. vsls. JSON:

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
> Sie können auch alle Dateien/Ordner, die **Sie freigeben,** beim Starten einer Zusammenarbeits Sitzung als schreibgeschützt festlegen. Weitere Informationen finden Sie weiter [unten](#read-only-mode) .

Sehen wir uns an, wie sich diese Eigenschaften ändern, welche Möglichkeiten die Gäste haben.

### <a name="properties"></a>Eigenschaften

Die **excludefiles** -Eigenschaft ermöglicht es Ihnen, eine Liste von globmuster-Datei Mustern anzugeben (sehr ähnlich wie solche. gitignore-Dateien), die verhindert, dass Live Share bestimmte Dateien oder Ordner für Gäste öffnet. Beachten Sie, dass dies Szenarien umfasst, wie z. b. einen Gast, der _auf den Bearbeitungs Speicherort folgt, und schrittweise eine Datei beim kollaborativen Debuggen, alle Code Navigations Features wie "Gehe zu Definition" und vieles mehr._ Sie ist für Dateien bestimmt, die Sie niemals freigeben möchten, wie z. b. solche, die Geheimnisse, Zertifikate oder Kenn Wörter enthalten. Da Sie z. b. die Sicherheit steuern, werden vsls. JSON-Dateien immer ausgeschlossen.

Die **hidefiles** -Eigenschaft ist ähnlich, aber nicht ganz so streng. Diese Dateien werden einfach aus der Dateistruktur ausgeblendet. Wenn Sie z. b. während des Debuggens einen Einzelschritt in eine dieser Dateien durchgeführt haben, wird Sie weiterhin im Editor geöffnet. Diese Eigenschaft ist in erster Linie nützlich, wenn Sie nicht über eine gitignore-Datei Einrichtung verfügen (wie bei Verwendung eines anderen Quell Code Verwaltungssystems), oder wenn Sie einfach nur die bereits vorhandenen Dateien erweitern möchten, um Übersichtlichkeit oder Verwirrung zu vermeiden.

Mit der **gitignore** -Einstellung wird festgelegt, wie Live Share den Inhalt von gitignore-Dateien in freigegebenen Ordnern verarbeiten soll. Standardmäßig werden alle in gitignore-Dateien gefundenen glob-Dateien so behandelt, als wären Sie in der Eigenschaft "hidefiles" angegeben. Sie können jedoch ein anderes Verhalten auswählen, indem Sie einen der folgenden Werte verwenden:

| Option    | Ergebnis                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | . gitignore-Inhalte sind für Gäste in der Dateistruktur sichtbar (vorausgesetzt, Sie werden nicht durch eine Gast-Editor-Einstellung gefiltert). |
| `hide`    | **Der Standardwert.** Glob in. gitignore werden so verarbeitet, als ob Sie sich in der Eigenschaft "hidefiles" befinden würden.                   |
| `exclude` | Glob in. gitignore werden so verarbeitet, als ob Sie sich in der Eigenschaft "excludefiles" befinden würden.                                 |

Ein Nachteil der `exclude` Einstellung besteht darin, dass sich der Inhalt von Ordnern wie node_modules häufig in. gitignore befindet, aber nützlich sein kann, während des Debuggens schrittweise auszuführen. Folglich unterstützt Live Share die Möglichkeit, eine Regel mithilfe von "!" in der excludefiles-Eigenschaft umzukehren. Diese. vsls. JSON-Datei würde beispielsweise alles in ". gitignore" ausschließen, mit Ausnahme von node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Die Regeln zum Ausblenden und ausschließen werden separat verarbeitet. Wenn Sie also node_modules immer noch ausblenden möchten, um die Übersichtlichkeit zu reduzieren, ohne Sie tatsächlich auszuschließen, können Sie die Datei einfach wie folgt bearbeiten:

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

### <a name="vslsjson-files-in-sub-folders"></a>vsls. JSON-Dateien in Unterordnern

Und schließlich können wie. gitignore auch vsls. JSON-Dateien in Unterordnern abgelegt werden. Regeln zum Ausblenden/ausschließen werden bestimmt, indem mit der vsls. JSON-Datei im Stamm Ordner begonnen wird, den Sie freigegeben haben (sofern vorhanden). Anschließend werden die einzelnen Unterordner von dort durchlaufen, sodass nach vsls. JSON-Dateien gesucht werden konnte. Der Inhalt der vsls. JSON-Dateien in Ordnern, die sich weiter unten in der Dateistruktur befinden, werden dann auf höheren Ebenen festgelegt (oder überschrieben).

### <a name="disabling-external-file-sharing"></a>Deaktivieren der Freigabe externer Dateien

Standardmäßig gibt Live Share auch alle Dateien frei, die der Host öffnet, die für den freigegebenen Ordner bzw. die freigegebene Lösung extern sind. Dies vereinfacht das schnelle Öffnen anderer verwandter Dateien, ohne dass eine erneute Freigabe erforderlich ist.

Wenn Sie dieses Feature deaktivieren möchten:

* Fügen Sie in **vs Code**der Datei "Settings. JSON" Folgendes hinzu:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* Legen Sie in **Visual Studio**Extras &gt; Optionen &gt; Live Share &gt; "externe Dateien freigeben" auf "false" fest.

## <a name="read-only-mode"></a>Schreib geschützter Modus

Wenn Sie Ihren Code als Host freigeben, sollen die Gäste manchmal keine Änderungen vornehmen. Möglicherweise müssen Sie sich an Ihren Gast teilnehmen, um sich einen Teil Ihres Codes anzusehen, oder Sie zeigen das Projekt einer großen Anzahl von Gästen an, und Sie möchten nicht, dass unnötige oder versehentliche Änderungen vorgenommen werden. Live Share bietet die Möglichkeit, Projekte im schreibgeschützten Modus gemeinsam zu nutzen.

Als Host haben Sie bei der Freigabe die Möglichkeit, den schreibgeschützten Modus für eine Zusammenarbeits Sitzung zu aktivieren. Wenn ein Gast Beitritt, kann er keine Änderungen am Code vornehmen. Sie können jedoch weiterhin die Cursor und Highlights der anderen sehen und durch das Projekt navigieren.

Sie können im schreibgeschützten Modus immer noch mit Gästen zusammen Debuggen. Gäste haben nicht die Möglichkeit, den Debugprozess zu durchlaufen, können aber trotzdem Breakpoints hinzufügen oder entfernen und Variablen überprüfen. Darüber hinaus können Sie weiterhin Server und Terminals (schreibgeschützt) mit Gästen freigeben.

Weitere Informationen zum Starten einer Sitzung für die schreibgeschützte Zusammenarbeit finden Sie unter: [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

## <a name="co-debugging"></a>Gemeinsames Debuggen

Wenn Sie schwierige Codierungs Probleme oder Fehler beheben, kann es sehr nützlich sein, wenn Sie das Debuggen über ein zusätzliches Paar von Augen haben. Visual Studio Live Share aktiviert "kollaboratives Debuggen" oder "mitdebuggen" durch Freigeben der Debugsitzung für alle Gäste, wenn der Host das Debugging startet.

Als Host haben Sie die vollständige Kontrolle darüber, wann eine Debugsitzung gestartet oder angehalten wird, aber das kodebuggen stellt einige Risiken dar, wenn Sie nicht vertrauenswürdige Personen freigeben. Live Share können Gäste, die Sie einladen, Konsolen-/repl-Befehle auszuführen. Daher besteht das **Risiko, dass ein böswilliger Akteur einen Befehl durchführt, den Sie nicht ausführen**möchten.

Folglich sollten Sie **nur mit denjenigen, denen Sie Vertrauen, eine kodebuggen.**

Weitere Informationen: [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Freigeben eines lokalen Servers

Beim gemeinsamen Debuggen kann es sehr hilfreich sein, Zugriff auf verschiedene Teile der Anwendung zu erhalten, die den Gästen vom Gastgeber für die Debugsitzung „serviert“ werden. Möglicherweise möchten Sie in einem Browser auf die App zugreifen, auf eine lokale Datenbank zugreifen oder einen Rest-Endpunkt aus ihren Tools erreichen. Mit Live Share können Sie einen Server freigeben, der einen lokalen Port auf dem Computer des Hosts dem exakt gleichen Port auf dem Gastcomputer zuordnet. Als Gast können Sie mit der Anwendung genau so interagieren, als ob Sie lokal auf Ihrem Computer ausgeführt würde (z. b. der Host und der Gast können auf eine Web-App zugreifen, die auf http://localhost:3000) ausgeführt wird.

Als Host sollten Sie jedoch **mit den Ports, die Sie für Gäste freigeben, sehr selektiv vorgehen** und nur Anwendungsports anstelle von Systemports freigeben. Für Gäste verhalten sich freigegebene Ports so, als würde der Server oder Dienst auf dem lokalen Gastcomputer ausgeführt werden. Dies ist zwar sehr nützlich, kann aber auch riskant sein, wenn der falsche Port freigegeben wird. Aus diesem Grund trifft Live Share keine Annahmen darüber, was ohne eine Konfigurationseinstellung oder nicht freigegeben werden sollte, und der Host führt eine Aktion aus.

In Visual Studio wird der in ASP.NET-Projekten angegebene **Webanwendungs Port** **nur beim Debuggen automatisch freigegeben** , um den Gast Zugriff auf die Web-App bei der Ausführung zu vereinfachen. Sie können diese Automatisierung jedoch deaktivieren, indem Sie Tools > Optionen > Live Share > "Web-App beim Debuggen freigeben" auf "false" festlegen, wenn Sie dies bevorzugen.

In Visual Studio Code versucht Live Share, **die richtigen Anwendungsports zu erkennen** und freizugeben. Sie können dies jedoch deaktivieren, indem Sie Folgendes zu "Settings. JSON" hinzufügen:

        liveshare.autoShareServers: false

Achten Sie in beiden Fällen darauf, dass Sie zusätzliche Ports freigeben.

Weitere Informationen zum Konfigurieren des Features finden Sie hier: [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Freigeben eines Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise ermöglicht Live Share es Ihnen als Gastgeber, für Gäste optional „ein Terminal freizugeben“. Das freigegebene Terminal kann schreibgeschützt oder vollständig für die Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Als Host können Sie es anderen Projektmitarbeitern gestatten, entweder die Ausgabe zu sehen oder eine beliebige Anzahl von Befehlszeilen Tools zu verwenden, um Tests, Builds oder sogar Umgebungs spezifische Probleme auszuführen.

Nur Hosts können freigegebene Terminals starten, um zu verhindern, dass Gast Betriebssysteme gestartet werden. Wenn Sie ein frei gegebenes Terminal als Host starten, können Sie angeben, ob es schreibgeschützt oder Lese-/Schreibzugriff sein soll. Im zweiten Fall kann jede Person einschließlich des Gastgebers Befehle im Terminal eingeben. Dadurch können unerwünschte Gastaktionen leicht unterbunden werden. **Die Lese- und Schreibberechtigungen sollten Sie aus Sicherheitsgründen ausschließlich Gästen bereitstellen, die darauf angewiesen sind**. Terminals mit Leseberechtigungen sollten Sie in Szenarios einsetzen, in denen Gäste nur die Ausgabe der von Ihnen ausgeführten Befehle sehen dürfen.

In Visual Studio werden Terminals standardmäßig nicht freigegeben. In vs Code werden Terminals standardmäßig automatisch als schreibgeschützt **frei** gegeben. Sie können dies jedoch deaktivieren, indem Sie Folgendes zu "Settings. JSON" hinzufügen:

```json
"liveshare.autoShareTerminals": false
```

Weitere Informationen: [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Zustimmung für Aad-Administrator

Wenn Sie sich mit einer von Microsoft gesicherten Geschäfts **-, Schul-oder Uni-e-Mail-Adresse** anmelden, wird bei der Anmeldung möglicherweise die Meldung **"Administrator Genehmigung erforderlich** Der Grund hierfür ist, dass Live Share Lesezugriff auf Benutzerinformationen für seine Sicherheitsfunktionen erfordert, und Ihr Azure AD Mandant muss für neue Anwendungen, die auf den Inhalt des Verzeichnisses zugreifen, eine "Administrator Zustimmung" erfordern.

Ihr AD-Administrator muss dies mit den folgenden Informationen beheben:

* **Anwendungs Name**: Visual Studio Live Share (Insider)
* **Anwendungstyp**: Web-App
* **Anwendungs Status**: Produktion
* **Delegierte Berechtigungen**: User. Read
* **Anwendungs-URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **Antwort-URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Dies muss nur einmal für alle Benutzer erfolgen, die Live Share verwenden. Weitere Informationen finden Sie [hier](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) und [hier](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) .

## <a name="see-also"></a>Siehe auch

* [Gewusst wie: zusammenarbeiten mit Visual Studio Code](../how-to-guides/vscode.md)
* [Gewusst wie: zusammenarbeiten mithilfe von Visual Studio](../how-to-guides/vs.md)
* [Anforderungen an die Konnektivität für Live Share](connectivity.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

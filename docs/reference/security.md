---
title: Sicherheit | Microsoft-Dokumentation
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
ms.openlocfilehash: 2b3021e96b321976772e6ab99a18cceb56929404
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870879"
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

Beim Initiieren einer Sitzung zwischen Peers wird von Live Share versucht, eine Peer-zu-Peer-Verbindung herzustellen. wenn dies nicht möglich ist (z. b. aufgrund von Firewalls/NATs), wird ein cloudrelay verwendet. Allerdings werden in beiden Verbindungstypen (P2P oder Relay) alle zwischen Peers übertragenen Daten mithilfe des SSH-Protokolls End-to-End verschlüsselt. Im Fall einer relayverbindung wird die SSH-Verschlüsselung über TLS-verschlüsselte websockets überlagert. Dies bedeutet, dass Live Share nicht vom cloudrelaydienst abhängig ist. Auch wenn das Relay kompromittiert wurde, konnte die Live Share Kommunikation nicht entschlüsselt werden.

Die Rolle des Live Share Dienstanbieter ist auf Benutzerauthentifizierung und Sitzungs Ermittlung beschränkt. Der Dienst selbst speichert oder hat keinen Zugriff auf den Inhalt einer Sitzung. Alle Benutzerinhalte in Live Share werden über die SSH-Sitzung übertragen. Dazu zählen Code, Terminals, freigegebene Server und alle anderen Funktionen zur Zusammenarbeit, die von Live Share oder Erweiterungen bereitgestellt werden, die darauf aufbauen.

Weitere Informationen zum Ändern dieser Verhaltensweisen und Live Share der Konnektivitätsanforderungen finden Sie unter **[Konnektivitätsanforderungen für Live Share](connectivity.md)**.

### <a name="wire-encryption"></a>Wire-Verschlüsselung 

Das SSH-Protokoll verwendet einen Diffie-Hellman Key-Exchange zum Einrichten eines gemeinsamen geheimen Schlüssels für die Sitzung und leitet sich von diesem Schlüssel für die symmetrische AES-Verschlüsselung ab. Der Verschlüsselungsschlüssel wird in regelmäßigen Abständen über die Dauer der Sitzung gedreht. Der geheime Schlüssel für die gemeinsame Sitzung und alle Verschlüsselungsschlüssel werden nur von beiden Seiten im Arbeitsspeicher verwaltet und sind nur für die Dauer der Sitzung gültig. Sie werden nie auf den Datenträger geschrieben oder an einen beliebigen Dienst (einschließlich Live Share) gesendet.

### <a name="peer-authentication"></a>Peer Authentifizierung

Die SSH-Sitzung ist ebenfalls bidirektional authentifiziert. Der Host (SSH-Server Rolle) verwendet die Authentifizierung mit öffentlichem und privatem Schlüssel, die für das SSH-Protokollstandard mäßig ist. Wenn ein Host eine Live Share Sitzung freigibt, wird ein eindeutiges öffentliches/privates RSA-Schlüsselpaar für die Sitzung generiert. Der private Schlüssel des Hosts wird nur im Arbeitsspeicher des Host Prozesses beibehalten. Er wird nie auf den Datenträger geschrieben oder an einen beliebigen Dienst gesendet, einschließlich des Live Share Dienstanbieter. Der öffentliche Host Schlüssel wird zusammen mit den Sitzungs Verbindungsinformationen (IP-Adresse und/oder relayendpunkt) im Live Share Dienst veröffentlicht, auf den Gäste über den Einladungslink zugreifen können. Wenn ein Gast eine Verbindung mit der SSH-Sitzung des Hosts herstellt, verwendet der Gast das SSH-Host Authentifizierungsprotokoll, um zu überprüfen, ob der Host den privaten Schlüssel enthält, der dem veröffentlichten öffentlichen Schlüssel entspricht (ohne dass der Gast den privaten Schlüssel tatsächlich erhält).

Der Gast verwendet ein Live Share Token, um sich beim Host zu authentifizieren. Das Token ist ein signiertes JWT, das vom Live Share-Dienst ausgegeben wird und Ansprüche über die Benutzeridentität (über MSA, AAD oder GitHub-Anmeldung abgerufen) enthält. Das Token weist auch Ansprüche auf, die angeben, dass der Gast Zugriff auf diese bestimmte Live Share Sitzung hat (da er über den Einladungslink verfügt und/oder der Host explizit vom Host eingeladen wurde). Der Host überprüft dieses Token und überprüft die Ansprüche (und abhängig von den Optionen, die den Host Benutzer möglicherweise auffordern), bevor der Gast den Beitritt zur Sitzung zulässt.

## <a name="invitations-and-join-access"></a>Einladungen und joinzugriff

Jedes Mal, wenn Sie eine neue Zusammenarbeits Sitzung starten, generiert Live Share einen **neuen eindeutigen Bezeichner** , der in den Einladungslink eingefügt wird. Diese Links stellen eine solide, sichere Grundlage dar, um die vertrauenswürdigen Personen einzuladen, da der Bezeichner in der Verknüpfung "nicht ausstellbar" ist und _nur für die Dauer einer einzelnen Zusammenarbeits Sitzung gültig_ ist.

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

* Fügen Sie in **vs Code** Folgendes hinzu, um settings.json (Datei > Einstellungen > Einstellungen) hinzuzufügen:

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* Legen Sie in **Visual Studio** Extras > Optionen > Live Share > "Gast Genehmigung erforderlich" auf "true" fest.

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

* Legen Sie in vs Code `liveshare.anonymousGuestApproval` settings.json (Datei > Einstellungen > Einstellungen) auf `accept` , `reject` oder `prompt` (Standardeinstellung) fest.

* Legen Sie in **Visual Studio** Extras > Optionen > Live Share > "anonyme Gast Genehmigung" fest, um nach Bedarf zu akzeptieren, abzulehnen oder einzugeben (Standardeinstellung).

 **Denken Sie daran, dass Sie nur Live Share Einladungs Links an Personen senden sollten, denen Sie vertrauen.**

## <a name="controlling-file-access-and-visibility"></a>Steuern des Datei Zugriffs und der Sichtbarkeit

Als Gast bietet das Remote Modell von Live Share schnellen Lese-/Schreibzugriff auf Dateien und Ordner, die der Host für Sie freigegeben hat, ohne dass der gesamte Inhalt eines Projekts synchronisiert werden muss. Sie können daher unabhängig von Dateien in der gesamten freigegebenen Dateistruktur navigieren und diese bearbeiten. **Diese Freiheit stellt jedoch einige Risiken für den Host dar.** Im Konzept könnte ein Entwickler den Quellcode ohne Ihr Wissen ändern oder den vertraulichen Quellcode oder "geheime Schlüssel" an einer beliebigen Stelle in der freigegebenen Dateistruktur sehen. Folglich möchten Sie als Host möglicherweise nicht immer, dass der Gast Zugriff auf das gesamte Projekt hat, das Sie freigeben. Ein zusätzlicher Vorteil dieses Remote Modells besteht darin, dass Sie Dateien ausschließen können, die Sie nicht für andere Benutzer freigeben möchten, ohne die Funktionalität zu beeinträchtigen. Ihre Gäste können weiterhin an Dingen wie dem Debuggen von Sitzungen teilnehmen, die normalerweise den Zugriff auf diese Dateien benötigen, wenn Sie dies selbst durchführen möchten.

Sie können dies erreichen, indem Sie dem Ordner oder Projekt, den bzw. das Sie freigeben, eine **.vsls.js** Datei hinzufügen. Alle Einstellungen, die Sie dieser JSON-formatierten Datei hinzufügen, ändern, wie Live Share Dateien verarbeitet. Diese Dateien können nicht nur direkt gesteuert werden, sondern Sie können auch in die Quell Code Verwaltung übernommen werden, damit alle Benutzer, die ein Projekt Klonen, diese Regeln ohne zusätzlichen Aufwand nutzen können.

Im folgenden finden Sie ein Beispiel .vsls.jsfür die Datei:

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

Die **excludefiles** -Eigenschaft ermöglicht es Ihnen, eine Liste von globmuster-Datei Mustern anzugeben (sehr ähnlich wie solche. gitignore-Dateien), die verhindert, dass Live Share bestimmte Dateien oder Ordner für Gäste öffnet. Beachten Sie, dass dies Szenarien umfasst, wie z. b. einen Gast, der _auf den Bearbeitungs Speicherort folgt, und schrittweise eine Datei beim kollaborativen Debuggen, alle Code Navigations Features wie "Gehe zu Definition" und vieles mehr._ Sie ist für Dateien bestimmt, die Sie niemals freigeben möchten, wie z. b. solche, die Geheimnisse, Zertifikate oder Kenn Wörter enthalten. Da Sie z. b. die Sicherheit steuern, werden .vsls.jsvon Dateien immer ausgeschlossen.

Die **hidefiles** -Eigenschaft ist ähnlich, aber nicht ganz so streng. Diese Dateien werden einfach aus der Dateistruktur ausgeblendet. Wenn Sie z. b. während des Debuggens einen Einzelschritt in eine dieser Dateien durchgeführt haben, wird Sie weiterhin im Editor geöffnet. Diese Eigenschaft ist in erster Linie nützlich, wenn Sie nicht über eine gitignore-Datei Einrichtung verfügen (wie bei Verwendung eines anderen Quell Code Verwaltungssystems), oder wenn Sie einfach nur die bereits vorhandenen Dateien erweitern möchten, um Übersichtlichkeit oder Verwirrung zu vermeiden.

Mit der **gitignore** -Einstellung wird festgelegt, wie Live Share den Inhalt von gitignore-Dateien in freigegebenen Ordnern verarbeiten soll. Standardmäßig werden alle in gitignore-Dateien gefundenen glob-Dateien so behandelt, als wären Sie in der Eigenschaft "hidefiles" angegeben. Sie können jedoch ein anderes Verhalten auswählen, indem Sie einen der folgenden Werte verwenden:

| Option    | Ergebnis                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | . gitignore-Inhalte sind für Gäste in der Dateistruktur sichtbar (vorausgesetzt, Sie werden nicht durch eine Gast-Editor-Einstellung gefiltert). |
| `hide`    | **Der Standardwert.** Glob in. gitignore werden so verarbeitet, als ob Sie sich in der Eigenschaft "hidefiles" befinden würden.                   |
| `exclude` | Glob in. gitignore werden so verarbeitet, als ob Sie sich in der Eigenschaft "excludefiles" befinden würden.                                 |

Ein Nachteil der- `exclude` Einstellung besteht darin, dass sich der Inhalt von Ordnern wie node_modules häufig in. gitignore befindet, aber hilfreich sein kann, wenn Sie während des Debuggens schrittweise ausführen. Folglich unterstützt Live Share die Möglichkeit, eine Regel mithilfe von "!" in der excludefiles-Eigenschaft umzukehren. Beispielsweise würde dieser .vsls.jsfür die Datei alles in ". gitignore" ausschließen, außer node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Die Regeln zum Ausblenden und ausschließen werden separat verarbeitet. Wenn Sie also node_modules immer noch ausblenden möchten, um die Übersichtlichkeit zu reduzieren, ohne Sie tatsächlich auszuschließen, können Sie die Datei wie folgt bearbeiten:

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

### <a name="vslsjson-files-in-sub-folders"></a>Dateien in Unterordnern .vsls.js

Ebenso wie. gitignore können .vsls.jsDateien in Unterordnern abgelegt werden. Regeln zum Ausblenden/ausschließen werden bestimmt, wenn Sie mit der Datei .vsls.jsin dem Stamm Ordner beginnen, den Sie freigegeben haben (sofern vorhanden), und dann in jedem Unterordner von dort durchlaufen, der zu einer bestimmten Datei geführt hat, um nach .vsls.jszu verarbeitenden Dateien zu suchen. Der Inhalt von .vsls.jsin Ordnern, die sich weiter unten in der Dateistruktur befinden, werden dann auf höheren Ebenen festgelegt (oder überschrieben).

### <a name="disabling-external-file-sharing"></a>Deaktivieren der Freigabe externer Dateien

Standardmäßig gibt Live Share auch alle Dateien frei, die der Host öffnet, die für den freigegebenen Ordner bzw. die freigegebene Lösung extern sind. Dies vereinfacht das schnelle Öffnen anderer verwandter Dateien, ohne dass eine erneute Freigabe erforderlich ist.

Wenn Sie dieses Feature deaktivieren möchten:

* Fügen Sie in **vs Code** folgenden settings.jshinzu:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* Legen Sie in **Visual Studio** Extras &gt; Optionen &gt; Live Share &gt; "externe Dateien freigeben" auf "false" fest.

## <a name="read-only-mode"></a>Schreibgeschützter Modus

Wenn Sie Ihren Code als Host freigeben, sollen die Gäste manchmal keine Änderungen vornehmen. Möglicherweise müssen Sie sich an Ihren Gast teilnehmen, um sich einen Teil Ihres Codes anzusehen, oder Sie zeigen das Projekt einer großen Anzahl von Gästen an, und Sie möchten nicht, dass unnötige oder versehentliche Änderungen vorgenommen werden. Live Share bietet die Möglichkeit, Projekte im schreibgeschützten Modus gemeinsam zu nutzen.

Als Host haben Sie bei der Freigabe die Möglichkeit, den schreibgeschützten Modus für eine Zusammenarbeits Sitzung zu aktivieren. Wenn ein Gast Beitritt, kann er keine Änderungen am Code vornehmen. Sie können jedoch weiterhin die Cursor und Highlights der anderen sehen und durch das Projekt navigieren.

Sie können im schreibgeschützten Modus immer noch mit Gästen zusammen Debuggen. Gäste haben nicht die Möglichkeit, den Debugprozess zu durchlaufen, können aber trotzdem Breakpoints hinzufügen oder entfernen und Variablen überprüfen. Darüber hinaus können Sie weiterhin Server und Terminals (schreibgeschützt) mit Gästen freigeben.

Weitere Informationen zum Starten einer Sitzung für die schreibgeschützte Zusammenarbeit finden Sie unter: [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Gemeinsames Debuggen

Wenn Sie schwierige Codierungs Probleme oder Fehler beheben, kann es sehr nützlich sein, wenn Sie das Debuggen über ein zusätzliches Paar von Augen haben. Visual Studio Live Share aktiviert "kollaboratives Debuggen" oder "mitdebuggen" durch Freigeben der Debugsitzung für alle Gäste, wenn der Host das Debugging startet.

Als Host haben Sie die vollständige Kontrolle darüber, wann eine Debugsitzung gestartet oder angehalten wird, aber das kodebuggen stellt einige Risiken dar, wenn Sie nicht vertrauenswürdige Personen freigeben. Live Share können Gäste, die Sie einladen, Konsolen-/repl-Befehle auszuführen. Daher besteht das **Risiko, dass ein böswilliger Akteur einen Befehl durchführt, den Sie nicht ausführen** möchten.

Folglich sollten Sie **nur mit denjenigen, denen Sie Vertrauen, eine kodebuggen.**

Weitere Informationen: [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Freigeben eines lokalen Servers

Beim gemeinsamen Debuggen kann es sehr hilfreich sein, Zugriff auf verschiedene Teile der Anwendung zu erhalten, die den Gästen vom Gastgeber für die Debugsitzung „serviert“ werden. Möglicherweise möchten Sie in einem Browser auf die App zugreifen, auf eine lokale Datenbank zugreifen oder einen Rest-Endpunkt aus ihren Tools erreichen. Mit Live Share können Sie einen Server freigeben, der einen lokalen Port auf dem Computer des Hosts dem exakt gleichen Port auf dem Gastcomputer zuordnet. Als Gast können Sie mit der Anwendung genau so interagieren, als ob Sie lokal auf Ihrem Computer ausgeführt würde (z. b. der Host und der Gast können auf eine Web-App zugreifen, die unter ausgeführt wird http://localhost:3000) .

Als Host sollten Sie jedoch **mit den Ports, die Sie für Gäste freigeben, sehr selektiv vorgehen** und nur Anwendungsports anstelle von Systemports freigeben. Für Gäste verhalten sich freigegebene Ports so, als würde der Server oder Dienst auf dem lokalen Gastcomputer ausgeführt werden. Dies ist zwar sehr nützlich, kann aber auch riskant sein, wenn der falsche Port freigegeben wird. Aus diesem Grund trifft Live Share keine Annahmen darüber, was ohne eine Konfigurationseinstellung oder nicht freigegeben werden sollte, und der Host führt eine Aktion aus.

In Visual Studio wird der in ASP.NET-Projekten angegebene **Webanwendungs Port** **nur beim Debuggen automatisch freigegeben** , um den Gast Zugriff auf die Web-App bei der Ausführung zu vereinfachen. Sie können diese Automatisierung jedoch deaktivieren, indem Sie Tools > Optionen > Live Share > "Web-App beim Debuggen freigeben" auf "false" festlegen, wenn Sie dies bevorzugen.

In Visual Studio Code versucht Live Share, **die richtigen Anwendungsports zu erkennen** und freizugeben. Sie können dies jedoch deaktivieren, indem Sie Folgendes zu settings.jsauf hinzufügen:

        liveshare.autoShareServers: false

Achten Sie in beiden Fällen darauf, dass Sie zusätzliche Ports freigeben.

Weitere Informationen zum Konfigurieren des Features finden Sie hier: [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Freigeben eines Terminals

Die moderne Entwicklung nutzt oft eine Vielzahl von Befehlszeilentools. Glücklicherweise ermöglicht Live Share es Ihnen als Gastgeber, für Gäste optional „ein Terminal freizugeben“. Das freigegebene Terminal kann schreibgeschützt oder vollständig für die Zusammenarbeit eingerichtet sein, damit Sie und Ihre Gäste Befehle ausführen und die Ergebnisse anzeigen können. Als Host können Sie es anderen Projektmitarbeitern gestatten, entweder die Ausgabe zu sehen oder eine beliebige Anzahl von Befehlszeilen Tools zu verwenden, um Tests, Builds oder sogar Umgebungs spezifische Probleme auszuführen.

Nur Hosts können freigegebene Terminals starten, um zu verhindern, dass Gast Betriebssysteme gestartet werden. Wenn Sie ein frei gegebenes Terminal als Host starten, können Sie angeben, ob es schreibgeschützt oder Lese-/Schreibzugriff sein soll. Im zweiten Fall kann jede Person einschließlich des Gastgebers Befehle im Terminal eingeben. Dadurch können unerwünschte Gastaktionen leicht unterbunden werden. **Die Lese- und Schreibberechtigungen sollten Sie aus Sicherheitsgründen ausschließlich Gästen bereitstellen, die darauf angewiesen sind**. Terminals mit Leseberechtigungen sollten Sie in Szenarios einsetzen, in denen Gäste nur die Ausgabe der von Ihnen ausgeführten Befehle sehen dürfen.

In Visual Studio werden Terminals standardmäßig nicht freigegeben. In vs Code werden Terminals standardmäßig automatisch als schreibgeschützt **frei** gegeben. Sie können dies jedoch deaktivieren, indem Sie Folgendes zu settings.jsauf hinzufügen:

```json
"liveshare.autoShareTerminals": false
```

Weitere Informationen: [ ![ vs Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [ ![ vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

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

## <a name="see-also"></a>Weitere Informationen

* [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
* [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio](../use/vs.md)
* [Anforderungen an die Konnektivität für Live Share](connectivity.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

---
title: Erweiterungen und das Ökosystem Support – Visual Studio Live Share | Microsoft-Dokumentation
description: Eine Übersicht über Unterstützung für Visual Studio Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 57be1ffd58be1a752974d58407adecd0d51fe9f0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640236"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>Erweiterungen und Ökosystem-Unterstützung

Eines der Hauptziele von Visual Studio Live Share ist, damit Entwickler, mit dem Komfort ihrer Favoriten, zusammenarbeiten und [ **hochgradig anpassbare** ](https://marketplace.visualstudio.com/) Tools. Auf diese Weise in vielen Fällen möglich, Ad-hoc-Interaktionen sind während des Bestehens der visuell vertraut und ergonomische, unabhängig davon, ob was mit hilfreich. Zu diesem Zweck ist es wichtig, dass Teilnehmer innerhalb einer zusammenarbeitssitzung sind auch weiterhin Erweiterungen, die unterstützen ihre [persönliche Einstellungen und Workflows](#user-specific-extensions) (z. B. Farbsymbole/Designs, tastaturzuordnungen, -Editor Produktivitätssteigerung).

Darüber hinaus werden um machen das Act eine zusammenarbeitssitzung als verknüpfen instant wie möglich bleibt dabei sehr produktive, das Ziel von Visual Studio Live Share aktivieren die Gäste automatisch die projektspezifische Tools nutzen, die dem Host freigegeben haben. Auf diese Weise können Sie einfach auf einen Link klicken, starten Sie Ihr bevorzugtes Tool und zusammenarbeiten, ohne zusätzliche Einrichtung. Um dies zu erreichen, ist es wichtig, Erweiterungen, die power den Kern [bearbeiten, erstellen und Debuggen von Workflows](#project-specific-extensions), sind vom Host zum Gast, transparent "Remote", sodass automatischer Vervollständigung, Gehe zu Definition wie, und das Debuggen " Arbeiten Sie einfach"ein.

Dieses Dokument behandelt die aktuelle bekannte Zustand für das Ökosystem der vast-Erweiterung sowie eine "Scorecard" für die oben genannten Ziele. Wenn eine Erweiterung, die diese Kriterien nicht erfüllen, und ist wichtig, Ihre persönlichen Workflows auftritt, bitte [lassen Sie uns wissen!](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>Benutzer-spezifische Erweiterungen

Erweiterungen, die benutzerspezifische Anpassungen unterstützen **muss** für den Host, Geschäfts- und **sollte** für alle Gäste funktionieren. Wenn eine Erweiterung nicht ordnungsgemäß für den Host funktioniert, wäre eine Regression, und ist wahrscheinlich ein Fehler in Visual Studio Live Share (bitte [ein Problem](https://github.com/MicrosoftDocs/live-share/issues/new) , wenn Sie eine finden Sie unter!). Wenn eine Erweiterung nicht für eine gastanwendung erwartungsgemäß verhält, ist möglicherweise eine [Änderungen in die Erweiterung selbst](#known-issues), und wir arbeiten mit dem Ökosystem zu Adresse/diese Szenarien zu verbessern.

### <a name="visual-studio-code"></a>Visual Studio Code

| Kategorie | Beispiele für | Guest-Supported? | Zusammenarbeit? |
|-|-|-|-|
| Farbdesigns | [Ein dunkles Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme), [Ausgabe Farbauswahl](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer), [Rainbow Zeichenfolge](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string), [gefärbt Regionen](https://github.com/jmihelcic/colored-regions), [eingerückt Block Hervorhebung](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting), [ TODO-Hervorhebung](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight), [Klammer Paar Farbauswahl](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *N/V* |
| Symbolsätze | [Vscode-Symbole](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), [Klassische Symbole mit Visual Studio](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *N/V* |
| Tastenbindungen | [VIM](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim), [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [Emacs-freundliche Tastaturlayout](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *N/V* |
| Codeausschnitte | [Angular v5 Codeausschnitte](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2), [HTML-Ausschnitte](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets), [SVG-Symbole](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons), [Header-Datei](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *N/V* <sup>1</sup> |
| Organisation | [Einstellungssynchronisierung](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), [Projektmanager](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager), [beschränken](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit), [Prüfpunkte](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints), [TODO-Parser](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser), [Favoriten ](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌), [Lesezeichen](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) (❌) | ✅ <sup>2</sup> | *N/V* <sup>3</sup> |
| Produktivität | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens), [automatisch umbenennen Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag), [Code Gliederung](https://github.com/patrys/vscode-code-outline), [Farbe der Hervorhebung](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight), [erhöhen Sie die Auswahl](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection), [ Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer), [Bildvorschau](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview), [JSON-Hilfsprogramm](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (zeigen), [Farbwähler](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color), [Kopieren von Word im Cursor](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word), [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens) [Git-Co-Autoren](https://github.com/rjimenezda/vscode-coauthor), [JavaScript weiter zu steigern](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions), [Turbo Konsolenprotokoll](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log), [ Gehe zum nächsten/vorherigen Element](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member), [AutoBildlauf-](https://github.com/PejmanNik/vscode-autoScroll?files=1), [NPM-Import-Version](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version) (❌), [importieren Kosten](https://github.com/wix/import-cost) (❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| REPLs | [REST-Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client), [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner), [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode), [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| Ressourcen-Manager | [MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), [ftp-Simple-](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple), [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [Brew-Dienste](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *, sofern ein Benutzer bereits mit einem Codeausschnitt vertraut sind wurde, wäre nicht erwarten, dass zur Verfügung stehen, und daher, sodass sie die freigegebene nicht unbedingt sinnvoll.*

<sup>2</sup> *dieser Erweiterung Kategorien sind so vielfältig, dass es unmöglich zu sagen ist. sie funktionieren. Allerdings in der Theorie werden, und den Schlüssel, die nicht nachverfolgt.*

<sup>3</sup> *dieser Erweiterung Kategorien von gemeinsamen Erfahrungen profitieren können, und daher benötigen wir wissen, dass die Endbenutzer-Feedback!*

<sup>4</sup> *diese erfordern, dass den Gast die Common Language Runtime Clienttools installiert haben (z. B. Node.js), und arbeiten, indem Sie Code lokal ausführen.*

<sup>5</sup> *diese arbeiten, indem Sie eine Verbindung mit einem Server irgendeiner Art und können mit beiden zentralisierten Server, Server, die der Gast freigegeben haben arbeiten.*

### <a name="visual-studio"></a>Visual Studio

Demnächst.

## <a name="project-specific-extensions"></a>Projekt-spezifische Erweiterungen

Host installierten Erweiterungen, die den Kern bearbeiten, erstellen und Debuggen einer Anwendung zu unterstützen, und beziehen sich auf eine Sprache/Plattform/Library/SDK, sollte automatisch für Gäste verfügbar sein, ohne dass diese etwas installieren. Auf diese Weise Hosts können Einrichten ihrer Umgebung zur Unterstützung der Produktivität der Entwicklung eines Projekts und ermöglichen ihren Gästen, sofort ohne zusätzlichen Voraussetzungen zu verknüpfen. Da projektspezifischen Erweiterungen subjektive oder persönliche in keiner Weise nicht sind, können diese deterministisch vom Host und Gast, gemeinsam genutzt werden ohne Beeinträchtigung der vertrauten Umgebung in den Köpfen der Entwickler.

Darüber hinaus zur Unterstützung von projektspezifischen Erweiterungen, die ein Gast installiert sind, aber der Host nicht, sie würden im Idealfall benutzerfreundlichkeit beeinträchtigt, noch funktionsfähig (z. B. Einzeldatei IntelliSense-Meldungen erhalten, dass Sie ein Dokument formatieren).

| Kategorie | Beispiele für | geteilt? | Guest-Supported? |
|-------|----------|--------|-----|
| Grammatiken / syntaxhervorhebung | [Shell Fischen](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish), [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx), [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv), [ES6-Zeichenfolge HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html), [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus), [Rainbow CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| Sprachdienste | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml), [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| JSON-Schemas | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linter | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint), [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), [Code Rechtschreibprüfung](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker), [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| Formatierungsprogramme | [Schönere](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [verschönern](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| Debugger | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| Test Runner | [Java-Testprogramm](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), [Mocha-Randleiste](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar), [Postman Runner](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman), [Jest Runner](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner), [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| Benutzerdefinierte Datei Vorschauen | [SVG-Vorschau](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer), [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz), [Markdown-Bildgröße](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| Datei oder eines Projekts Generatoren | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [C-/C++-Projekt-Generator](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| Quellcodeverwaltungsanbieter | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *derzeit nur C# und JavaScript/TypeScript mit mehr Unterstützung in Kürze verfügbar.*

<sup>2</sup> *unterstützt nur das aktuelle Dokument, da Gäste nicht über den Zugriff auf lokale Dateien verfügen.*

<sup>3</sup> *die Core-Debuggen wird freigegeben, jedoch keine gestarteten Server werden nicht automatisch weitergeleitet.*

<sup>4</sup> *Gäste keine haben eine lokale Kopie der app, und daher die ausgeführte app und alle Debugsitzungen, auf dem Computer des Hosts zu starten.*

<sup>5</sup> *die Ausgabe eines Testlaufs müsste, dass alle sich ergebenden Terminals, Ausgabebereiche und Fehler auch für Gäste freigegeben wurden.*

<sup>6</sup> *Verwenden dieser Node.js `fs` Modul direkt auf Dateien zu erstellen, die funktionieren würde.*

### <a name="visual-studio"></a>Visual Studio

Demnächst.

## <a name="known-issues"></a>Bekannte Probleme

Im folgenden sind aktuell bekannte Erweiterung Probleme, die können verhindern, dass diese Arbeiten für Gäste innerhalb des Kontexts einer zusammenarbeitssitzung (zusammen mit deren umgehungen aufgelistet), und daher können Workflow auswirken:

### <a name="visual-studio-code"></a>Visual Studio Code

| Problem | Grund | Problemumgehung |
|-|-|-|
| Verwenden das Node.js `fs` Modul erkennen/lesen-Dateien (z. B. eine Config-Datei) oder das Auflisten von Verzeichnissen (und Sie keinen Sprachdienst). | Gäste, die Zugriff auf lokale Dateien haben keine. | 1. Die Benutzeroberfläche Ihre Anforderungen ordnungsgemäß herabstufen *(sofern möglich).*<br /><br />2. Verwenden der `openTextDocument` und `findFiles` Arbeitsbereich-APIs zum Lesen und Auflisten von Dateien. |
| Verwenden das Node.js `fs` Modul zu erstellen oder Schreiben von Dateien | *Wie oben* | *N/v* können Sie die `openTextDocument(Uri)` -API zum Erstellen einer `untitled` -Datei, aber Sie können nicht gespeichert werden sie direkt in das Dateisystem, in einem bestimmten Pfad. |
| Abhängig von einer Bibliothek gebündelt mit dem Projekt oder einem tool | *Wie oben* | 1. Bündeln Sie eine alternative Version der Abhängigkeit mit der Erweiterung<br><br> 2. Unterstützt globale Installation, die Gäste zu entsperren, wenn sie ihn ausdrücklich installieren möchten.<br><br> 3. Remote-der Status/Aktion, wenn möglich, da der Host die richtigen Abhängigkeiten verfügbar aufweisen würden. |
| Verwenden das Node.js `fs` Modul zum Erstellen eines Verzeichnisses | *Wie oben* | *N/V* |
| Einschränken von Funktionen für Dokumente, verwenden die `file` Schema. | Dateien für das Gastbetriebssystem Seite Verwendung die `vsls` Schema. | Hinzufügen von Unterstützung für `vsls` Dokumente ([Beispiel](https://github.com/CoenraadS/BracketPair/pull/73)) |
| Mithilfe der `Uri.file` Methode bzw. `Uri.fsPath` / `TextDocument.fileName` Member beim Serialisieren und Analysieren von URIs | *Wie oben* | Verwendung `Uri.parse` und `Url.toString()` stattdessen die verwalten, und berücksichtigen Sie die Datei-Schemas ([Beispiel](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Mithilfe der `workspace.openTextDocument` -Methode mit einem Dateipfad anstelle von einem `Uri` | *Wie oben* | Geben Sie einen `Uri` Instanz statt mit einer Rohdatendatei-Pfadzeichenfolge ([Beispiel](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Mithilfe der `workspace.rootPath` Eigenschaft zum Erkennen des Vorhandenseins eines Arbeitsbereichs | Die `workspace.rootPath` eigenschaftsaufrufen `Uri.fsPath` auf der ersten `workspaceFolder` in die `workspace`, die über das gleiche Problem mit dem oben genannten verfügt | Verwenden der `workspace.workspaceFolders` Eigenschaft, um das Vorhandensein eines Arbeitsbereichs stattdessen erkennen und bei Bedarf betrachten `workspaceFolder`des `Uri.scheme` zu bestimmen, ob sie lokal oder nicht ist |
| Ein Dokument-Schema nicht angeben, wenn Sie Sprachdienste registrieren (entweder über eine `LanguageClient`, oder die `languages.register*` Methoden) | Gäste erhalten die Language-Service-Ergebnisse aus ihrer lokalen Erweiterungen und dem Host, und daher, wenn beide Teilnehmer die gleiche Sprache-Service-Erweiterung installiert haben, Gäste sehen doppelte Einträge für bestimmte Vorgänge (z. B. automatische Vervollständigung, code Aktionen) | Beschränken Sie die Sprachdienste nur `file` und `untitled` Schemas ([Beispiel](https://github.com/vuejs/vetur/pull/756/files)) |
| Keine Überprüfung des Dokuments `Uri.scheme` vor dem Auffüllen einer `DiagnosticCollection` dafür | *Wie oben* | Generieren Sie nur `Diagnostics` für `documents` , deren `Uri.scheme`  ===  `file` ([Beispiel](https://github.com/Huachao/vscode-restclient/pull/196)) |
| Keine Überprüfung für Arbeitsbereich Schema, bei der Rückgabe `Tasks` aus einem benutzerdefinierten `TaskProvider`  | Gäste alle lokale und remote-Aufgaben anzeigen und aus diesem Grund würde Duplikate angezeigt, wenn beide Teilnehmer Erweiterung installiert haben  | Nur zurückgeben `Tasks` für `WorkspaceFolder`s, dessen `Uri.scheme`  ===  `file` ([Beispiel](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

Demnächst.

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

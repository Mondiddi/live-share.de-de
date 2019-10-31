---
title: Unterstützung für Plattformen und Sprachen-Visual Studio Live Share | Microsoft-Dokumentation
description: Eine Übersicht über die Platt Form-und Sprachunterstützung für die Visual Studio-Live Freigabe.
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
ms.openlocfilehash: 386a8204787ed378413e1b35b7c2a80e0de678ce
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170086"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Sprach- und Plattformunterstützung

Die Funktionen von Visual Studio Live Share sind für die Verwendung in einer Vielzahl von Sprachen und Anwendungsplattformen vorgesehen. Allerdings sind einige Plattformen und Sprachen aufgrund der reinen Anzahl von Variationen besser als andere Plattformen und Sprachen. In diesem Dokument wird der aktuelle bekannte Zustand einer Reihe beliebter Sprachen und Plattformen für derzeit unterstützte Funktionen behandelt.

Sie benötigen eine Sprache oder Plattform, die Sie benötigen? Möchten Sie eine hinzufügen, die Sie nicht sehen? [Stimmen Sie hier ab.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Alle Sprachen/Plattformen verfügen über die gleiche Datei IntelliSense (wenn die jeweilige Erweiterung installiert ist) sowie Unterstützung für farbliche und Co-Bearbeitung. In der folgenden Liste werden erweiterte Features behandelt, die derzeit ohne umfassende universelle Unterstützung sind:

### <a name="languages"></a>Sprachen

| Sprache | Freigegebene Sprachdienste | Frei gegebenes Debugging |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *nicht zutreffend* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | Nicht zutreffend <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | Nicht zutreffend <sup>4</sup> |
| [SAP](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | Nicht zutreffend <sup>4</sup> |
| CSHTML | *N/v* <sup>1</sup> | ✅ |
| CSS | *nicht zutreffend* | *nicht zutreffend* |
| Darts | ✅ | ✅ |
| Docker | ✅ | *nicht zutreffend* |
| Elixir | ✅ | ✅ |
| Elfmeter | ✅ |  Nicht zutreffend <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  Nicht zutreffend <sup>4</sup> |
| Fluss | ✅ |  Nicht zutreffend <sup>4</sup> |
| Fortran | ✅ | *nicht zutreffend* |
| Gehe zu | ✅ | ✅ |
| Gradle | ✅ | Nicht zutreffend <sup>4</sup> |
| Graphql | ✅ | Nicht zutreffend <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *nicht zutreffend* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/typescript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | Nicht zutreffend <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *nicht zutreffend* | Nicht zutreffend <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *nicht zutreffend* |
| MATLAB |  ✅ | Nicht zutreffend <sup>4</sup> |
| Objective-C | ✅ | Nicht zutreffend <sup>4</sup> |
| Pas | ✅ | Nicht zutreffend <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *nicht zutreffend* | ✅ |
| Python |  ✅ | ✅ |
| Purescript | ✅ | Nicht zutreffend <sup>4</sup> |
| R |  ✅ | Nicht zutreffend <sup>4</sup> |
| [Grund/ocaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | Nicht zutreffend <sup>4</sup> |
| Umstrukturierung Text | ✅ | *nicht zutreffend* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | Nicht zutreffend <sup>4</sup> |
| [Beschäftigte](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *nicht zutreffend* |
| AS | ✅ | Nicht zutreffend <sup>4</sup> |
| Solidity | ✅ | Nicht zutreffend <sup>4</sup> |
| SQL/T-SQL | *nicht zutreffend* | Nicht zutreffend <sup>4</sup> |
| [Stift](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *nicht zutreffend* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | Nicht zutreffend <sup>4</sup> |
| Swift | ✅ | Nicht zutreffend <sup>4</sup> |
| TERRAFORM | ✅ | Nicht zutreffend <sup>4</sup> |
| XML | ✅ | Nicht zutreffend <sup>4</sup> |
| YAML | ✅ | Nicht zutreffend <sup>4</sup> |

<sup>1</sup> keine cshtml-unter C# Stützung in der Erweiterung.<br />
<sup>2</sup> eingebettetes Javascript in HTML wird beim Debuggen von Clients unterstützt.<br />
<sup>3</sup> JavaScript/typescript-Debuggen für Knoten oder Browser.<br />
<sup>4</sup> die entsprechende Erweiterung für vs Code unterstützt derzeit nicht das Debuggen. Sobald dies der Fall ist, wird das Hinzufügen von Co-Debugging-Unterstützung untersucht. <br />

### <a name="platforms"></a>Plattformen

| App-/Plattformtyp | Frei gegebenes Debugging | App-Freigabe |
|-------------------|--------------|-------------|
| Arduino | ✅ | *nicht zutreffend* |
| Azure App Service | ✅ | *nicht zutreffend* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (lokal und Remote) | ✅ | ✅ <sup>1</sup> |
| Blockchain (ethereum) | ✅ | ✅ <sup>1</sup> |
| Konsole/CLI | ✅ | ✅ <sup>4</sup> |
| Databases | <sup>5</sup> | ✅ <sup>1</sup> |
| Desktop (Elektronen/System eigen) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Spiele (Unity) | ✅ | <sup>9</sup> |
| Spiele (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *nicht zutreffend* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1, 7</sup> |
| Mobile (System eigen) | ✅ | <sup>9</sup> |
| Mobile (systemeigene Reaktion) | ✅ | ✅ <sup>1, 8</sup> |
| Web-App/API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Web-App (Front-End) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code Erweiterungen | | <sup>9</sup> |

<sup>1</sup> über [Freigeben des lokalen Servers](../how-to-guides/vscode.md#share-a-server).<br />
<sup>2</sup> das Debuggen erfolgt im Browser des Hosts anstelle von "Gast".<br />
<sup>3</sup> durch Freigeben von Back-End.<br />
<sup>4</sup> unterstützt durch freigegebene Terminals.<br />
<sup>5</sup> gespeicherte Prozeduren für das Debuggen <br />
<sup>6</sup> über "Vorschau". Images werden jedoch aufgrund eines bekannten Problems nicht angezeigt. [Stimmen Sie (👍) hier ab.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova-Apps können über die Plattform "Browser" freigegeben werden.<br />
<sup>8</sup> reagieren Sie auf native Apps können über die Expo und frei [gegebene Server](../how-to-guides/vscode.md#share-a-server)freigegeben werden.<br />
<sup>9</sup> Live Share unterstützt derzeit nicht die Freigabe von Fenstern/Bildschirmen. [Stimmen Sie (👍) hier ab.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Obwohl die meisten Sprachen einige IntelliSense-Unterstützung für einzelne Dateien aufweisen, gibt es einige Einschränkungen, die im folgenden beschrieben werden. Alle Sprachen/Plattformen unterstützen die Co-Bearbeitung. Der Rest der Liste umfasst erweiterte Features, die derzeit ohne umfassende universelle Unterstützung sind:

### <a name="languages"></a>Sprachen

| Sprache | Sprachdienste für einzelne Dateien | Projekt weite Sprachdienste | Kodebuggen |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅<sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *nicht zutreffend* | <sup>2</sup> |
| CSS | ✅ | *nicht zutreffend* | *nicht zutreffend* |
| JavaScript/typescript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *nicht zutreffend* | *nicht zutreffend* |
| PowerShell | ✅ | *nicht zutreffend* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *nicht zutreffend* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *nicht zutreffend* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *nicht zutreffend* | ✅ |

<sup>1</sup> Lücke: cshtml, vbhtml und aspx haben bekannte Probleme bei der eingebetteten C#/VB Unterstützung von Code-Behind C#/VB-Dateien werden nicht aufgelöst, weil die vollständige IntelliSense-Implementierung nicht implementiert ist. [Stimmen Sie (👍) hier auf cshtml/vbhtml ab.](https://github.com/MicrosoftDocs/live-share/issues/59) [Stimmen Sie (👍) hier unter aspx ab.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> eingebettetes Javascript in HTML wird beim Debuggen von Clients unterstützt.<br />
<sup>3</sup> JavaScript/typescript-Debuggen für Knoten oder Browser.<br />
<sup>4</sup> obwohl das Debuggen von XAML selbst technisch gesehen N/v ist, wird das Debugging von Code Behind unterstützt.<br />
<sup>5</sup> Lücke: R-Sprachdienst Fehler auf der Gastseite bei Join und nach jedem Zeilen Bereich. Wird nicht unterstützt. [Stimmen Sie (👍) hier ab.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plattformen

| App-/Plattformtyp | Gemeinsames Debuggen | App-Freigabe |
|-------------------|--------------|-------------|
| Web-App/API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Web-App (Front-End) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Überprüfung auf | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Databases | <sup>4</sup> | ✅ <sup>5</sup> |
| Konsole/CLI | ✅ | ✅ <sup>6</sup> |
| Desktop (WinForms) | ✅ | |
| Desktop (WPF) | ✅ | |
| Universelle Windows-Plattform | ✅ |  |
| VS-Erweiterungen | ✅ |  |

<sup>1</sup> über [Freigeben des lokalen Servers](../how-to-guides/vs.md#share-a-server). ASP.net Web-Apps können auch die [Automatische Web-App-Freigabe](../how-to-guides/vs.md#automatic-web-app-sharing)verwenden.<br />
<sup>2</sup> das Debuggen erfolgt im Browser des Hosts anstelle von "Gast".<br />
<sup>3</sup> durch Freigeben von Back-End.<br />
<sup>4</sup> gespeicherte Prozeduren für das Debuggen gespeicherter Daten <br />
<sup>5</sup> über [Freigeben des lokalen Servers](../how-to-guides/vs.md#share-a-server). <br />
<sup>6</sup> teilweise unterstützt über freigegebene Terminals.<br />
<sup>?</sup> Noch nicht überprüft.

## <a name="see-also"></a>Siehe auch

- [Unterstützung für Erweiterung](extensions.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

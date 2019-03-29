---
title: Unterstützung der Plattform und Sprache – Visual Studio Live Share | Microsoft-Dokumentation
description: Eine Übersicht über die Plattform und Sprache-Unterstützung für Visual Studio Live Share.
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
ms.openlocfilehash: 91e80df324a0b2f49fdf37a5270cf7b86fca5c7c
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640223"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Sprach-und plattformunterstützung

Visual Studio Live Share Funktionen sollen bunten Vielfalt an Sprachen und Plattformen funktionieren. Jedoch sind die bloße Anzahl von Variationen, einige Plattformen und Sprachen umfassendere als andere. Dieses Dokument behandelt dem aktuellen Zustand einer Reihe von gängigen Sprachen und Plattformen für die derzeit unterstützten Funktionen bezeichnet.

Sehen Sie eine Sprache oder Plattform benötigen Sie? Möchten Sie hinzufügen, die nicht angezeigt? [Hier abstimmen.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Alle Sprachen und Plattformen dieselbe Datei-Intellisense (wenn die jeweilige Erweiterung installiert ist), sowie die farbliche Kennzeichnung und gemeinsam bearbeitungsunterstützung. Die Listen unten sind komplexere Funktionen derzeit ohne vollständige, universelle Unterstützung:

### <a name="languages"></a>Sprachen

| Sprache | Freigegebene Sprachdienste | Freigegebene Debuggen |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/V* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/V* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/V* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/V* <sup>4</sup> |
| CSHTML | *N/V* <sup>1</sup> | ✅ |
| CSS | *N/V* | *N/V* |
| DART | ✅ | ✅ |
| Docker | ✅ | *N/V* |
| Elixir | ✅ | ✅ |
| ELM | ✅ |  *N/V* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/V* <sup>4</sup> |
| Fluss | ✅ |  *N/V* <sup>4</sup> |
| Fortran | ✅ | *N/V* |
| Gehe zu | ✅ | ✅ |
| Gradle | ✅ | *N/V* <sup>4</sup> |
| GraphQL | ✅ | *N/V* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/V* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/V* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/V* | *N/V* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/V* |
| MATLAB |  ✅ | *N/V* <sup>4</sup> |
| Objective-C | ✅ | *N/V* <sup>4</sup> |
| Pascal-Schreibweise | ✅ | *N/V* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/V* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/V* <sup>4</sup> |
| R |  ✅ | *N/V* <sup>4</sup> |
| [Reason/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/V* <sup>4</sup> |
| reStructuredText | ✅ | *N/V* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/V* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/V* |
| Scala | ✅ | *N/V* <sup>4</sup> |
| Solidity | ✅ | *N/V* <sup>4</sup> |
| SQL / T-SQL | *N/V* | *N/V* <sup>4</sup> |
| [Stylus](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/V* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/V* <sup>4</sup> |
| Swift | ✅ | *N/V* <sup>4</sup> |
| Terraform | ✅ | *N/V* <sup>4</sup> |
| XML | ✅ | *N/V* <sup>4</sup> |
| YAML | ✅ | *N/V* <sup>4</sup> |

<sup>1</sup> keine CSHTML-Unterstützung in C# Erweiterung.<br />
<sup>2</sup> eingebetteten JavaScript in HTML-Code wird unterstützt, wenn debugging des Clients durchführen.<br />
<sup>3</sup> JavaScript / TypeScript-Debuggen für Knoten oder den Browser.<br />
<sup>4</sup> die jeweilige Erweiterung für Visual Studio Code unterstützt derzeit keine Debuggen. Sobald dies der Fall, untersuchen wir gemeinsam die debugging-Unterstützung hinzugefügt wird. <br />

### <a name="platforms"></a>Plattformen

| App-Plattform-Typ | Freigegebene Debuggen | App-Freigabe |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/V* |
| Azure App Service | ✅ | *N/V* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure-Funktionen (lokal und Remote) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Konsole / CLI | ✅ | ✅ <sup>4</sup> |
| Databases | <sup>5</sup> | ✅ <sup>1</sup> |
| Desktop (Electron/systemeigen) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Spiele (Unity) | ✅ | <sup>9</sup> |
| Spiele (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/V* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| Mobile (systemeigen) | ✅ | <sup>9</sup> |
| Mobile (React Native) | ✅ | ✅ <sup>1,8</sup> |
| Web-app / API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Web-app (Front-End) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code-Erweiterungen | | <sup>9</sup> |

<sup>1</sup> über [Freigabe lokaler Server](../use/vscode.md#share-a-server).<br />
<sup>2</sup> Debuggen tritt auf, für der Hosts Browser anstatt als Gast.<br />
<sup>3</sup> anhand der Back-End.<br />
<sup>4</sup> über freigegebener Terminals unterstützt.<br />
<sup>5</sup> Datenbank gespeicherte Prozeduren Debuggen wird derzeit nicht unterstützt <br />
<sup>6</sup> über "Preview". Images werden jedoch nicht aufgrund eines bekannten Problems angezeigt. [Stimme (👍) hier.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova-apps können gemeinsam genutzt werden, über die Plattform "Browser"<br />
<sup>8</sup> react Native-apps können gemeinsam genutzt werden, über Expo und [freigegebener Server](../use/vscode.md#share-a-server).<br />
<sup>9</sup> live Share unterstützt derzeit keine Freigabe von Windows-Bildschirme. [Stimme (👍) hier.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Die meisten Sprachen einige Einzeldatei Intellisense-Unterstützung verfügen, es gibt einige Einschränkungen, die unten beschriebenen. Alle Sprachen/Plattformen unterstützen, gleichzeitig bearbeiten. Der Rest der Liste umfasst erweiterte Funktionen derzeit ohne vollständige, universelle Unterstützung:

### <a name="languages"></a>Sprachen

| Sprache | Einzeldatei-Sprachdienste | Projektweite-Sprachdienste | Debuggen von Co |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/V* | <sup>2</sup> |
| CSS | ✅ | *N/V* | *N/V* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/V* | *N/V* |
| PowerShell | ✅ | *N/V* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/V* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *N/V* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/V* | ✅ |

<sup>1</sup> Lücke: ASPX, CSHTML und VBHTML haben Sie eine bekannte Probleme rund um eingebettete C#bereitgestellte Code-Behind-/ VB-Unterstützung C#/VB-Dateien werden nicht aufgelöst, aufgrund der vollständige IntelliSense-Funktionalität nicht implementiert wird. [Stimme (👍) hier auf CSHTML/VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Stimme (👍) hier bei ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> eingebetteten JavaScript in HTML-Code wird unterstützt, wenn debugging des Clients durchführen.<br />
<sup>3</sup> JavaScript / TypeScript-Debuggen für Knoten oder den Browser.<br />
<sup>4</sup> Debuggen von XAML selbst technisch n/v ist, zwar Debuggen von Code-Behind wird unterstützt.<br />
<sup>5</sup> Lücke: R-Sprache-Dienstfehler auf der Gastseite auf die Verknüpfung und nach jeder neue-Zeile. Wird nicht unterstützt. [Stimme (👍) hier.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plattformen

| App-Plattform-Typ | Gemeinsames Debuggen | App-Freigabe |
|-------------------|--------------|-------------|
| Web-app / API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Web-app (Front-End) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Überprüfung auf | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Leerzeichen](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Databases | <sup>4</sup> | ✅ <sup>5</sup> |
| Konsole / CLI | ✅ | ✅ <sup>6</sup> |
| Desktop (WinForms) | ✅ | |
| Desktop (WPF) | ✅ | |
| Universelle Windows-Plattform | ✅ |  |
| VS-Erweiterungen | ✅ |  |

<sup>1</sup> über [Freigabe lokaler Server](../use/vs.md#share-a-server). ASP.NET Web-Apps können Sie auch [automatische Web app-Freigabe](../use/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> Debuggen tritt auf, für der Hosts Browser anstatt als Gast.<br />
<sup>3</sup> anhand der Back-End.<br />
<sup>4</sup> Datenbank gespeicherte Prozeduren Debuggen wird derzeit nicht unterstützt <br />
<sup>5</sup> über [Freigabe lokaler Server](../use/vs.md#share-a-server). <br />
<sup>6</sup> teilweise über freigegebener Terminals unterstützt.<br />
<sup>?</sup> Noch nicht überprüft wurden.

## <a name="see-also"></a>Siehe auch

- [Unterstützung für Erweiterung](extensions.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

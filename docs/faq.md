---
title: FAQ | Microsoft-Dokumentation
description: Häufig gestellte Fragen zu Visual Studio Live share.
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3da327261766ea0aea7ed167059c864100d25da0
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870487"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

## <a name="what-is-live-share"></a>Was ist Live Share?
Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können das aktuelle Projekt sofort (und sicher) freigeben und dann nach Bedarf Debuggingsitzungen, Terminal Instanzen, localhost-Web-Apps und vieles mehr freigeben. Entwickler, die ihren Sitzungen beitreten, erhalten Ihren gesamten Editor-Kontext von Ihrer Umgebung (z. b. Sprachdienste, Debuggen), wodurch sichergestellt wird, dass Sie sofort produktiv zusammenarbeiten können, ohne dass Sie irgendwelche Repositorys Klonen oder sdgt installieren müssen.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Welche Tool Anforderungen gelten für die Verwendung von Live Share?
Die [wichtigsten Funktionen](#what-are-the-core-capabilities-of-live-share) von Live Share werden in den folgenden Tools vollständig unterstützt:

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6 und höher)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

Wir durchlaufen schnell, um auf das Feedback von Benutzern zu reagieren. Dies erfordert, dass wir die Features in Visual Studio und Visual Studio Code nutzen, die nur in den jeweiligen Vorschau-/Insider-Releases verfügbar sind. Wir geben an, welche Features neuere Versionen von vs oder vs Code in der Dokumentation erfordern. Beispielsweise erfordert die Unterstützung für lokale Rückgängig/Wiederholen Visual Studio 2017 15,7 +.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Was sind die wichtigsten Funktionen von Live Share?
Live Share ermöglicht es Ihnen, ihre Codebasis über eine sichere Verbindung für Ihre Teammitglieder freizugeben. Mit Live Share können Sie mehrere Dateien in einem Arbeitsbereich zusammenarbeiten und noch wichtiger ist, Ihre Anwendung mit ihren Teamkollegen zu debuggen. Während der Co-Bearbeitung werden Ihre Bearbeitungen sofort von ihren Teamkollegen eingesehen. Während des Debuggens teilen Sie die gleiche Debugsitzung für Ihre Anwendung. Dies bedeutet, dass Sie und ihre Teamkollegen die Programmausführung mit Breakpoints und Schritten steuern können. Sie können jedoch Variablen, Überwachungen, lokale Elemente und REPLs (z. b. das direkt Fenster in Visual Studio) unabhängig überprüfen.

Live Share verfügt über eine Vielzahl von Anwendungsfällen, wie z. b. die Untersuchung eines Fehlers, der ein Problem anzeigt, das auf dem Computer einer anderen Person nicht wieder verwendet werden kann, die Behebung von Entwurfs Problemen, die Programmierung von Paaren, das Durchführen eines Codierungs Interviews, das betreuen anderer Mitglieder eines Teams oder das Ausführen von Ad-hoc

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Mit Live Share wird mein Code auf einem Microsoft-Server gespeichert?
Nein, der freigegebene Code befindet sich ausschließlich auf dem Computer des Entwicklers, der die Freigabe initiiert hat. Er wird in keiner Weise in die Cloud gespeichert oder hochgeladen. Stattdessen stellt Live Share einfach eine sichere Verbindung zwischen Ihnen und ihren Teamkollegen her (die End-to-End verschlüsselt ist) und keine Daten über den freigegebenen Code überprüft oder sammelt.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>Funktioniert dieses Remote basierte Modell überall? Handelt es sich um einen Peer-to-Peer?
Die einzige Voraussetzung Live Share ist, dass die freigegebene Person und Ihr Teamkollegen über Internetzugang verfügen. Eine sichere Kommunikation zwischen Teammitgliedern während einer Zusammenarbeits Sitzung wird durch ein Azure Relay ermöglicht. Der Arbeitsbereich (d. h. Quelldateien) wird nicht in der Cloud gespeichert. Es ist keine spezielle Peer-to-Peer-Verbindung erforderlich, obwohl eine verwendet werden kann, um die Latenz zu verringern. Weitere Informationen finden Sie unter [Ändern des Verbindungs Modus](https://aka.ms/vsls-docs/connection-mode) in unserer Dokumentation.

## <a name="what-is-shared-during-a-live-share-session"></a>Was wird während einer Live Share Sitzung freigegeben?
Live Share übertragen nicht alle Tastatur-und Maus Eingaben. Die Daten, die für jede Zusammenarbeits Aktivität benötigt werden, werden nur an die Computer Ihrer Teamkollegen übermittelt. Wenn Sie z. b. den Arbeitsbereich freigeben, wird die Ordnerstruktur freigegeben. Wenn Sie eine Datei kollaborativ bearbeiten, wird der Inhalt dieser Datei freigegeben. Wenn Sie gemeinsam Debuggen, werden Debugaktionen (z. b. schrittweise) und Status (z. b

## <a name="when-will-live-share-be-released"></a>Wann werden Live Share freigegeben?
Live Share jetzt allgemein verfügbar! Sie können noch heute [mit Live Share beginnen](https://aka.ms/vsls-start) .

## <a name="how-much-will-it-cost"></a>Wie viel wird das kosten?
Wir haben einen substanziellen kostenlosen Tarif für Visual Studio Live Share für Entwickler bereitgestellt, der fortlaufend verwendet werden soll. Wir werden die Einführung von kostenpflichtigen Tarifen mit erweiterten Features evaluieren, da wir die Anforderungen der Community besser verstehen.

## <a name="how-is-my-code-shared-with-other-teammates"></a>Wie wird mein Code für andere Teamkollegen freigegeben?
Wenn Sie Live Share verwenden, stellen Sie sicher, dass der Code, an dem Sie arbeiten, verfügbar ist, sodass Ihre Teamkollegen über einen sicheren clouddienst darauf zugreifen können, dass Befehle aus dem Editor entfernt werden. Ihre Teamkollegen können die Dateien öffnen und bearbeiten, ohne Sie in der Cloud speichern oder Sie dauerhaft auf dem Computer Ihres Team Diensts speichern zu müssen.

Live Share ermöglicht den sofortigen Zugriff auf Funktionen wie die Projektstruktur, die Code Navigation und die Suche. Außerdem können Ihre Teamkollegen von Editor-Erweiterungen wie IntelliSense profitieren.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>Was geschieht, wenn ein Benutzer offline geschaltet wird oder die Freigabe beendet?
Das Remote Modell erfordert, dass die Entwickler Freigabe über Live Share und ihren Teamkollegen online sein müssen, um eine Verbindung herstellen zu können. Wenn Ihr Teamkollegen versucht, Live Share zu verwenden, wenn Sie offline sind, kann er der Sitzung erst beitreten, wenn Sie wieder online sind. Wenn die Zusammenarbeit beendet wird (z. b. Wenn Sie den Editor schließen, offline schalten oder Freigabe beenden), werden weitere Aktionen oder der Dateizugriff durch ihre Teamkollegen sofort deaktiviert.

## <a name="what-about-screen-sharing"></a>Was ist mit der Bildschirm Freigabe?
Mit Live Share können Sie den Projekt Code und seinen Kontext freigeben. Dies bedeutet, dass Ihr Teamkollegen problemlos in Ihre Codebasis springen und mit Ihnen zusammenarbeiten kann, indem er das vertraute Tool verwendet. Der Editor oder andere apps sind nicht freigegeben oder können von Ihrem Teamkollegen nicht angezeigt werden, und Sie müssen Ihren Arbeitsstil nicht ändern oder eine webbasierte App verwenden.

Live Share ersetzt die Bildschirm Freigabe nicht, wenn Sie ein Menü Element anzeigen oder visuelle Aspekte der APP oder des Editors erörtern möchten. Stattdessen haben Sie die Möglichkeit, Live Share zusammen mit Chat, sprach-, Video-und Bildschirm Freigabe zu verwenden.

## <a name="what-about-other-collaboration-tools"></a>Was ist mit anderen Tools zur Zusammenarbeit?
Live Share können mit Chat-, Instant Messaging-oder e-Mail-Technologien verwendet werden. Wir haben festgestellt, dass in diesen Tools viele Interaktionen zwischen den Entwicklern gestartet werden. Wenn die Diskussion jedoch über Code erfolgt, kommt es häufig zu einem Punkt, an dem es einfach zu schwierig ist, ein Problem mit Text, Code Ausschnitten oder einzelnen Dateien zu erläutern. es ist mehr Kontext erforderlich.

Live Share können für viele Dinge verwendet werden, wie z. b. die Suche nach Hilfe zu einem Problem, das Beheben eines Fehlers, das Koppeln der Programmierung, das Ausführen eines Codierungs Interviews oder das Durchführen einer Ad-hoc-Überprüfung vor einem codecommit oder einer Pull-Anforderung.

## <a name="what-about-other-web-editors"></a>Was ist mit anderen Web-Editoren?
Mit webbasierten Editoren müssen beide Teamkollegen dieselbe Web-App verwenden, um kollaborative Vorteile zu erhalten. Dies ist möglicherweise nicht der primäre, alltägliche Editor. Viele webbasierte Editoren gehen davon aus, dass Sie eine virtuelle Maschine, die häufig in einer cloudumgebung gehostet wird, entwickeln und bereitstellen.

Obwohl dies für viele Szenarien wünschenswert sein kann, möchten Entwickler häufig an apps arbeiten, die nicht auf einem virtuellen Computer oder in der Cloud gehostet werden.  Mit Live Share können Sie und Ihr Teamkollegen zusätzlich zu den Funktionen, die in webbasierten Editoren verfügbar sind, die Funktionen des Ökosystems "Tools" verwenden.

Live Share führt einen Schritt weiter und ermöglicht es Ihnen, eine Debugsitzung freizugeben.  Dies macht es besonders nützlich, wenn Sie andere Personen auflisten, um Probleme zu ermitteln, die nur auf Ihrem Computer auftreten, ohne den Entwicklungs Workflow zu ändern oder den Anwendungs Entwurf ändern zu müssen.

## <a name="which-languages-and-platforms-will-be-supported"></a>Welche Sprachen und Plattformen werden unterstützt?
Unser Ziel besteht darin, die unterschiedlichen Sprachen und Plattformen zu unterstützen, um sicherzustellen, dass wir unabhängig vom entwickelten Anwendungstyp die umfassende Zusammenarbeit aktivieren können. Ausführliche Informationen zu den heute Funktionsweise finden Sie im Artikel zur [Unterstützung von Sprachen und Plattformen](reference/platform-support.md) .

## <a name="how-many-developers-can-join-a-collaboration-session"></a>Wie viele Entwickler können einer Zusammenarbeits Sitzung beitreten?
Wir unterstützen derzeit 30 gleichzeitige Gäste, zusätzlich zum Entwickler, der das Projekt freigibt ("Hosting"). 

## <a name="what-is-the-roadmap"></a>Was ist die Roadmap?
[Hier](https://aka.ms/vsls-issues)können Sie den Satz bekannter Probleme und Roadmap-Elemente anzeigen. Wenn Sie anstelle aller Probleme nur Funktionsanforderungen sehen möchten, finden Sie [hier](https://aka.ms/vsls-feature-requests)Weitere Informationen. Wir empfehlen Ihnen, vorhandene Elemente abzustimmen, neue Featureanforderungen zu stellen und Fehlerberichte zu protokollieren, um uns dabei zu unterstützen, die Richtung des Produkts in die Zukunft zu gestalten.

## <a name="see-also"></a>Weitere Informationen

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

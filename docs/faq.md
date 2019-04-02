---
title: Häufig gestellte Fragen – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Häufig gestellte Fragen zu Visual Studio Live Share ein.
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
ms.openlocfilehash: 1b68dc90f4bac5e21c04c555ab2d8fc7f59aad55
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853598"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen (FAQs)

## <a name="what-is-live-share"></a>Was ist Live Share?
Live Share ermöglicht Ihnen gemeinsames Bearbeiten und Debuggen mit anderen in Echtzeit – unabhängig von Ihren verwendeten Programmiersprachen oder erstellten App-Typen. Sie können sofort (und sicher) des aktuellen Projekts, und klicken Sie dann nach Bedarf, freigeben, Debugsitzungen, Terminaldienste-Instanzen, "localhost"-Web-apps und mehr! Entwickler, die Ihre Sitzungen verknüpfen erhalten Sie alle von ihrem Editor-Kontext aus Ihrer Umgebung (z. B. Language Services, Debuggen), um sicherzustellen, dass sie mit der Zusammenarbeit produktiv sofort, ohne alle Repositorys klonen, oder installieren Sie alle SDKs beginnen können.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Was sind die Tools-Anforderungen für die Verwendung von Live Share?
Die [Kernfunktionen](#what-are-the-core-capabilities-of-live-share) von Live Share werden in der folgenden Tools vollständig unterstützt:

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6+)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

Wir durchlaufen Sie schnell zum Reagieren auf Feedback von Benutzern. Dies erfordert, die Funktionen in Visual Studio nutzen, und Visual Studio-Code, die nur in ihre jeweiligen Vorschau/Insider-Versionen verfügbar sein. Es wird angegeben, welche featureanforderungen aktuellere Versionen von Visual Studio oder Visual Studio Code in der Dokumentation. Lokale Rückgängig/Wiederholen-Unterstützung erfordert z. B. Visual Studio 2017 15.7 und höher.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Was sind die Kernfunktionen von Live Share?
Live Share ermöglicht Ihnen, zu Teilen Ihrer Codebasis mit den Mitgliedern Ihres Teams über eine sichere Verbindung. Klicken Sie mit Live-Freigabe können Sie mehrere Dateien in einem Arbeitsbereich gemeinsam bearbeiten, und weitere vor allem Ihrer Anwendung mit Ihren Teamkollegen Debuggen. Während der Bearbeitung zusammen Ihre Änderungen werden sofort Ihre Teamkollegen sichtbar. Während des Debuggens zusammen werden Sie derselben Debuggingsitzung Ihrer Anwendung frei. Dies bedeutet, dass Sie und Ihre Teamkollegen können die Ausführung des Programms mit Haltepunkten und Schritten steuern, aber Sie können unabhängig voneinander untersuchen, Variablen, Überwachungselemente, lokale Variablen und REPLs (z. B. das Direktfenster in Visual Studio).

Livefreigabe verfügt über eine Vielzahl von Szenarien wie: Untersuchen einen Fehler, ein Problem, das Reproduktion auf Computer mit einer anderen Person wird nicht mit Entwurf zu lösen ausgibt, Paar programmieren, Durchführen einer coding Interview, Anleitung für die anderen Elemente in einem Team oder ausführen Ad-hoc-codeüberprüfungen.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Ist Sie mithilfe von Live Share können eigenen Code, der auf einem Microsoft-Server gespeichert?
Nein, befindet sich der freigegebene Code, ausschließlich auf dem Computer des Entwicklers, der die Freigabe initiiert hat. Es ist nicht gespeichert oder in der Cloud in keiner Weise hochgeladen. Stattdessen Live Share einfach richtet eine sichere Verbindung zwischen Ihnen und Ihren Teamkollegen (die verschlüsselten End-to-End), und nicht zu überprüfen oder Sammeln von Daten auf den Code, der freigegeben wird.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>Funktioniert diese Remote-basiertes Modell anywhere? Handelt es sich um Peer-zu-Peer?
Livefreigabe die einzige Voraussetzung ist, dass die Person, die Freigabe und ihren teamkamerad Zugriff auf das Internet. Sichere Kommunikation zwischen Teammitgliedern während einer zusammenarbeitssitzung wird durch ein Azure Relay genutzt. Arbeitsbereichsversion (d. h. Quelldateien) wird nicht in der Cloud gespeichert. Keine besondere Peer-zu-Peer-Verbindung ist erforderlich, wenn eine verwendet werden kann, die Latenz zu verringern. Finden Sie unter [ändern den Verbindungsmodus](https://aka.ms/vsls-docs/connection-mode) in unserer Dokumentation für zusätzliche Details.

## <a name="what-is-shared-during-a-live-share-session"></a>Was wird bei einer Live Share-Sitzung gemeinsam genutzt?
Alle Eingaben von Tastatur und Maus Livefreigabe nicht übertragen werden. Es kommuniziert nur die Daten für jede Aktivität Zusammenarbeit mit Ihren Teamkollegen Computern erforderlich sind. Z. B. Wenn Sie Ihrem Arbeitsbereich freigeben, wird die Ordnerstruktur gemeinsam genutzt. Wenn Sie gemeinsam eine Datei bearbeiten, dass der Inhalt Datei freigegeben werden. Wenn Sie gemeinsam Debuggen, Debugging-Aktionen (z. B. stepping) und Status (z. B. "Aufrufliste" und "lokal") freigegeben.

## <a name="when-will-live-share-be-released"></a>Wann wird Live Share veröffentlicht?
Livefreigabe ist jetzt allgemein verfügbar! Sie können [erste Schritte mit Live Share](https://aka.ms/vsls-start) noch heute.

## <a name="how-much-will-it-cost"></a>Wie viel kostet es?
Wir sind an substanziellen free-Tarif für Visual Studio Live Share fortlaufend Verwendung zu übergeben. Wir werden die Einführung von kostenpflichtigen Tarifen mit erweiterten Features auswerten werden, wie wir die Anforderungen von der Community besser verstehen.

## <a name="how-is-my-code-shared-with-other-teammates"></a>Wie wird mein Code mit Teamkollegen gemeinsam genutzt?
Wenn Live Share verwenden zu können, machen Sie den Code, die, den Sie auf verfügbaren arbeiten, sodass Ihre Teamkollegen diese über einen sicheren Cloud-Dienst zum Remotes-Befehle über den Editor zugreifen können. Ihre Teamkollegen können öffnen und bearbeiten die Dateien ohne Speichern sie in der Cloud oder dauerhaft auf Ihre Kollegin des Computers zu speichern.

Live Share ermöglicht sofortigen Zugriff auf Funktionen wie die Projektstruktur, codenavigation und Suche. Darüber hinaus können Ihre Teamkollegen-Editor-Erweiterungen wie IntelliSense profitieren.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>Was geschieht, wenn ein Benutzer beendet die Freigabe oder offline geschaltet?
Das remote-Modell erfordert, dass der Entwickler, die Freigabe von Dateien über Live Share und ihre teamkamerad online verbunden sein muss. Wenn Ihre Kollegin versucht, die Live Share verwenden, wenn Sie offline sind, werden sie nicht verknüpfen die Sitzung, bis Sie wieder online sind. Darüber hinaus werden, sobald die Zusammenarbeit beendet wird (z. B. Sie schließen Sie den Editor, in den Offlinemodus wechseln oder Aufheben der Freigabe), klicken Sie dann weiter, Aktionen oder den Zugriff auf Dateien durch Ihre Teamkollegen sofort deaktiviert.

## <a name="what-about-screen-sharing"></a>Wie sieht die Bildschirmfreigabe?
Live Share können Sie den Code Ihres Projekts und der Kontext gemeinsam zu nutzen. Es bedeutet, dass Ihre Kollegin kann problemlos sofort in Ihrer Codebasis gemeinsam mit Ihnen, ihre vertraute Tool zu verwenden. Ihren Editor oder anderen apps sind nicht freigegeben werden oder können durch Ihre Kollegin, und Sie müssen Ihren Arbeitsstil ändern, oder verwenden Sie eine Web-basierte Anwendung.

Livefreigabe ersetzt nicht die Bildschirmfreigabe, in denen möglicherweise möchten Sie ein Menüelement anzeigen oder visuellen Aspekte Ihrer app oder Ihrem Editor erläutert. Stattdessen müssen Sie die Option zum Verwenden von Live Share zusammen mit Chat, Sprach-, Video- und Bildschirmfreigabe.

## <a name="what-about-other-collaboration-tools"></a>Was ist mit anderen Tools zur Zusammenarbeit?
Live-Dateifreigabe kann mit Chat, instant messaging oder e-Mail-Technologien verwendet werden. Wir haben festgestellt, dass viele gemeinsame Interaktionen zwischen Entwicklern in diesen Tools starten. Allerdings wird die Diskussion über Code, sie erhalten oft auf einen Punkt, an dem sie einfach zu schwierig, ein Problem mit Text, Codeausschnitte oder einzelne Dateien - erläutern mehr Kontext erforderlich ist.

Livefreigabe kann für viele Dinge, wie z. B. verwendet werden: Suchen die Hilfe auf ein Problem, und Beheben eines Fehlers Paar programmieren, Durchführen einer coding Interview oder Durchführen einer Ad-hoc-überprüfen Sie, vor dem committen von Code oder eine Pull-Anforderung.

## <a name="what-about-other-web-editors"></a>Was ist mit anderen Web-Editoren?
Mit webbasierten-Editoren einzustellen müssen beide Teamkollegen derselben Web-app zu verwenden, um die Zusammenarbeit, erzielt die möglicherweise nicht ihre primäre täglichen-Editor. Viele webbasierte Editoren wird davon ausgegangen, dass die Erstellung und Bereitstellung in einem virtuellen Computer, die häufig in einer Cloudumgebung gehostet.

Während dies für viele Szenarien wünschenswert sein, möchten Entwickler häufig an apps zu arbeiten, die auf einem virtuellen Computer oder in der Cloud gehostet werden nicht.  Mit Live-Freigabe können Sie und Ihre Kollegin die Funktionen der Tools-Ökosystem, zusätzlich zu den gleichen Funktionen, die in der webbasierten-Editoren verfügbar.

Live-Freigabe geht einen Schritt weiter und ermöglicht es Ihnen, eine Debugsitzung zu teilen.  Dadurch besonders nützlich in anderen, mit denen Sie die Probleme zu ermitteln, der nur auf dem Computer auftreten können, ohne ihre entwicklungsworkflows ändern oder zum Ändern des Anwendungsentwurfs müssen eintragen.

## <a name="which-languages-and-platforms-will-be-supported"></a>Welche Sprachen und Plattformen werden unterstützt?
Unser Ziel ist zur Unterstützung der bunten Vielfalt an Sprachen und Plattformen, um sicherzustellen, dass wir umfassende Zusammenarbeit, unabhängig vom entwickelte Anwendung aktivieren können. Finden Sie unter den [Sprach- und plattformunterstützung](reference/platform-support.md) finden Sie Details dazu, was heute funktioniert.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>Wie viele Entwickler können eine zusammenarbeitssitzung beitreten?
Wir unterstützen derzeit 30 gleichzeitige-Gäste zusätzlich zu den Entwickler, die ("hosting") gemeinsam nutzen, wird ihr Projekt. Aktivieren wir standardmäßig bis zu 5 Gästen in einer Sitzung ein. 

So aktivieren Sie die erhöhte Gast Grenzwert: 
- **Visual Studio Code:** Add "liveshare.increasedGuestLimit":"true" to settings.json.
- **VS:** Legen Sie Extras > Optionen > Live Share > höhere Gast-Grenzwert auf "True"

## <a name="what-is-the-roadmap"></a>Wie sieht die Roadmap?
Sie können den Satz von bekannten Problemen und Roadmap für die Elemente anzeigen [hier](https://aka.ms/vsls-issues). Wenn Sie alle Probleme, anstatt nur Feature-Anforderungen finden Sie unter möchten, finden Sie unter [hier](https://aka.ms/vsls-feature-requests). Wir empfehlen Ihnen, vorhandene Elemente abstimmen, Datei anfordern neuer Features und melden Sie sich die Fehlerberichte, um uns helfen, Form, die Richtung des Produkts für die Zukunft.

## <a name="see-also"></a>Siehe auch

- [Sprach-und plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](reference/security.md)
- [Alle große Fehler, Features und Einschränkungen](https://aka.ms/vsls-issues)
- [Alle Anfragen zu Features und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](troubleshooting.md) oder [Feedback geben](support.md).

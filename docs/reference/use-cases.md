---
title: Gängige Anwendungsfälle – Visual Studio-Livefreigabe | Microsoft-Dokumentation
description: Eine Übersicht über die Anwendungsfälle, denen Entwickler häufig Visual Studio Live Share für nutzen.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2ef982a00a06cb312cd0270ba65abd308518d99e
ms.sourcegitcommit: c20a6ddef4f184678a2d6cf1a2493d42ea3a4356
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2019
ms.locfileid: "57725700"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Gängige Anwendungsfälle

Das primäre Ziel von Visual Studio Live Share ist, damit Entwickler leichter, miteinander zusammenarbeiten, ohne alle Meinung dazu, wann und wie es geht (z. B. welche Tool für die Kommunikation zu verwenden, die "richtige" Software-Methode oder die SCM-Workflow). Auf diese Weise können Ihre Tools Interaktionen, die auftreten unterstützen **auf natürliche Weise**, und als **häufig*je nach Bedarf, aber auf eine Weise, **den empfohlenen*wie Sie bereits arbeiten möchten.

Dieses Dokument-Highlights einige Anwendungsfälle, dass Visual Studio Live Share für die bereits verwendet wird, und es wird beschrieben, wie gut wir unterstützen derzeit diese verwendet wird und wie es ist geplant, diese weiter (basierend auf Feedback!) zu optimieren. Wenn Sie Live Share für etwas, das bereits im folgenden erläutert ist nicht verwenden, oder wenn Sie können wir besser erwägen auf einen bestimmten Anwendungsfall, Sie unterstützen [Teilen Sie uns](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Schnelle Hilfe](#quick-assistance)
    - [Geschäftszeiten](#office-hours)
- [Paarprogrammierung](#pair-programming)
    - [Mob-Programmierung](#mob-programming)
    - [Codieren Wettbewerbe / Hack-A-Thons](#coding-competitions--hack-a-thons)
    - [School-Ressourcengruppenprojekten](#school-group-projects)
    - [Streaming-Entwickler](#developer-streaming)
    - [Erstellen von Prototypen / Project-Einführung](#prototyping--project-inception)
- [Interaktive Schulung](#interactive-education)
    - [Peer-Beratung / Onboarding](#peer-mentoring--onboarding)
    - [Beispielsweise Team](#team-brown-bags)
    - [Classroom Vorlesungen](#classroom-lectures)
- [Codereviews](#code-reviews)
- [Technische Interviews](#technical-interviews)

## <a name="quick-assistance"></a>Schnelle Hilfe

Wenn Sie ein Problem (z. B. versuchen, die einen Fehler, die Einrichtung Ihrer Umgebung zu beheben) ausführen, können Sie Visual Studio Live Share verwenden, um Unterstützung zu erhalten, von einem anderen Peer sofort zu suchen. In vielen Fällen ist es nicht sofort klar welcher Kontext, der die Person, bieten Sie Hilfe benötigen, und somit hilft und es einfach, um Zugriff auf das gesamte Projekt bereitzustellen und If/als erforderliche mit Live-Freigabe inkrementell mehr (z. B. einem lokalen Server, schreibgeschützt Terminaldienste). Nicht erforderlich, um Codeausschnitte und/oder Fehlermeldungen hin und her zu senden!

Darüber hinaus da Live-Freigabe Sie Ihre aktive Debugsitzung, gemeinsam nutzen, ohne dass "Gäste" zum Installieren der erforderlichen Plattformen SDKs (z. B. Node.js, Go, .NET Core), oder tooling-Erweiterungen können, können sie Ihnen helfen, schnellere Lösung zu erhalten, und "nicht verhindern, dass Situationen für die Reproduktion auf meinem Computer". Live Share können Sie nutzen Debugzustand mit anderen Benutzern, für jede Sprache oder Runtime Programmierumgebung (z.B. Kubernetes, React Native-app) und daher unabhängig davon, ob was Sie Hilfe benötigen, Sie sie freigeben können.

### <a name="office-hours"></a>Geschäftszeiten

Viele Unternehmen und Bildungseinrichtungen (USA) (z. B. Schulen, onlineschulungen) bieten Unterstützung für ihre Kunden/Studenten/Mitarbeiter zur vorgegeben, Wiederherstellungszeiten und in der Regel auf eine Wiederholungsrate (z. B. jeden Freitag aus 3-17: 00 Uhr). Auf diese Weise sind "Geschäftszeiten" einfach eine geplante Form der "schnelle Hilfe", im Gegensatz zu vollständig-Ad-hoc-Daten. Livefreigabe erleichtert es, um schnell Hilfe zu erhalten, da die Hilfe für "expertensicht" bereitstellen können sofort beitreten zu einer zusammenarbeitssitzung und Ihre Fragen, beantworten ohne dass Sie ihren Computer überhaupt einrichten müssen.

## <a name="pair-programming"></a>Paarprogrammierung

Eine der am häufigsten Szenarien für Visual Studio Live Share "paarprogrammierung" ist: zwei oder mehr Entwickler, die auf eine freigegebene Aufgabe, mit dem Ziel wissen, was zu höheren Team Kohäsion und potenziell Produktqualität zusammenarbeiten. Die genaue Aussehen und Verhalten der paarprogrammierung kann zwischen einzelnen Teams und Fällen, abhängig von den folgenden (unter anderem) erheblich unterscheiden:

1. Der Bereich von der "Task" wird die Virtualisierungssoftware (z. B. einen Fehler, einer User Story)

1. Die erwartete Dauer der der zusammenarbeitssitzung (z. B. zwei Minuten, einer Stunde Vollzeit, einmal pro Woche, TBD)

1. Die Anzahl der Personen einbezogen werden (z. B. zwei, das gesamte Team)

1. Die Rolle jeder Teilnehmer (z. B. "Driver", / Beobachter-Prüfer, fachlicher Ansprechpartner)

1. Die Nähe der Teilnehmer (z. B. gemeinsam befindet sich im selben Gebäude, auf der ganzen Welt)

Livefreigabe wurde entworfen, um agnostisch für alle oben genannten Probleme, und stattdessen paarprogrammierung unterstützen, die völlig "opportunistische" und für Ihre Situation automatisch werden sollen. Dies bedeutet, dass im Gegensatz zu zwei Entwickler, die gemeinsame Nutzung einer Tastatur und Bildschirm Live Share ermöglicht eine Form der paarprogrammierung, die Entwickler arbeiten, auf eine gemeinsame Ziel verfolgen, ohne ihre einzelnen Autonomie oder Umgebung Einstellungen ermöglicht. Sie können unabhängig voneinander arbeiten oder zusammen, sodass jeder Teilnehmer, schalten Sie ihre eigenen Überlegungen, die Zusammenarbeit.

Weiter unterstützen paarprogrammierung, und jede "Gast" zu häufig benötigten Aktionen ausführen können, haben wir Arbeit geplant stetig des Kontexts und der Funktionen, die in einer Live Share-Sitzung gemeinsam verwendet werden: Aufgaben ([#40](https://github.com/MicrosoftDocs/live-share/issues/40)), Erstellen der Ausgabe ([#48](https://github.com/MicrosoftDocs/live-share/issues/48)), Gast-driven Debuggen ([#32](https://github.com/MicrosoftDocs/live-share/issues/32)), und vieles mehr. Lassen Sie uns wissen Sie, welche dieser Funktionen für Sie wichtig sind!

Um diesen Anwendungsfall noch weiter nach unten zu unterbrechen, stellen die folgenden Elemente Formen der paarprogrammierung, dass wir mithilfe von Live-Freigabe für Personen beobachtet habe dar:

### <a name="mob-programming"></a>Mob-Programmierung

[Mob Programmierung](https://en.wikipedia.org/wiki/Mob_programming) (oder swarm-Programmierung) ist im Wesentlichen Paar programmieren, jedoch mit mehr als zwei Personen. Daher gelten alle die Vorteile von Live Share für paarprogrammierung ebenso wie gut ein. Darüber hinaus werden einige Teams "swarming" im Gegensatz zu Vollzeit auf einen Bedarf (z. B. das Team um erstfall rallying).

Live Share unterstützt derzeit bis zu fünf Gäste innerhalb einer Sitzung, die möglicherweise nicht die Teamgröße Ihres aufzunehmen. Dies ist jedoch etwas wir planen, zu erhöhen (für verschiedene Anwendungsfälle) und auf Feedback suchen ([Stimme 👍 hier](https://github.com/MicrosoftDocs/live-share/issues/229))

### <a name="coding-competitions--hack-a-thons"></a>Codieren Wettbewerbe / Hack-A-Thons

Schreiben von Code Wettbewerbe und Hack-a-Thons sind effektiv kurzfristige, einzelnen Aufgabe Variationen des Mob-Programmierung. Die Mitglieder des Teams und ihrer aktuellen Rolle sind auch potenziell dynamisch. Da in diesem Fall in der Regel auch ZEITEMPFINDLICH ist die Möglichkeit für die Zusammenarbeit in Echtzeit, ohne dass müssen, verwenden ein völlig neues Tool, und die Möglichkeit, die zusammenarbeiten, ohne auf einem einzelnen Bildschirm oder eine Tastatur, beschränkt wird eine Möglichkeit Log in aufsteigender aufgenommen werden kann Geschwindigkeit.

Da die Teilnehmer in dieser Umgebung möglicherweise nicht immer vollständig "vertrauenswürdig", wir haben Anforderungen zu erfahren entfernen (und blockieren) eines Gasts in einer Sitzung zu jedem Zeitpunkt wird besteht, die wir zum Aktivieren der voraussichtlich ([#398](https://github.com/MicrosoftDocs/live-share/issues/398)), und unterstützt Das Ziel für die Bereitstellung von "Hosts" mit vollständiger Kontrolle über ihre Umgebung.

### <a name="school-group-projects"></a>School-Ressourcengruppenprojekten

Gruppiert Projekte enden sieht viel Mob programmieren, in denen mehrere Schüler/Studenten, zusammenarbeiten und kann der Übergang nahtlos zwischen einer einzelnen Aufgabe konzentrieren, oder einzelne Aufgaben gleichzeitig verarbeitet. Anstatt einfach mit Versionskontrolle, um asynchron zusammenarbeiten, können sie Live Share in Echtzeit, zusammenarbeiten verwenden, die soziale Netzwerke und Bildungseinrichtungen Vorteile der Verwendung in einer Gruppe dienen können.

### <a name="developer-streaming"></a>Streaming-Entwickler

Entwickler, die (über twitch integrierte oder Mixer)-streaming ist eine überzeugende neue Form von Bildungseinrichtungen geworden. Beim Live Share ist nicht vorgesehen, ihre Broadcasting-Plattformen (auch wenn die Anforderung schon!) zu ersetzen, bietet jedoch eine Möglichkeit für der Host Paar mit einem oder mehreren Gästen Programm, und Sie anschließend diese Interaktion streamen. Auf diese Weise können Viewer möglicherweise mehr erfahren Sie, indem angezeigt wird, der die natürliche Aktivität und die Denkprozess von zwei oder mehr Entwicklern, sogar vollständig getrennter Betriebssysteme und IDEs, die zusammenarbeiten, werden konnte.

### <a name="prototyping--project-inception"></a>Erstellen von Prototypen / Project-Einführung

Wenn ein Team ein neues Projekt oder in einem Microservice oder ein neues Feature zum Erstellen von Prototypen/zugenommen hat, gestartet wird, kann es oft hilfreich sein, Zusammenarbeit, um eine schnelle Fortschritte, und erkunden neue Ideen. Da der neu bildende Codebasis in einem freigegebenen Repository noch kein Commit ausgeführt werden kann, kann Live Share alle zur Teilnahme an des iterativen Prozess, unabhängig davon, ob, wenn sie im selben Büro oder nicht sind.

## <a name="interactive-education"></a>Interaktive Schulung

Im Allgemeinen versucht Live Share-Entwickler in wissen für ihr Team zu unterstützen. Education ist eine grundlegende Anwendungsfall für Live-Freigabe, und dies besonders gut, indem Sie von jedem Teilnehmer für die Interaktion mit der Codebasis wird, im Gegensatz zu beobachten einfach auf einen Bildschirm zusammengearbeitet zulassen unterstützt. Jeder auf unterschiedliche Weise Besonderheit hat, und daher durch die Bereitstellung Unabhängigkeit von der in "Student", werden sie von der Anweisung angegeben wird, ohne die Fähigkeit, untersuchen ihre eigene Ideen auf dem Weg zu opfern nutzen können.

### <a name="peer-mentoring--onboarding"></a>Peer-Beratung / Onboarding

Wenn einen Entwickler auf einer neuen Codebasis einführen, feature-Bereich, Technologie usw. können Sie sie dem Projekt durchlaufen Live Share (mit `Follow Mode`), sodass sie Sie nachvollziehen können jedoch von ihren eigenen persönlichen IDE. Lässt sich Live Share "Gäste", um das Projekt unabhängig zu navigieren (z. B. eine Datei zu öffnen, das Ausführen von einer `Peek Definition`), sie folgen können zulassen, aber auch, schnelle Suchvorgänge nach Bedarf (z.B.) "Gehofft hatten, was tut diese Funktion?").

### <a name="team-brown-bags"></a>Beispielsweise Team

Team braunen kontextbehälter sind effektiv wie Peer-Beratung, jedoch im Gegensatz zu den Onboarding-support und/oder hilft Ihnen bei der eine bestimmte Aufgabe, die ein ganzes Team, und möglicherweise mehr mit dem Schwerpunkt socializing im Allgemeinen ein nützliches bekannt ist, angezeigt.

### <a name="classroom-lectures"></a>Classroom Vorlesungen

Wenn Dozenten etwas sagen wollen, können sie die Live-Freigabe verwenden, ihr Projekt für Schüler/Studenten, statt einzelner einfach auf ihren Bildschirm freigeben. Dadurch wird die gesamte Klasse zusammen mit der Lehrer befolgen, um das Projekt auf ihren eigenen interagieren. Darüber hinaus kann der Kursleiter einzelne Schüler/Studenten zur Unterstützung bei der Lösung von eines bestimmten Teils der Lektion (z. B. Stellen "Welche Methode sollten wir aufrufen hier?"), die hilfreich sein kann in die gesellschaftlichen Aspekte der-Klasse, ohne physisch anwesend ist, im selben Raum (z. B. Onlinekurse) sein, die Schülern und Studenten in den Vordergrund des Raums Aufwärts oder sogar erfordern.

Hilfestellung bei der Classroom-Einstellungen können Live Share Freigabe im schreibgeschützten Modus. Dozenten können nur-Lese Modus verwenden, damit diese für Schüler/Studenten ihre Projekte freigeben, ohne sich Gedanken unnötige oder versehentliche Änderungen vorgenommen werden können.

Darüber hinaus verfügt Live Share experimentelle Unterstützung für bis zu 30 Gäste, die in einer zusammenarbeitssitzung verknüpfen zu aktivieren. Auf diese Weise können Dozenten haben ihre gesamte Klasse in einer Sitzung beitreten, und zeigen Code gemeinsam haben.

Um diese experimentelle Funktion zu aktivieren:

- **Visual Studio Code:** "Liveshare.features":"experimental" und "Settings.JSON" hinzugefügt.
- **VS:** Legen Sie Extras > Optionen > Live Share > "Experimentell" Funktionen

Um dieses Szenario vollständig Live Share optimieren, müssen wir weiter steigern, die aktuelle Grenze für den Gast ([#229](https://github.com/MicrosoftDocs/live-share/issues/229)), und vereinfachen Sie die Möglichkeit, dass Sitzungen initiiert werden ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Codereviews

PRs sind eine leistungsfähige Möglichkeit zur Zusammenarbeit mit anderen Personen, jedoch in der Regel den Abschluss einer Aufgabe, die (mit Ausnahme von "WIP" Pull Requests) darstellen und der Wunsch, im zusammengeführt. In vielen Fällen das Feedback, das in einem PR vorliegt, kann problemlos erhalten haben weiter oben, und es Wert ist deshalb möglicherweise für Teams, einfach und ohne Unterbrechungen Tipps von Kollegen, im Gegensatz zu warten, bis sie eine Aufgabe zu Fragen "complete" zu suchen.

Da Live-Freigabe sofort das Projekt für andere Benutzer freigeben können, können sie verwendet werden, um "informelle" aktivieren / Ad-hoc-codeüberprüfungen, werden nicht aufgefordert, um Hilfe zu erhalten, Sie einfach Eingabe, um sicherzustellen, dass Ihre Richtung bzw. Ansatz sehr für andere Benutzer ausgerichtet. Dadurch können potenziell in der nachfolgenden Pull Requests schneller abgeschlossen ist, und auf jeden Fall entwicklungsprofis können Kenntnisse innerhalb des Teams.

Darüber hinaus, da Live-Freigabe auf einem beliebigen Verzeichnis gemeinsam nutzen können, können Sie sie zum Ausführen von codereviews, auch wenn Sie Versionskontrolle (obwohl Sie sollte!) zurzeit nicht verwenden, oder wenn Ihr Team PRs (z. B. nicht verwendet Sie verwenden "Trunk" basierende Entwicklung).

Livefreigabe freigeben nicht gerade Source Control Unterschiede, dies ist ein wichtiger Teil des Kontexts, wenn es sich bei codereviews verwendet. Dies ist unsere Roadmap und Priorität Feedback ist uns wichtig ([Stimme 👍 hier](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Technische Interviews

Bei Kandidaten für eine Developer-Position Befragung zu können, kann es oft hilfreich sein Whiteboard Diskussionen hinausgehen und stattdessen beobachten sie die Lösung ein Problem bei der codeerstellung aus einer tatsächlichen IDE (insbesondere dann, wenn Ihr Team/Ihre Organisation "auf einem Tool standardisiert wurde", Möchten sie verwenden, finden Sie unter). Dadurch nicht nur erhalten sie den Vorteil, dass arbeiten auf eine Weise, die möglicherweise natürlicher/angenehmer (die meisten Entwickler nicht code bei Bedarf auf Whiteboards!), aber darüber hinaus erhalten sie unmittelbar Feedback/Unterstützung bei der Arbeit (z. B. Buildfehler, Intellisense). In vielen Fällen ist es wichtiger zu des Kandidaten-Denkprozess, im Gegensatz zu ihrer Fähigkeit, die genaue Syntax bzw. API-Namen zu merken. Auf diese Weise bietet Live Share eine Erfahrung, die ähnlich wie eine paarprogrammierung, Sitzung, jedoch kann die Teilnehmer in einer eigenen Umgebung (einschließlich der betriebssystemeinstellungen, wie etwa der Barrierefreiheit) und genauso funktioniert auch für lokale oder remote Interviews.

Darüber hinaus ist die realen Entwicklung mehr als nur Code schreiben. Da Live Share auch freigegebene Debuggen, Aufgaben und Terminals unterstützt, können Personen zum Beobachten von Kandidaten bei der Diagnose eines Problems, und stellen sie die geeigneten Tools erforderlich, um das (z. B. Schritt Debuggen, Ausführen von Tests) Problem zu beheben. Da alle von dem Computer des Hosts Remote ist, können Kandidaten schnell in die Umgebung"Interview" wechseln, ohne ihren Computer (über das Installieren von Live Share) einrichten. Teams können klicken Sie dann verwalten Sie ein Repository mit freigegebenen apps Befragung (oder ihren tatsächlichen Product Codebasis verwenden), die geklont und Kandidaten freigegeben, indem einfach die URL der Sitzung vor der einzelnen Interviews senden konnte.

## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)
- [Alle große Fehler, Features und Einschränkungen](https://aka.ms/vsls-issues)
- [Alle Anfragen zu Features und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

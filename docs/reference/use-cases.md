---
title: 'Gängige Anwendungsfälle: Visual Studio Live Share | Microsoft-Dokumentation'
description: Eine Übersicht über die Anwendungsfälle, für die Entwickler im allgemeinen Visual Studio Live share nutzen.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d328ad39b35ae1c6338825848857342765418d9
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019826"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Gängige Anwendungsfälle

Das primäre Ziel von Visual Studio Live Share besteht darin, Entwicklern die gemeinsame Zusammenarbeit zu ermöglichen, ohne dass Sie sich über den Zeitpunkt und die Vorgehensweise (z. b. das zu verwendende Kommunikations Tool, die "richtige" Software Methodik oder den SCM-Workflow) vorstellen müssen. Auf diese Weise können Ihre Tools Interaktionen unterstützen, die auf **natürliche**Weise und so **oft** wie nötig auftreten, aber auf eine Weise, die die Funktions **Weise der Arbeit** vor sich zieht.

In diesem Dokument werden einige Anwendungsfälle hervorgehoben, für die Visual Studio Live Share bereits verwendet wird, und es wird beschrieben, wie gut diese derzeit unterstützt werden und wie wir diese weiter optimieren möchten (basierend auf Feedback!). Wenn Sie Live Share für etwas verwenden, das nicht bereits unten behandelt wird, oder wenn Sie der Ansicht sind, dass wir einen bestimmten Anwendungsfall besser unterstützen, informieren Sie [uns](https://github.com/MicrosoftDocs/live-share/issues/new)bitte.

- [Schnelle Unterstützung](#quick-assistance)
    - [Bürostunden](#office-hours)
- [Paarprogrammierung](#pair-programming)
    - [Mob-Programmierung](#mob-programming)
    - [Programmieren von Wettbewerben/Hack-A-THONS](#coding-competitions--hack-a-thons)
    - [Schulgruppen Projekte](#school-group-projects)
    - [Entwickler Streaming](#developer-streaming)
    - [Prototyperstellung/Projekt Anfang](#prototyping--project-inception)
- [Interaktives Education](#interactive-education)
    - [Peer-Mentoring/Onboarding](#peer-mentoring--onboarding)
    - [Team braune Taschen](#team-brown-bags)
    - [Classroom-Vorlesungen](#classroom-lectures)
- [Code Reviews](#code-reviews)
- [Technische Interviews](#technical-interviews)

## <a name="quick-assistance"></a>Schnelle Unterstützung

Wenn Sie auf ein Problem stoßen (z. b. den Versuch, einen Fehler zu beheben, die Umgebung einrichten), können Sie Visual Studio Live Share verwenden, um umgehend Unterstützung von einem anderen Peer zu suchen. In vielen Fällen ist es nicht sofort klar, welcher Kontext von der Person, die Hilfe bereitstellt, benötigt wird, und Live Share dadurch erleichtert, den Zugriff auf das gesamte Projekt bereitzustellen. Wenn/bei Bedarf, werden mehr (z. b. ein lokaler Server schreibgeschützt) weitergegeben. Terminal). Es ist nicht erforderlich, Code Ausschnitte und/oder Fehlermeldungen hin-und herzusenden.

Da Live Share Ihnen außerdem die Freigabe ihrer aktiven Debugsitzung ermöglicht, ohne dass "Gäste" die erforderlichen Plattformen (z. b. Node. js, go, .net Core) oder die Tool Erweiterungen installieren müssen, können Sie die Auflösung schneller erreichen und verhindern, dass "nicht "Reproduktion" auf meinem Computer. Mit Live Share können Sie den Debugzustand für andere Programmiersprachen oder Laufzeitumgebungen (z. b. Kubernetes, systemeigene APP) freigeben. unabhängig davon, welche Hilfe Sie benötigen, können Sie Sie freigeben!

### <a name="office-hours"></a>Bürostunden

Viele Unternehmen und Bildungseinrichtungen (z. b. Schulen, Online Schulungskurse) unterstützen Ihre Kunden/Mitarbeiter/Studenten zu vordefinierten Zeiten und in der Regel in regelmäßigen Abständen (z. b. jeden Freitag von 3-5 Uhr). Auf diese Weise sind "Office-Stunden" einfach eine geplante Form der "schnellen Unterstützung", anstatt vollständig Ad-hoc zu sein. Mit Live Share können Sie schnell Hilfe erhalten, da der "Experte", der Hilfe bietet, sofort einer Zusammenarbeits Sitzung beitreten und Ihre Fragen beantworten kann, ohne dass der Computer überhaupt eingerichtet werden muss.

## <a name="pair-programming"></a>Paarprogrammierung

Eines der am häufigsten verwendeten Szenarios für Visual Studio Live Share ist die "Kombination von Programmierung": zwei oder mehr Entwickler, die zusammen an einer gemeinsam genutzten Aufgabe arbeiten, mit dem Ziel, wissen zu teilen, das Team in Bezug auf das Team und potenziell die Produktqualität zu verbessern. Das genaue Erscheinungsbild der Paarprogrammierung kann sich zwischen Teams und Situationen erheblich unterscheiden, abhängig von den folgenden (u.a.):

1. Der Gültigkeitsbereich der Aufgabe, an der gearbeitet wird (z. b. ein Fehler, ein User Story).

1. Die erwartete Dauer der Zusammenarbeits Sitzung (z. b. zwei Minuten, eine Stunde, voll Zeit, einmal pro Woche, TBD)

1. Die Anzahl der beteiligten Personen (z. b. zwei, das gesamte Team)

1. Die Rolle jedes Teilnehmers (z. b. "Driver", Observer/Reviewer, subject-Experte)

1. Die Nähe der Teilnehmer (z. b. zusammen mit dem gleichen Gebäude auf der ganzen Welt)

Live Share wurde für alle oben genannten Aspekte agnostisch entwickelt und versucht stattdessen, die Paarprogrammierung zu unterstützen, die vollständig "opportunistisch" ist und ihrer Situation gerecht wird. Anders als bei zwei Entwicklern, die eine einzige Tastatur und einen Bildschirm nutzen, Live Share eine Form der Paarprogrammierung ermöglicht, mit der Entwickler an einem gemeinsamen Ziel arbeiten können, ohne Ihre individuellen Autonomie-oder Umgebungseinstellungen zu entfernen. Sie können unabhängig voneinander arbeiten oder zusammenarbeiten, sodass jeder Teilnehmer seinen eigenen Denkprozess in die Zusammenarbeit bringen kann.

Um diesen Anwendungsfall noch weiter zu unterbrechen, stellen die folgenden Elemente Formen der Paarprogrammierung dar, die von den Benutzern beobachtet wurden, die Live Share für Folgendes verwenden:

### <a name="mob-programming"></a>Mob-Programmierung

Die [Mob](https://en.wikipedia.org/wiki/Mob_programming) -Programmierung (oder Swarm-Programmierung) ist im wesentlichen Paarprogrammierung, aber mit mehr als zwei Personen. Daher gelten alle Vorteile von Live Share für die Paarprogrammierung ebenfalls gleichermaßen. Darüber hinaus werden einige Teams nach Bedarf (z. b. das Team, das eine Feuer Übung auslöst) im Gegensatz zur voll Zeitänderung durchführen.

Derzeit werden von Live Share bis zu 30 Gäste innerhalb einer Sitzung unterstützt.
> [!TIP]
> So aktivieren Sie 30 Gäste in einer Sitzung:
> - **Vs Code:** "LiveShare. ereguestlimit": "true" zu "Settings. JSON" hinzufügen
> - Im **Vergleich zu:** Legen Sie Extras > Optionen > Live Share > höheres Gast Limit auf "true" fest. 

### <a name="coding-competitions--hack-a-thons"></a>Programmieren von Wettbewerben/Hack-A-THONS

Codierungs Wettbewerbe und Hack-a-THONS sind praktisch kurzfristige, einzelne Aufgaben Variationen der Mob-Programmierung. Die Mitglieder des Teams und Ihre aktuelle Rolle sind ebenfalls potenziell dynamisch. Da dieser Anwendungsfall in der Regel auch Zeit empfindlich ist, kann die Möglichkeit der Zusammenarbeit in Echtzeit, ohne dass ein völlig neues Tool übernommen werden muss, und die Möglichkeit zur Zusammenarbeit, ohne auf einen Bildschirm oder eine Tastatur beschränkt zu sein, bei steigender Ausführung ein Protokoll sein. End.

Da die Teilnehmer in dieser Umgebung nicht immer vollständig "vertrauenswürdig" sind, können Sie einen Gast jederzeit aus einer Sitzung entfernen (und blockieren). Dadurch wird "Hosts" mit der vollen Kontrolle über Ihre Umgebung bereitgestellt.

### <a name="school-group-projects"></a>Schulgruppen Projekte

Gruppen Projekte sehen sich sehr ähnlich wie die Mob-Programmierung an, bei der mehrere Schüler und Studenten zusammenarbeiten und nahtlos zwischen dem Fokus auf eine einzelne Aufgabe und der gleichzeitigen Arbeit an separaten Aufgaben wechseln können. Anstatt sich einfach auf die Versionskontrolle zu verlassen, um asynchron zusammenzuarbeiten, können Sie Live Share verwenden, um in Echtzeit zusammenzuarbeiten, was den sozialen und pädagogischen Vorteilen der Arbeit in einer Gruppe helfen kann.

### <a name="developer-streaming"></a>Entwickler Streaming

Entwickler Streaming (über Twitch oder Mixer) ist eine überzeugende neue Form der Bildung. Obwohl Live Share nicht dazu gedacht ist, ihre Übertragungsplattformen zu ersetzen (obwohl wir die Anforderung gehört haben!), bietet es dem Host eine Möglichkeit, das Programm mit einem oder mehreren Gästen zu koppeln und dann diese Interaktion zu streamen. Auf diese Weise können Betrachter vielleicht mehr lernen, indem Sie die natürliche Interaktion und den Denkprozess von zwei oder mehr Entwicklern sehen, die sogar in vollständig separaten Betriebssystemen und IDES arbeiten könnten!

### <a name="prototyping--project-inception"></a>Prototyperstellung/Projekt Anfang

Wenn ein Team ein neues Projekt bzw. einen neuen-Webdienst startet oder ein neues Feature erstellt bzw. ein neues Feature erstellt, kann es häufig hilfreich sein, zusammen zusammenzuarbeiten, um einen schnellen Fortschritt zu erreichen und neue Ideen zu erforschen. Da die neu zu erstellende Codebasis möglicherweise noch nicht in ein frei gegebenes Repository übertragen wird, ermöglicht Live Share allen Benutzern die Teilnahme am iterativen Prozess, unabhängig davon, ob Sie sich im selben Büro befinden oder nicht.

## <a name="interactive-education"></a>Interaktives Education

Im Allgemeinen ist Live Share bestrebt, Entwicklern bei der Freigabe von Kenntnissen in Ihrem Team zu helfen. Education ist ein grundlegender Anwendungsfall für Live Share und unterstützt dies besonders gut, da jeder Teilnehmer mit der Codebasis interagieren kann, an der gearbeitet wird, anstatt einfach einen Bildschirm anzusehen. Jeder lernt auf unterschiedliche Weise, und durch die Bereitstellung von Unabhängigkeit für einen "Student" können die Benutzer die angegebene Anweisung nutzen, ohne Ihre Fähigkeit zum Kennenlernen ihrer eigenen Ideen zu opfern.

### <a name="peer-mentoring--onboarding"></a>Peer-Mentoring/Onboarding

Bei der Einführung eines Entwicklers in eine neue CodeBase, einen Funktionsbereich, eine Technologie usw. können Sie Live Share verwenden, um Sie durch das Projekt zu durchlaufen (mit `Follow Mode`), sodass Sie sie zusammen mit Ihnen, aber von ihrer eigenen persönlichen IDE aus verfolgen können. Da Live Share die "Gäste" die unabhängige Navigation im Projekt ermöglicht (z. b. das Öffnen einer Datei, die Durchführung einer `Peek Definition`), können Sie die Option "zulassen" befolgen, aber auch bei Bedarf schnelle Suchvorgänge durchführen (z. b. "Hmm", was funktioniert diese Funktion?).

### <a name="team-brown-bags"></a>Team braune Taschen

Team braune Behälter sind effektiv wie peermentate, werden jedoch einem ganzen Team präsentiert und können sich möglicherweise stärker auf die Sozialisierung von allgemein nützlichen Kenntnissen konzentrieren, im Gegensatz zum Onboarding-Support und/oder bei der Unterstützung einer bestimmten Aufgabe.

### <a name="classroom-lectures"></a>Classroom-Vorlesungen

Wenn Dozenten eine Lektion unterrichten, können Sie Live Share verwenden, um Ihr Projekt für Schüler und Studenten freizugeben, anstatt einfach den Bildschirm zu präsentieren. Dadurch kann die gesamte Klasse zusammen mit dem Lehrer befolgt werden, während Sie gleichzeitig mit dem Projekt interagieren kann. Außerdem kann der Lehrkräfte einzelne Schüler/Studenten bitten, einen bestimmten Teil der Lektion zu lösen (z. b. "welche Methode soll hier aufgerufen werden?"), was bei sozialen Aspekten der Klasse hilfreich sein kann, ohne dass die Schüler/Studenten in den Vordergrund gehen müssen. oder sogar physisch im gleichen Raum (z. b. Onlinekurse) vorhanden sein.

Zur Unterstützung der Classroom-Einstellungen Live Share die Freigabe im schreibgeschützten Modus aktiviert. Dozenten können den schreibgeschützten Modus verwenden, damit Sie Ihre Projekte für Schüler und Studenten freigeben können, ohne sich Gedanken über unnötige oder versehentliche Änderungen machen zu müssen.

Außerdem bietet Live Share Unterstützung für die Aktivierung von bis zu 30 Gästen, die einer Zusammenarbeits Sitzung beitreten. Auf diese Weise können Dozenten die gesamte Klasse in eine Sitzung einbinden und Code zusammen anzeigen.

So aktivieren Sie dieses Feature:

- **Vs Code:** Fügen Sie "LiveShare. ereguestlimit": "true" zu "Settings. JSON" hinzu.
- Im **Vergleich zu:** Legen Sie Extras > Optionen > Live Share > höheres Gast Limit auf "true" fest.

Um Live Share für dieses Szenario vollständig zu optimieren, müssen wir die Art und Weise vereinfachen, in der Sitzungen initiiert werden ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Code Reviews

PRS sind eine leistungsstarke Möglichkeit, mit anderen zusammenzuarbeiten, aber in der Regel den Abschluss einer Aufgabe (mit Ausnahme von "WIP"-PRS) und den Wunsch, Sie in zusammenzuführen. Häufig könnte das Feedback, das in einem PR gegeben wurde, schon früher festgestellt werden, und es ist möglich, dass Teams auf einfache und kontinuierliche Weise Ratschläge von ihren Peers suchen können, anstatt zu warten, bis Sie eine zu suchende Aufgabe "abgeschlossen" haben.

Da Live share es Ihnen ermöglicht, das Projekt sofort für andere freizugeben, kann es verwendet werden, um "informelle"/Ad-hoc-Code Überprüfungen zu aktivieren, in denen Sie anstelle von Hilfe nur Eingaben suchen, um sicherzustellen, dass Ihre Richtung und/oder Ihr Ansatz mit anderen in Einklang steht. Dies kann dazu führen, dass nachfolgende PRS schneller ausgeführt werden können

Da Live Share das Freigeben eines beliebigen Verzeichnisses ermöglicht, können Sie darüber hinaus Code Überprüfungen durchführen, auch wenn Sie die Versionskontrolle derzeit nicht verwenden (obwohl Sie dies tun sollten), oder wenn das Team PRS nicht verwendet (z. b. Sie verwenden die trunk basierte Entwicklung).

Die Quell Code Verwaltung wird von Live Share derzeit nicht gemeinsam genutzt, was ein wichtiger Teil des Kontexts ist, wenn Sie für Code Überprüfungen verwendet wird. Dies ist in unserer Roadmap zu sehen, und Feedback zu Priorität wird sehr geschätzt ([Vote 👍 hier](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Technische Interviews

Wenn Sie Kandidaten für eine Entwickler Position anzeigen, ist es oft hilfreich, über whiteboarddiskussionen hinauszugehen und stattdessen zu beobachten, wie Sie ein Codierungs Problem innerhalb einer echten IDE lösen können (insbesondere, wenn Ihr Team/Ihre Organisation auf einem Tool, das Sie möchten sehen, dass Sie verwendet werden.) Dies hat nicht nur den Vorteil, dass Sie auf eine Art und Weise arbeiten können (die meisten Entwickler sind nicht auf Whiteboards Codieren!), sondern Sie erhalten bei der Arbeit sofort Feedback und Unterstützung (z. b. Buildfehler, IntelliSense). Häufig ist es wichtiger, den Denkprozess eines Kandidaten zu verstehen, anstatt die genaue Syntax und/oder API-Namen zu merken. Auf diese Weise bietet Live Share eine Umgebung, die mit einer paar Programmierungs Sitzung vergleichbar ist, aber den Teilnehmer in der eigenen Umgebung (einschließlich der Einstellungen des Betriebssystems, wie z. b. Barrierefreiheit) finden kann, und funktioniert gleichermaßen für lokale oder Remote-Interviews.

Außerdem ist die reale Entwicklung mehr als das einfache Schreiben von Code. Da Live Share auch das gemeinsame Debuggen, Tasks und Terminals unterstützt, ermöglicht es den Interviewern, Kandidaten während der Diagnose eines Problems zu beobachten und Ihnen die entsprechenden Tools zur Verfügung zu stellen (z. b. schrittweise Debuggen, Tests ausführen). Da der gesamte Kontext vom Computer des Hosts entfernt ist, können Kandidaten schnell in die "Interview Umgebung" springen, ohne Ihren Computer einrichten zu müssen (neben der Installation Live Share). Die Teams können dann ein Repository mit freigegebenen Interview-apps verwalten (oder ihre tatsächliche Produkt-Codebasis verwenden), die geklont und für Kandidaten freigegeben werden können, indem Sie Ihnen einfach vor jedem Gespräch die Sitzungs-URL senden.

## <a name="see-also"></a>Siehe auch

- [Sprach- und Plattformunterstützung](../reference/platform-support.md)
- [Anforderungen an die Konnektivität für Live Share](../reference/connectivity.md)
- [Sicherheitsfeatures von Live Share](../reference/security.md)
- [Schwerwiegende Fehler, Featurevorschläge und Einschränkungen](https://aka.ms/vsls-issues)
- [Featurevorschläge und Einschränkungen](https://aka.ms/vsls-feature-requests)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

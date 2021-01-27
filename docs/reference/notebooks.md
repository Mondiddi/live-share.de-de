---
title: Notebooks-Visual Studio Live Share | Microsoft-Dokumentation
description: Ausführliche Informationen zur Verwendung von Live Share für die Notebook-Zusammenarbeit
ms.date: 01/26/2021
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: simoncal
ms.workload:
- liveshare
ms.openlocfilehash: 40e30c77ebf3a1c339e1694c413eb8e744d576b9
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98887595"
---
# <a name="-notebooks"></a>📓 He

Notebooks sind ein wichtiger Bestandteil des Workflows vieler Entwickler und Datenanalysten. Mit Visual Studio Code, die einen umfangreichen, systemeigenen Notebook-Editor anbieten, freuen wir uns, eine Zusammenarbeit in Echtzeit zu ermöglichen, die es Teams und-Klassen ermöglicht, Notebooks und Live Share zusammen zu verwenden.

Die Live Share Notebook-Darstellung befindet sich derzeit in der Vorschau Phase und hat daher einige [Voraussetzungen](#pre-requisites) und [bekannte Probleme](#known-issues) , die beachtet werden müssen. Wir werden diese erste Vorschauversion schnell durchlaufen. Daher sollten Sie uns bei der Evaluierung [keine Fragen/Feedback senden](http://github.com/microsoftdocs/live-share). 👍<br />

<img width="800px" src="https://user-images.githubusercontent.com/116461/105928037-0d07a680-5ffa-11eb-8447-23bdb77fee9e.png" title="Notebook-Zusammenarbeit" />

## <a name="pre-requisites"></a>Voraussetzungen

Bevor Sie mit dem ausprobieren von Kollaborations Notebooks beginnen können, müssen Sie die folgenden Voraussetzungen im Rahmen dieser Vorschauversion installieren:

| Erforderliche Komponente | Host: erforderlich? | Gast: erforderlich? |
|-|-|-|
| Visual Studio-Insider | ✅ | ✅ |
| Live Share v 1.0.3541 + | ✅ | ✅ |
| Die erforderlichen Notebook-Erweiterungen (z. b. jupyter) | ✅ | Nicht _zutreffend (Live Share_ übernimmt dies!) |

## <a name="getting-started"></a>Erste Schritte

Sobald Sie und Ihre Teilnehmer über die erforderlichen Voraussetzungen verfügen, können Sie mit den folgenden Schritten Live Share und Notebooks verwenden:

1. Öffnen Sie ein Notebook innerhalb Visual Studio Code
1. Starten einer Live Share Sitzung
1. Sobald Ihre Gäste beitreten, können Sie mit der zusammen Bearbeitung von Zellen beginnen und die Cursor und Text Highlights der anderen sehen.
1. Sie haben Spaß bei der Zusammenarbeit an Notebooks! 🎉 

## <a name="known-issues"></a>Bekannte Probleme

In der folgenden Liste sind die bekannten Probleme mit den Live Share-und Notebooks-expertence zusammen mit den entsprechenden Problem Umgehungen dargestellt. 

| Problem | Problemumgehung | 
|-|-|
| Der "Follow-Modus" verfolgt keinen Bildlauf innerhalb eines Notebooks. | Wir arbeiten an der richtigen "Follow"-Unterstützung für Notebooks, aber in der Zwischenzeit müssen Sie manuell zur richtigen Notebook-Zelle scrollen, die Sie mit ihren Teilnehmern zusammen bearbeiten möchten. |
| Das Hinzufügen/Löschen/Verschieben von Zellen wird nicht zwischen Teilnehmern synchronisiert | Speichern Sie das Notebook Dokument, und lassen Sie es von allen Personen erneut öffnen. In Zukunft werden die Vorgänge auf Notebook Ebene in Echtzeit vollständig synchronisiert. |
| Notebook-Editoren beachten schreibgeschützte Live Share Sitzungen nicht | Obwohl Gäste Notebook-Zellen bearbeiten können, sind Sie nicht in der Lage, Sie auf dem Datenträger zu speichern, und ihre Sicherheit wird daher in einer schreibgeschützten Sitzung beibehalten. |

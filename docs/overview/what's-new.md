---
title: Übersicht – Visual Studio Live Share | Microsoft-Dokumentation
description: Neue Live Share Features und Releases
ms.custom: ''
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
ms.workload:
- liveshare
ms.openlocfilehash: 55425a7d57775a4e042e87b8dceb86532e1b966a
ms.sourcegitcommit: 211b17e49e7343786bd6859b65444cedd5e24958
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85796062"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

## <a name="integrated-chat"></a>Integrierter Chat 
Live Share jetzt den integrierten Chat für [Visual Studio Code](..\use\vscode.md) und [Live Share Web.](..\quickstart\browser-join). Dies bedeutet, dass Sie in Ihrer IDE mit ihren Peers chatten können.

>[!TIP]
>Live Share zuvor eine begleitende Erweiterung bereitgestellt. Dies bedeutete, dass Benutzer mit dieser Erweiterung Chat in Live Share verwenden konnten. Diese Erweiterung wurde nun abgewertet, und alle Benutzer von Live share in vs Code und dem WebClient verfügen über einen Chatdienst.

### <a name="common-questions"></a>Häufig gestellte Fragen

##### <a name="why-am-i-seeing-this-error-message"></a>Warum wird diese Fehlermeldung angezeigt?

Wenn Sie automatische Updates für Ihre Erweiterungen deaktiviert haben (einschließlich Live Share und der Live Share begleitenden Chat Erweiterung), werden die folgenden Fehlermeldungen angezeigt.

1. Wenn Sie den Host oder den Gast haben, wenn Sie die Live Share begleitende Chat-Erweiterung installiert haben, wenn Folgendes angezeigt wird:

>Aktualisieren Sie die `Live Share Chat` Begleit Erweiterung. Die installierte Version ist nicht mehr kompatibel.

Diese Fehlermeldung erfordert, dass Sie den Live Share Companion Chat aktualisieren, um die neue integrierte Chatfunktion zu verwenden.
Besuchen Sie den Marketplace, und suchen Sie nach *Chat* und Update auf die neueste Version. 

2. Als Gast, wenn Sie über die neuesten Versionen der Live Share Erweiterungen verfügen und Folgendes angezeigt wird:

>Der Host dieser Zusammenarbeits Sitzung ist derzeit nicht vom Chat getrennt oder verwendet eine Version von _Live Share_ , die dieses Feature nicht unterstützt. [Weitere Informationen] 

Der Host Ihrer Live Share Sitzung verwendet entweder Visual Studio oder andere Plattformen, um eine Sitzung zu hosten, die Live Share integrierten Chat noch nicht unterstützt. Möglicherweise wird auch die Fehlermeldung 1 angezeigt. oben aufgeführt.

3. Als Host oder Gast, wenn diese Fehlermeldung angezeigt wird: 

> Die Person, die Sie kontaktieren möchten, ist zurzeit nicht verfügbar oder verwendet eine Version von _Live Share_ , die dieses Feature nicht unterstützt. [Weitere Informationen] 

>Der Chatdienst ist zurzeit nicht getrennt.Versuchen Sie es in Kürze erneut.

Der Host Ihrer Live Share Sitzung verwendet entweder Visual Studio oder andere Plattformen, um eine Sitzung zu hosten, die Live Share integrierten Chat noch nicht unterstützt. Sie sind möglicherweise auch derzeit nicht verfügbar. Möglicherweise wird auch die Fehlermeldung 1 angezeigt. oben aufgeführt.


**Um den integrierten Chat zu verwenden, benötigen Sie automatische Updates für Ihre Live Share-Erweiterungen auf.** 

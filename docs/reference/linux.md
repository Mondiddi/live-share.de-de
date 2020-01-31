---
title: Linux-Installationsdetails-Visual Studio Live Share | Microsoft-Dokumentation
description: Ausführliche Informationen zum Installieren von Visual Studio Live share unter Linux.
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 69bc178ebb4052757f984d67482d216335f46dac
ms.sourcegitcommit: 5180aab73c086cbded6aae01aa01f71fb991dee1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818075"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Details zur Linux-Installation

Linux ist eine sehr variable Umgebung, deren Einrichtung durch die Vielzahl an Desktopumgebungen und Distributionen sich schwierig gestalten kann. Wenn Sie die unterstützten Versionen von **Ubuntu Desktop** (16.04 +), **CentOS 7**oder **Fedora Workstation** (27 und höher) verwenden und nur **offizielle Verteilungen von vs Code**verwenden, sollten Sie den Prozess direkt durchführen. Falls Sie jedoch eine vom Standard abweichende Konfiguration oder eine Downstreamdistribution verwenden, können eventuell Probleme auftreten. Dieses Dokument enthält einige Informationen zu den Anforderungen und Details zur Problembehandlung, die Ihnen helfen können, auch dann einzurichten, wenn Ihre Konfiguration nur von der Community unterstützt wird. Beachten Sie, dass Live Share nur **64-Bit-Linux**unterstützt.

## <a name="install-linux-prerequisites"></a>Installation der erforderlichen Komponenten für Linux

Einige Distributionen von Linux enthalten nicht alle Bibliotheken, die für Live Share erforderlich sind. Standardmäßig erkennt und installiert Live Share die erforderlichen Komponenten für Linux. Wenn Live Share ein Problem ermittelt, das aus fehlenden Bibliotheken resultiert, wird eine Popupbenachrichtigung angezeigt, die Sie auffordert, Live Share die Berechtigung zum Installieren der Bibliotheken zu erteilen.

![Popup Benachrichtigung mit der Meldung, dass die Voraussetzungen für Linux fehlen](../media/vscode-linux-prereq-missing.png)

Wenn Sie auf "installieren" klicken, wird ein Terminalfenster angezeigt, in dem Ihr Betriebssystem Sie auffordert, Ihr Administrator-/Stammkennwort einzugeben, um den Vorgang fortzusetzen. Wenn Sie davon ausgehen, dass das Skript erfolgreich abgeschlossen wurde, Visual Studio Code erneut laden, wenn Sie dazu aufgefordert werden. Weitere Tipps und Problemumgehungen finden Sie im Abschnitt **[tips by distribution (Tipps nach Distribution)](#tips-by-distribution)** .

Wenn eine Meldung angezeigt wird, dass das Skript Ihre Distribution nicht unterstützt, finden Sie von der Community zusammengestellte Informationen unter **[tips for community supported distributions (Tipps zu von der Community unterstützten Distributionen)](#tips-for-unsupported-distros)** .

Wenn Sie **den Befehl nicht für Sie ausführen vs Code ausführen**möchten, können Sie die neueste Version dieses Skripts jederzeit manuell erneut ausführen, indem Sie den folgenden Befehl in einem Terminal Fenster verwenden:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Tipps nach Verteilung

Obwohl das obige Installationsskript für die erforderlichen Komponenten eine Vielzahl von Verteilungen abdeckt, Fragen Sie sich vielleicht, was in den Vanille Installationen normalerweise fehlt. In der folgenden Liste werden die Schlüssel Bibliotheken angezeigt, die bei einer Neuinstallation einer bestimmten Verteilung fehlten. Die Liste enthält auch einige Tipps, die Ihnen helfen können, wenn Sie ein Problem erreichen.

| Verteilungs- | Nicht installierte Bibliotheken für die Vanille Installation | Weitere Schritte |
|--------|-------------------|----|
| Ubuntu Desktop 18,04 (64 Bit) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16,04 (64 Bit) | &lt;none&gt; | &lt;none&gt; |
| Kuubuntu 18,04 (64 Bit) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kuubuntu 16,04 (64 Bit) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18,04 (64 Bit) |&lt;none&gt;  | <ul><li>Stellen Sie sicher, dass "Start gnome Services on startup" auf der Registerkarte "Erweitert" von "Sitzung und Start" aktiviert ist.</li><li>Wenn Sie Probleme bei der Anmeldung haben, installieren Sie `seahorse`, starten Sie "Kenn Wörter und Schlüssel", vergewissern Sie sich, dass Sie über einen "Login"-Schlüsselbund verfügen und ihn entsperren können.</li></ul> |
| Xubuntu 16,04 (64 Bit) | &lt;none&gt; | <ul><li>Stellen Sie sicher, dass "Start gnome Services on startup" auf der Registerkarte "Erweitert" von "Sitzung und Start" aktiviert ist.</li><li>Wenn Sie Probleme bei der Anmeldung haben, installieren Sie `seahorse`, starten Sie "Kenn Wörter und Schlüssel", vergewissern Sie sich, dass Sie über einen "Login"-Schlüsselbund verfügen und ihn entsperren können.</li></ul> |
| Minze 19 Zimt (64 Bit) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18,3 Cinnamon (64 Bit) | &lt;none&gt;  | &lt;none&gt; |
| Tests für Debian 10 (Buster) (64 Bit) | Release nicht stabil, so unbekannt. | <ul><li>Debian-Tests und instabil (SID) werden nicht offiziell unterstützt.</li><li>Es gibt ein [bekanntes Problem](https://github.com/dotnet/corefx/issues/33179) in .net Core, das sich auf Live Share auswirkt. </li><li>[Eine Problem Umgehung](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)finden Sie hier.</li></ul> |
| Debian 9-gnome-Desktop (64 Bit) | &lt;none&gt; | <ul><li>Möglicherweise müssen Sie `sudo` installieren und den Benutzer der sudo-Gruppe hinzufügen, um das automatisierte Installationsskript zu verwenden.</li>  |
| Fedora Workstation 29 (64 Bit) | `openssl-compat10` | &lt;none&gt; |
| Fedora Workstation 28 (64 Bit) | &lt;none&gt; | &lt;none&gt; |
| Fedora Workstation 27 (64 Bit) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7-GNOME-Desktop (64 Bit) | &lt;none&gt; | &lt;none&gt; |

Weitere Informationen zu anderen nicht-Debian-, Ubuntu-oder RHL-basierten Distributionen finden Sie **[unter Tipps für von der Community unterstützte Distributionen](#tips-for-community-supported-distros)** .

Weitere Details finden Sie weiter [unten](#detailed-library-requirements) in den spezifischen Bibliotheken Live Share Anforderungen.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Tipps für von der Community unterstützte Distributionen

Verteilungen außerhalb der Debian/Ubuntu-oder RHL-Strukturen werden von Visual Studio Code oder .net Core nicht offiziell unterstützt. Daher werden Sie von der Erweiterung nicht offiziell von Visual Studio Live Share unterstützt. Allerdings hat die Community einige nützliche Informationen zum Einrichten und Ausführen von Live Share für eine Reihe zusätzlicher Distributionen beigetragen.

> **PRS Willkommen:** Wenn Sie diese Informationen mit Ihrer bevorzugten Distribution aktualisieren möchten, senden Sie einen PR für [Diese Datei](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) in unserem GitHub-Repository. Noch besser: Wenn Sie möchten, dass das Anwendungsinstallations Programm Ihre bevorzugte Verteilung unterstützt, können Sie einen PR [für diese Datei über](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)Mitteln.

| Verteilungs- | Test? | Nicht installierte Bibliotheken für die Vanille Installation | Weitere Schritte |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 Bit) | Ja | Variiert. Mögliche Bibliotheken: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Wird vom [Installationsskript](#install-linux-prerequisites)für erforderliche Komponenten unterstützt.</li><li>Verwenden Sie zum vs Code das [Visual Studio-Code-bin-](https://aur.archlinux.org/packages/visual-studio-code-bin) Aur-Paket.</li><li>`sudo` müssen installiert werden, damit das automatisierte erforderliche Installationsskript verwendet werden kann.</li><li>in einigen Desktopumgebungen sind `gnome-keyring` möglicherweise zusätzliche [Einrichtungsschritte](https://wiki.archlinux.org/index.php/GNOME/Keyring) erforderlich.</ul> |
| Manjaro 17,1 (64 Bit) | Ja | `xorg-xprop liburcu` | <ul><li>Wird vom [Installationsskript](#install-linux-prerequisites)für erforderliche Komponenten unterstützt.</li><li>Verwenden Sie zum vs Code das [Visual Studio-Code-bin-](https://aur.archlinux.org/packages/visual-studio-code-bin) Aur-Paket.</li></ul> |
| openSUSE, Version 15, KDE (64 Bit) | Ja | `libopenssl1_0_0 gnome-keyring` | <ul><li>Wird vom Installationsskript für erforderliche Komponenten unterstützt.</li></ul> |
| Solus 3 (64 Bit) | Ja | `xprop` | <ul><li>Wird vom [Installationsskript](#install-linux-prerequisites)für erforderliche Komponenten unterstützt.</li><li>In Versionen des `vscode` Pakets vor Version 57 fehlten die erforderlichen Product. JSON-Werte ([siehe unten](#vs-code-oss-issues)). Aktualisieren Sie das `vscode` Paket, um dieses Problem zu beheben.</li></ul> |
| "Gentoo" (64 Bit) | Ja | Hohe Variable. Mögliche fehlende Pakete: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>Das `visual-studio-code`-Paket in der **jorgicio** -Überlagerung ist bekanntermaßen funktionsfähig.</li></ul>

## <a name="install-prerequisites-manually"></a>Erforderliche Komponenten manuell installieren

 Es wird empfohlen, das Skript für die **Abhängigkeits Installation**von Live Share zu verwenden, aber dieser Abschnitt enthält weitere Details zu den Bibliotheks Anforderungen, wenn Sie diese Schritte selbst ausführen möchten oder eine Distribution verwenden, die nicht vom Skript unterstützt wird.

Typische fehlende Bibliotheken in Vanille Installationen finden Sie in den Abschnitten [Tipps by Distribution](#tips-by-distribution) und [Tipps zu von der Community unterstützten Distributionen](#tips-for-unsupported-distros) .

### <a name="detailed-library-requirements"></a>Ausführliche Bibliotheks Anforderungen

Die systemeigenen Bibliotheks Anforderungen von Visual Studio Live Share stammen aus der Verwendung von .net Core 2,1, libsecret zum Beibehalten von Anmelde Informationen und der Browser Integration. In der folgenden Tabelle werden die Anforderungen für Verteilungen zusammengefasst, die offiziell von .net Core unterstützt

| Verteilungs- | .Net Core-reqs | Speicherung von Anmelde Informationsspeicher-reqs| Browser Integration reqs |
|--------------|-----------|--------------------|------------|
| Ubuntu-und downstreamverteilungen | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (für Ubuntu 16,04, Mint 18,3) oder `libicu57` (für Ubuntu 17,10) oder `libicu60` (für Ubuntu 18,04, Mint 19) | `libsecret-1-0 gnome-keyring` (oder libsecret-unterstützter Schlüsselbund-KWallet unterstützt libsecret nicht) | `desktop-file-utils x11-utils` |
| Debian 9-und downstreamverteilungen | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (oder libsecret-unterstützter Schlüsselbund-KWallet unterstützt libsecret nicht) | `desktop-file-utils x11-utils` |
| RHL/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora erfordert auch `compat-openssl10`| `libsecret gnome-keyring` (oder libsecret-unterstützter Schlüsselbund-KWallet unterstützt libsecret nicht) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (oder libsecret-unterstützter Schlüsselbund-KWallet unterstützt libsecret nicht) | `desktop-file-utils xprop`

Während andere Verteilungen die gleichen Bibliotheken erfordern, können sich die Paketnamen unterscheiden. Einige dieser Informationen finden Sie im Abschnitt [Tipps für von der Community unterstützte Distributionen](#tips-for-unsupported-distros) .

### <a name="debian--ubuntu"></a>Debian/Ubuntu

Bibliotheken können auf Debian/Ubuntu-basierten Verteilungen installiert werden, indem `sudo apt install <library-name>` in einem Terminal ausgeführt wird.

Führen Sie für Ubuntu-basierte Verteilungen einschließlich Mint Folgendes aus:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Führen Sie für in Debian 9 und nicht-Ubuntu-downstreamverteilungen Folgendes aus:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/CentOS/RHL

Bibliotheken können auf Fedora/CentOS/RHL-basierten Verteilungen installiert werden, indem `sudo yum install <library-name>` in einem Terminal ausgeführt wird. Beispielsweise wird Folgendes installiert:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>VS Code OSS-Probleme

> **Arch Linux/manjaro-Benutzer:** Verwenden Sie das [Visual Studio-bin-BS-](https://aur.archlinux.org/packages/visual-studio-code-bin) Paket, um dieses Problem zu vermeiden.

Bei Paketen von Visual Studio Code, bei denen es sich entweder um Vanille oder geänderte Versionen von vs Code OSS handelt, kann ein kritischer Wert in `product.json` Datei fehlen, der verhindert, dass Visual Studio Live Share aktiviert wird.

Eine schnelle Möglichkeit, um zu sehen, dass dieses Problem möglicherweise auftritt, besteht darin, den > "umschalten Entwicklertools" zu unterstützen und zu überprüfen, ob Sie eine Stapel Überwachung finden, die anzeigt, dass die Live Share Erweiterung nicht aktiviert wurde, weil Sie eine "vorgeschlagene API" verwendet hat.

Überprüfen Sie den Inhalt `product.json`, um zu überprüfen, ob dies das Problem ist. Der Speicherort der Datei variiert je nach Paket, befindet sich jedoch in der Regel an einem der folgenden Speicherorte:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Wenn die `extensionAllowedProposedApi`-Eigenschaft fehlt oder "MS-vsliveshare. vsliveshare" nicht referenziert wird, verwenden Sie eine OSS-Version mit diesem Problem.

Um dieses Problem zu **umgehen**, können Sie den folgenden Code in der Datei "Product. JSON" hinzufügen:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Im [obigen](#tips-for-community-supported-distros) Abschnitt finden Sie weitere Informationen dazu, ob die von Ihnen verwendete Distribution bekanntermaßen funktioniert.

## <a name="linux-browser-integration"></a>Browserintegration unter Linux

In der Regel sind für die Browserintegration unter Linux **keine zusätzlichen Installationsschritte** in Visual Studio Live Share erforderlich.

Um dies zu erreichen, platziert Live Share automatisch eine Desktop Datei in `~/.local/share/applications` und das erforderliche Start Programm in `~/.local/share/vsliveshare`, wenn die Erweiterung zum ersten Mal initialisiert wird. Wenn dies erfolgreich ist, ist keine Aktion erforderlich.

In einigen Fällen unterstützen Verteilungen diesen Speicherort nicht, oder es sind Anpassungen erforderlich, damit Sie mit den eigenen Vanille Installationen arbeiten können. In diesen Fällen greift Live Share auf die Verwendung von `/usr/local/share` zurück. Daher **können Sie benachrichtigt werden, dass Ihr Administrator Kennwort (sudo)** zum Abschluss der Installation erforderlich ist. Daraufhin wird ein Terminalfenster angezeigt, das den Installationspfad für das Startprogramm des Browsers enthält. Geben Sie Ihr Kennwort ein, wenn Sie dazu aufgefordert werden, und drücken Sie nach Abschluss der Installation die EINGABETASTE, um das Terminalfenster zu schließen.

Wenn Sie stattdessen den Befehl selbst ausführen möchten, können Sie stattdessen auf "Kopieren" klicken, wodurch der Terminal Befehl stattdessen in die Zwischenablage kopiert wird.

Wenn Sie diesen Schritt vollständig überspringen möchten, können Sie weiterhin Zusammenarbeits [Sitzungen manuell beitreten](../use/vscode.md#join-manually), aber Sie können nicht beitreten, indem Sie im Browser einen Einladungslink öffnen. Beachten Sie, dass Sie zu einem späteren Zeitpunkt jederzeit erneut auf den Befehl zugreifen können, indem Sie **STRG + UMSCHALT + p/cmd + UMSCHALT + p** drücken und den Befehl "Live Share: Start Programm Setup" auswählen.

## <a name="see-also"></a>Siehe auch

- [Gewusst wie: zusammenarbeiten mit Visual Studio Code](../use/vscode.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

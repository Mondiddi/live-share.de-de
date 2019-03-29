---
title: Details zur der Linux - Installation – Visual Studio Live Share | Microsoft-Dokumentation
description: Ausführliche Informationen zum Installieren von Visual Studio Live Share unter Linux.
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
ms.openlocfilehash: 9ac16b0e598fb07446c2b682397684b7e2e4709a
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640132"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Details zur Installation von Linux

Linux ist eine sehr variable Umgebung, deren Einrichtung durch die Vielzahl an Desktopumgebungen und Distributionen sich schwierig gestalten kann. Wenn Sie an die unterstützten Versionen von halte **Ubuntu Desktop** (16.04 und höher), **CentOS 7**, oder **Fedora Arbeitsstation** (27 und höher) und nur **offizielle Distributionen von Visual Studio Code**, finden Sie den Prozess einfach. Falls Sie jedoch eine vom Standard abweichende Konfiguration oder eine Downstreamdistribution verwenden, können eventuell Probleme auftreten. Dieses Dokument enthält einige Informationen zu Anforderungen und einige Details zur Problembehandlung, mit denen Sie einzurichten und ausführen, auch wenn Sie Konfiguration nur Community unterstützt. Beachten Sie, die Live Share nur unterstützt **64-Bit-Linux**.

## <a name="install-linux-prerequisites"></a>Installation der erforderlichen Komponenten für Linux

Einige Distributionen von Linux enthalten nicht alle Bibliotheken, die für Live Share erforderlich sind. Standardmäßig erkennt und installiert Live Share die erforderlichen Komponenten für Linux. Wenn Live Share ein Problem ermittelt, das aus fehlenden Bibliotheken resultiert, wird eine Popupbenachrichtigung angezeigt, die Sie auffordert, Live Share die Berechtigung zum Installieren der Bibliotheken zu erteilen.

![Popup mit Benachrichtigung, dass die Linux-Voraussetzungen nicht erfüllt sind](../media/vscode-linux-prereq-missing.png)

Wenn Sie auf "Installieren" klicken, wird ein terminal-Fenster angezeigt, in dem Ihr Betriebssystem werden Sie aufgefordert, geben Ihren Administrator / root-Kennwort ("sudo"), um den Vorgang fortzusetzen. Vorausgesetzt, dass das Skript erfolgreich abgeschlossen wurde, sollte erneut laden Visual Studio Code, wenn Sie dazu aufgefordert startklar sein! Weitere Tipps und Problemumgehungen finden Sie im Abschnitt **[tips by distribution (Tipps nach Distribution)](#tips-by-distribution)**.

Wenn eine Meldung angezeigt wird, dass das Skript Ihre Distribution nicht unterstützt, finden Sie von der Community zusammengestellte Informationen unter **[tips for community supported distributions (Tipps zu von der Community unterstützten Distributionen)](#tips-for-unsupported-distros)**.

Wenn Sie **bevorzugen Sie nicht möchten, dass Visual Studio Code, führen Sie den Befehl für Sie**, Sie können auch entscheiden, um die neueste Version dieses Skripts zu einem beliebigen Zeitpunkt manuell erneut ausführen, indem mit dem folgenden Befehl in einem Terminalfenster:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Tipps, die von der Verteilung von

Während der Installation der erforderlichen Komponenten oben angegebene Skript umfasst eine Vielzahl von Verteilungen, vielleicht wie einfache Installationen in der Regel nicht vorhanden ist. Die folgende Liste enthält die wichtigsten Bibliotheken, die in einer Neuinstallation von einer bestimmten Distribution nicht vorhanden waren. Die Liste enthält auch, dass einige Tipps, die Ihnen helfen können betriebsbereit machen, wenn ein Problem auftritt.

| Verteilung | Vanille installieren fehlende Bibliotheken | Zusätzliche Schritte |
|--------|-------------------|----|
| Ubuntu Desktop 18.04 (64-Bit) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16.04 (64-bit) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64-bit) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64-bit) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64-bit) |&lt;none&gt;  | <ul><li>Stellen Sie sicher "Starten Sie GNOME Dienste beim Start" auf der Registerkarte "Erweitert", "Sitzung und beim Starten der" aktiviert ist.</li><li>Wenn der Anmeldung Probleme auftreten, installieren Sie `seahorse`, "Kennwörter und Schlüssel" beginnen, überprüfen Sie "Anmeldung" Schlüsselbund und, dass Sie es entsperren können.</li></ul> |
| Xubuntu 16.04 (64-bit) | &lt;none&gt; | <ul><li>Stellen Sie sicher "Starten Sie GNOME Dienste beim Start" auf der Registerkarte "Erweitert", "Sitzung und beim Starten der" aktiviert ist.</li><li>Wenn der Anmeldung Probleme auftreten, installieren Sie `seahorse`, "Kennwörter und Schlüssel" beginnen, überprüfen Sie "Anmeldung" Schlüsselbund und, dass Sie es entsperren können.</li></ul> |
| Erstellen von 19 Zimt (64-Bit) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18,3 Zimt (64-Bit) | &lt;none&gt;  | &lt;none&gt; |
| Debian-10 (Buster) Testing (64-Bit) | Release nicht stabil, also unbekannt. | <ul><li>Debian Test- und Instabilität (Sid) werden nicht offiziell unterstützt.</li><li>Es gibt eine [bekanntes Problem](https://github.com/dotnet/corefx/issues/33179) in .NET Core, die Live Share betroffen sind. </li><li>Finden Sie unter [hier, um dieses Problem zu umgehen](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Debian 9 GNOME-Desktops (64-Bit) | &lt;none&gt; | <ul><li>Sie müssen möglicherweise installieren `sudo` und fügen Sie Ihr Benutzerkonto zur Gruppe "sudo" Skript für die automatisierte Installation zu verwenden.</li>  |
| Fedora Arbeitsstation 29 (64-Bit) | `openssl-compat10` | &lt;none&gt; |
| Fedora Arbeitsstation 28 (64-Bit) | &lt;none&gt; | &lt;none&gt; |
| Fedora Arbeitsstation 27 (64-Bit) | &lt;none&gt; | &lt;none&gt; |
| GNOME-Desktops für CentOS 7 (64-Bit) | &lt;none&gt; | &lt;none&gt; |

Finden Sie unter **[Tipps für die Community unterstützt Verteilungen](#tips-for-community-supported-distros)** Informationen zu anderen nicht-Debian / Ubuntu oder RHL basierende Distributionen.

Weitere Informationen finden Sie auch [unten](#detailed-library-requirements) zu den bestimmten Bibliotheken, die Live Share benötigt.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Tipps für die Community unterstützte Distributionen

Verteilungen außerhalb der Debian / Ubuntu oder RHL Strukturen werden von Visual Studio Code oder .NET Core nicht offiziell unterstützt. Aus diesem Grund werden durch Erweiterung, sie nicht offiziell von Visual Studio Live Share entweder unterstützt. Die Community beigetragen hat einige nützliche Informationen zu Live Share einrichten und Ausführen auf einer Reihe von zusätzlichen Verteilungen.

> **Willkommen bei der Pull Requests:** Wenn Sie diese Informationen mit Ihrem bevorzugten Verteilungspunkt aktualisiert interessieren, senden Sie einen PR für [dieser Datei](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) in unserem GitHub-Repository für Dokumente. Noch besser ist, wenn Sie, um den Dependency-Installationsprogramm unterstützen Ihre bevorzugten Verteilungspunkt abzurufen möchten, Sie können übermitteln ein PR [für diese Datei](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Verteilung | Funktioniert? | Vanille installieren fehlende Bibliotheken | Zusätzliche Schritte |
|--------------|----------|-------------------|------------------|
| Arch Linux (64-Bit) | Ja | Variiert. Mögliche Bibliotheken: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Unterstützt durch die [erforderliche Installationsskript](#install-linux-prerequisites).</li><li>Verwenden der [Visual-Studio-Code-Bin](https://aur.archlinux.org/packages/visual-studio-code-bin) Paket der Benutzerrepository für Visual Studio Code.</li><li>`sudo` installiert werden, verwenden Sie wird die automatisierte Skripts installieren müssen.</li><li>`gnome-keyring` möglicherweise erfordern zusätzliche [Installationsschritte](https://wiki.archlinux.org/index.php/GNOME/Keyring) in einige desktopumgebungen.</ul> |
| Manjaro 17.1 (64-Bit) | Ja | `xorg-xprop liburcu` | <ul><li>Unterstützt durch die [erforderliche Installationsskript](#install-linux-prerequisites).</li><li>Verwenden der [Visual-Studio-Code-Bin](https://aur.archlinux.org/packages/visual-studio-code-bin) Paket der Benutzerrepository für Visual Studio Code.</li></ul> |
| OpenSuSE LEAP 15 KDE (64-Bit) | Ja | `libopenssl1_0_0 gnome-keyring` | <ul><li>Vom Skript für die erforderliche Installation unterstützt.</li></ul> |
| Solus 3 (64-Bit) | Ja | `xprop` | <ul><li>Unterstützt durch die [erforderliche Installationsskript](#install-linux-prerequisites).</li><li>Versionen der `vscode` Paket vor der Freigabe 57 fehlen erforderliche product.json Werte ([siehe unten](#vs-code-oss-issues)). Aktualisieren der `vscode` Paket, um dieses Problem zu beheben.</li></ul> |
| Gentoo (64-Bit) | Ja | Stark variieren. Mögliche fehlende Pakete: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>Die `visual-studio-code` -Paket in der **Jorgicio** Overlay bekanntermaßen funktioniert.</li></ul>

## <a name="install-prerequisites-manually"></a>Manuelles Installieren von Voraussetzungen

 Während es empfiehlt sich Live Share **Abhängigkeit Installationsskript**, dieser Abschnitt enthält weitere Details Anforderungen an den Fall, dass diese Schritte selbst ausführen, oder verwenden eine Verteilung, die von nicht unterstützt werden sollen die Skript.

Typische fehlende Bibliotheken in einfachen Installation finden Sie in der [Tipps, die von der Verteilung von](#tips-by-distribution) und [Tipps für die Community unterstützt Verteilungen](#tips-for-unsupported-distros) Abschnitte.

### <a name="detailed-library-requirements"></a>Ausführliche bibliotheksanforderungen.

Visual Studio Live Share die native bibliotheksanforderungen stammen von der Verwendung von .NET Core 2.1, Libsecret Anmeldeinformationen und die Browserintegration beibehalten. Der folgenden Tabelle werden diese Anforderungen für Distributionen, die von .NET Core offiziell unterstützt.

| Verteilung | .NET Core-Aufzählanforderungen | Credential Storage Aufzählanforderungen| Browser-Integration Aufzählanforderungen |
|--------------|-----------|--------------------|------------|
| Ubuntu und downstream-Verteilungen | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (für Ubuntu 16.04, Erstellen von 18,3) oder `libicu57` (für die Ubuntu 17.10) oder `libicu60` (für Ubuntu 18.04, Erstellen von 19) | `libsecret-1-0 gnome-keyring` (oder Libsecret unterstützt Schlüsselbund - Kwallet Libsecret nicht unterstützt) | `desktop-file-utils x11-utils` |
| Debian 9 und downstream-Verteilungen | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (oder Libsecret unterstützt Schlüsselbund - Kwallet Libsecret nicht unterstützt) | `desktop-file-utils x11-utils` |
| RHL / CentOS / Fedora | `openssl-libs krb5-libs zlib libicu` Fedora ist auch erforderlich. `compat-openssl10`| `libsecret gnome-keyring` (oder Libsecret unterstützt Schlüsselbund - Kwallet Libsecret nicht unterstützt) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (oder Libsecret unterstützt Schlüsselbund - Kwallet Libsecret nicht unterstützt) | `desktop-file-utils xprop`

Während andere Distributionen die gleichen Bibliotheken erfordern, können ihren Paketnamen variieren. Finden Sie einige davon in der [Tipps für die Community unterstützt Verteilungen](#tips-for-unsupported-distros) Abschnitt.

### <a name="debian--ubuntu"></a>Debian / Ubuntu

Bibliotheken können auf Debian/Ubuntu-basierte Distributionen installiert werden, mit `sudo apt install <library-name>` in einem Terminal aus.

Führen Sie für Ubuntu-basierte Distributionen einschließlich Mint:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Für Debian 9 "und" nicht-Ubuntu downstream-Distributionen ausgeführt:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

Bibliotheken können auf Fedora/CentOS/RHL-basierten Distributionen installiert werden, mit `sudo yum install <library-name>` in einem Terminal aus. Dies wird beispielsweise alles, was installiert:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>VS Code OSS-Probleme

> **Arch Linux/Manjaro-Benutzer:** Verwenden der [Visual-Studio-Bin](https://aur.archlinux.org/packages/visual-studio-code-bin) Paket der Benutzerrepository um dieses Problem zu vermeiden.

Pakete von Visual Studio Code, die entweder Vanille oder geändert werden Versionen von Visual Studio Code OSS können in einen kritischen Wert fehlt `product.json` -Datei, die verhindert, dass Visual Studio Live Share aktivieren.

Eine schnelle Möglichkeit, sehen Sie möglicherweise haben, besteht dieses Problem wird in der Hilfe zu > "Entwicklertools ein-/ausschalten" und sehen Sie sich, wenn Sie feststellen, dass eine stapelüberwachung, der angibt, der Live Share-Erweiterungs nicht aktivieren, da es eine "vorgeschlagene-API." verwendet wurde

Um zu überprüfen, ob dies das Problem, überprüfen Sie den Inhalt der `product.json`. Der Speicherort der Datei unterscheidet sich von dem Paket, aber es ist in der Regel in einem der folgenden Speicherorte:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Wenn die `extensionAllowedProposedApi` Eigenschaft ist nicht vorhanden oder nicht angezeigt. "ms-vsliveshare.vsliveshare" auf die verwiesen wird, verwenden Sie eine OSS-Version dieses Problems.

Als eine **problemumgehung**, können Sie Folgendes in die product.json hinzufügen:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Finden Sie unter [oben](#tips-for-community-supported-distros) Weitere Details zur gibt an, ob die Verteilung, die Sie verwenden bekanntermaßen funktioniert.

## <a name="linux-browser-integration"></a>Browserintegration unter Linux

In der Regel sind für die Browserintegration unter Linux **keine zusätzlichen Installationsschritte** in Visual Studio Live Share erforderlich.

Zu diesem Zweck fügt automatisch Live Share in eine desktop-Datei `~/.local/share/applications` und das erforderliche Startprogramm selbst in `~/.local/share/vsliveshare` Wenn die Erweiterung zunächst initialisiert. Wenn dies erfolgreich ist, ist keine Aktion Ihrerseits erforderlich.

In einigen Fällen Verteilungen entweder diesen Speicherort zu unterstützen oder nicht erfordern Änderungen mit ihren einfachen installiert arbeiten soll. In diesen Fällen Live Share greift auf zurück `/usr/local/share` stattdessen. Daher **Sie werden benachrichtigt, dass Ihr Administratorkennwort ("sudo") erforderlich ist** um die Installation abzuschließen. Daraufhin wird ein Terminalfenster angezeigt, das den Installationspfad für das Startprogramm des Browsers enthält. Geben Sie Ihr Kennwort ein, wenn Sie dazu aufgefordert werden, und drücken Sie nach Abschluss der Installation die EINGABETASTE, um das Terminalfenster zu schließen.

Wenn Sie den Befehl selbst stattdessen ausführen möchten, können Sie klicken, "Kopieren" die terminalbefehl aus stattdessen in die Zwischenablage kopiert wird.

Schließlich, wenn Sie diesen Schritt überspringen, vollständig sich entscheiden, Sie können weiterhin [Manuelles Verknüpfen von zusammenarbeitssitzungen](../use/vscode.md#join-manually), aber Sie werden nicht in der Lage, verknüpfen, indem ein Link zur freigabeeinladung im Browser öffnen. Beachten Sie, dass Sie es später noch Mal, stets den Befehl durch Drücken von zugreifen können **STRG + UMSCHALT + P / Cmd + UMSCHALT + P** und Auswählen der "Live-Freigabe: Setup für Startfeld"-Befehl.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Zusammenarbeiten mithilfe von Visual Studio Code](../use/vscode.md)
- [Anforderungen an die Konnektivität für Live Share](connectivity.md)
- [Sicherheitsfeatures von Live Share](security.md)

Gibt es Probleme? Lesen Sie [Troubleshooting](../troubleshooting.md) oder [Feedback geben](../support.md).

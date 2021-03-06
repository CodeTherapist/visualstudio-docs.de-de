---
title: Tools zum Erkennen und Verwalten von Visual Studio-Instanzen
description: Erfahren Sie mehr über die Tools, die Sie zum Erkennen und Verwalten von Visual Studio-Installationen auf Clientcomputern verwenden können.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 160d0f283542445335496e3cbb7b98955df02b05
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50672612"
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>Tools zum Erkennen und Verwalten von Visual Studio-Instanzen

Es gibt mehrere Tools, die Sie zum Erkennen und Verwalten von Visual Studio-Installationen auf Clientcomputern verwenden können.

## <a name="detecting-existing-visual-studio-instances"></a>Erkennen vorhandener Visual Studio-Instanzen

Wir haben mehrere Tools zur Verfügung gestellt, mit denen Sie installierte Instanzen von Visual Studio auf Clientcomputern erkennen und verwalten können:

* [VSWhere](https://github.com/microsoft/vswhere): eine ausführbare Datei, die entweder in Visual Studio integriert oder zur separaten Verteilung verfügbar ist und Ihnen dabei hilft, die Speicherorte aller Visual Studio-Instanzen auf einem bestimmten Computer zu finden.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): PowerShell-Skripts, die die Setupkonfigurations-API zum Identifizieren der installierten Instanzen von Visual Studio verwenden.
* [VS-Setup-Samples](https://github.com/microsoft/vs-setup-samples): C#- und C++-Beispiele, die veranschaulichen, wie Sie die Setupkonfigurations-API zum Abfragen einer vorhandene Installation verwenden.

Darüber hinaus stellt die [Setupkonfigurations-API](<xref:Microsoft.VisualStudio.Setup.Configuration>) Schnittstellen für Entwickler bereit, die eigene Hilfsprogramme zum Abfragen von Visual Studio-Instanzen erstellen möchten.

## <a name="using-vswhereexe"></a>Verwenden von „vswhere.exe“

`vswhere.exe` ist in Visual Studio 2017-Version 15.2 oder höher im Lieferumfang enthalten. Alternativ dazu können Sie die Datei auch von der Seite mit den [Releases](https://github.com/Microsoft/vswhere/releases) herunterladen. Verwenden Sie `vswhere -?`, um Hilfeinformationen zum Tool zu erhalten. Dieser Befehl zeigt beispielsweise alle Releases von Visual Studio, einschließlich älterer Produktversionen und Vorabversionen, und gibt die Ergebnisse im JSON-Format zurück:

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

>[!TIP]
>Weitere Informationen zur Installation von Visual Studio 2017 finden in den [Blogbeiträgen von Heath Stewart](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).


## <a name="editing-the-registry-for-a-visual-studio-instance"></a>Bearbeiten der Registrierung einer Visual Studio-Instanz

In Visual Studio 2017 werden Registrierungseinträge in einem privaten Speicherort gespeichert, was ermöglicht, dass sich mehrere Instanzen derselben Version von Visual Studio auf demselben Computer befinden.

Da diese Einträge nicht in der globalen Registrierung gespeichert werden, gibt es spezielle Anweisungen zum Verwenden des Registrierungseditors, um Registrierungseinträge zu ändern:

1. Wenn Sie eine Instanz Visual Studio-2017 geöffnet haben, schließen Sie sie.
2. Starten Sie `regedit.exe`.
3. Wählen Sie den Knoten `HKEY_LOCAL_MACHINE` aus.
4. Wählen Sie im Hauptmenü des Registrierungs-Editors **Datei -> Struktur laden...** und dann die private Registrierungsdatei aus, die im Ordner **AppData\Local** gespeichert ist. Zum Beispiel:
   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

   > [!NOTE]
   > `<config>` entspricht der Instanz von Visual Studio, die Sie durchsuchen möchten.

Sie werden aufgefordert, einen Strukturnamen anzugeben, der zum Namen Ihrer isolierten Struktur wird. Anschließend sollten Sie in der Lage sein, die Registrierung unter der von Ihnen erstellten isolierten Struktur zu durchsuchen.

> [!IMPORTANT]
> Bevor Sie Visual Studio erneut starten, müssen Sie die isolierte Struktur entladen, die Sie erstellt haben. Zu diesem Zweck wählen Sie im Hauptmenü des Registrierungs-Editors „Datei -> Struktur entladen“ aus. (Wenn Sie dies nicht tun, bleibt die Datei gesperrt, und Visual Studio kann nicht gestartet werden.)

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Siehe auch

* [Administratorhandbuch für Visual Studio](visual-studio-administrator-guide.md)

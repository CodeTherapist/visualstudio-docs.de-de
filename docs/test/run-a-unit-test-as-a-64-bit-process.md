---
title: Ausführen eines Komponententests als 64-Bit-Prozess in Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: cf8a815cb0827ed69c24686053bf118a48c020eb
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379903"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Ausführen eines Komponententest als 64-Bit-Prozess

Wenn Sie über einen 64-Bit-Computer verfügen, können Sie Komponententests ausführen und Code Coverage-Informationen als 64-Bit-Prozess erfassen.

## <a name="to-run-a-unit-test-as-a-64-bit-process"></a>So führen Sie einen Komponententest als 64-Bit-Prozess aus

1. Wenn Ihr Code oder Ihre Tests als 32-Bit/X86 kompiliert wurden, aber Sie diese als ein 64-Bit-Prozess ausführen möchten, kompilieren Sie sie als **Beliebige CPU** oder optional als **64-Bit**.

    > [!TIP]
    > Maximale Flexibilität erhalten Sie, wenn Sie die Testprojekte mit der Konfiguration **Beliebige CPU** kompilieren. Die Ausführung ist dann sowohl auf 32- als auch auf 64-Bit-Agents möglich. Das Kompilieren von Testprojekten mit der **64-Bit**-Konfiguration bietet keinen Vorteil.

2. Wählen Sie im Visual Studio-Menü **Test**, wählen Sie dann **Einstellungen** und anschließend **Prozessorarchitektur** aus. Wählen Sie **x64** zum Ausführen der Tests als 64-Bit-Prozess aus.

   - ODER

   Geben Sie `<TargetPlatform>x64</TargetPlatform>` in einer *RUNSETTINGS*-Datei an. Ein Vorteil dieser Methode ist, dass Sie Gruppen von Einstellungen in verschiedenen Dateien angeben und schnell zwischen verschiedenen Einstellungen wechseln können. Sie können auch die Einstellungen zwischen Projektmappen kopieren. Weitere Informationen hierzu finden Sie unter [Configure unit tests by using a .runsettings file (Konfigurieren von Komponententests mithilfe einer .runsettings-Datei)](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

## <a name="see-also"></a>Siehe auch

- [Ausführen von Komponententests mit dem Test-Explorer](../test/run-unit-tests-with-test-explorer.md)
- [Ausführen von Komponententests für Code](../test/unit-test-your-code.md)

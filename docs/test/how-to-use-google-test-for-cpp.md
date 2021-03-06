---
title: Verwenden von Google Test für C++ in Visual Studio
ms.date: 11/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: a047b7d46aa2fe325baa4fee7459bb822e3b1bea
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138632"
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Verwenden von Google Test für C++ in Visual Studio
In **Visual Studio 2017 Version 15.5** und höher wird Google Test als Standardkomponente der Workload **Desktopentwicklung mit C++** in die Visual Studio-IDE integriert. Öffnen Sie den Visual Studio-Installer, und suchen Sie Google Test in der Liste der Workloadkomponenten, um sicherzustellen, dass dieses auf Ihrem Computer installiert ist.

![Installieren von Google Test](media/cpp-google-component.png)

## <a name="add-a-google-test-project-to-the-solution"></a>Hinzufügen eines Google Test-Projekts zur Projektmappe
1. Klicken Sie im **Projektmappen-Explorer** erst mit der rechten Maustaste auf den Knoten „Projektmappe“ und anschließend mit der Linken auf **Hinzufügen** > **Neues Projekt**.
2. Klicken Sie im linken Bereich erst auf **Visual C++** > **Test** und dann auf **Google Test Project** (Google Test-Projekt) im mittleren Bereich.
3. Benennen Sie das Testprojekt, und klicken Sie auf **OK**.

![Neues Google Test-Projekt](media/cpp-gtest-new-project.png)

## <a name="configure-the-test-project"></a>Konfigurieren des Testprojekts
Im Dialogfeld **Testprojektkonfiguration**, das Ihnen angezeigt wird, können Sie das Projekt auswählen, das Sie testen möchten. Wenn Sie ein Projekt auswählen, fügt Visual Studio einen Verweis auf das ausgewählte Projekt hinzu. Wenn Sie kein Projekt auswählen, müssen Sie manuell Verweise auf das Projekt hinzufügen, das Sie testen möchten. Bei der Auswahl zwischen statischer und dynamischer Verknüpfung mit den Google Test-Binärdateien müssen die gleichen Aspekte wie bei jedem anderen C++-Programm beachtet werden. Weitere Informationen finden Sie unter [DLLs in Visual C++](/cpp/build/dlls-in-visual-cpp).

 ![Konfigurieren von Google Test-Projekten](media/cpp-gtest-config.png)

## <a name="set-additional-options"></a>Festlegen von zusätzlichen Optionen
Klicken Sie im Hauptmenü auf **Extras** > **Optionen** > **Testadapter für Google Test**, um zusätzliche Optionen festzulegen. Weitere Informationen zu diesen Einstellungen finden Sie in der Google Test-Dokumentation.

 ![Google Test-Projekteinstellungen](media/cpp-gtest-settings.png)

## <a name="add-include-directives"></a>Hinzufügen von include-Anweisungen
Fügen Sie Ihrer *CPP*-Testdatei alle erforderlichen `#include`-Anweisungen hinzu, um die Typen und Funktionen Ihres Programms für den Testcode anzuzeigen. In der Regel befindet sich das Programm in der Ordnerhierarchie eine Ebene darüber. Wenn Sie `#include "../"` eingeben, wird ein IntelliSense-Fenster angezeigt, und Sie können den vollständigen Pfad zur Headerdatei auswählen.

![Hinzufügen von #include-Direktiven](media/cpp-gtest-includes.png)

## <a name="write-and-run-tests"></a>Schreiben und Ausführen von Tests
Sie können nun Google Test-Tests schreiben und ausführen. Weitere Informationen über die Testmakros finden Sie unter [Google Test primer (Einführung in Google Test)](https://github.com/google/googletest/blob/master/googletest/docs/primer.md). Weitere Informationen zum Ermitteln, Ausführen und Gruppieren Ihrer Tests mithilfe des **Test-Explorers** finden Sie unter [Ausführen von Komponententests mit dem Test-Explorer](run-unit-tests-with-test-explorer.md).

## <a name="see-also"></a>Siehe auch
[Schreiben von Komponententests für C/C++](writing-unit-tests-for-c-cpp.md)











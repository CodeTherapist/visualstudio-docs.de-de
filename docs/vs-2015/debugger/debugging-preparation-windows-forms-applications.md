---
title: 'Vorbereitung zum Debuggen: Windows Forms-Anwendungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [J#], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4997aa5f184fb5d6f0e9a3ccd08a9d829c26a0cc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765627"
---
# <a name="debugging-preparation-windows-forms-applications"></a>Vorbereitung zum Debuggen: Windows Forms-Anwendungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die Windows Forms-Projektvorlage erstellt eine Windows Forms-Anwendung. Das Debuggen dieses Anwendungstyps in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ist einfach. Weitere Informationen finden Sie unter [Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Wenn Sie ein Windows Forms-Projekt mit der Projektvorlage erstellen, werden die erforderlichen Einstellungen für die Debug- und Releasekonfigurationen automatisch durch [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] festgelegt. Diese Einstellungen können ggf. geändert werden. Diese Einstellungen können geändert werden, der  **\<Projektname > Eigenschaftenseiten** (Dialogfeld) (**Mein Projekt** in Visual Basic).  
  
 Weitere Informationen finden Sie unter [empfohlene Eigenschafteneinstellungen](../debugger/managed-debugging-recommended-property-settings.md).  
  
 Eine zusätzlich empfohlene Eigenschafteneinstellung wird in der folgenden Tabelle angezeigt.  
  
### <a name="configuration-properties-in-debug-tab"></a>Konfigurationseigenschaften auf der Registerkarte "Debuggen"  
  
|**Eigenschaftenname**|**Einstellung**|  
|-----------------------|-----------------|  
|**Startaktion**|– Legen Sie auf **Startprojekt,** den meisten Fällen. Legen Sie auf **externes Programm starten** sollten Sie eine andere ausführbare Datei starten beim Starten des Debugvorgangs (in der Regel für das Debuggen von DLLs).|  
  
 Sie können Windows Forms-Anwendungen aus [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] heraus debuggen oder durch das Anfügen zu einer bereits laufenden Anwendung. Weitere Informationen zum Anfügen, finden Sie unter [Anfügen an ausgeführte Prozesse](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>So debuggen Sie eine C#-, F#- oder Visual Basic-Windows Forms-Anwendung  
  
1. Öffnen Sie das Projekt in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
2. Erstellen Sie Haltepunkte nach Bedarf.  
  
    Da Windows Forms-Anwendungen ereignisgesteuert sind, gehen die Haltepunkte entweder in den Ereignishandlercode oder in Methoden, die vom Ereignishandlercode aufgerufen werden. Typische Ereignisse, in denen Haltepunkte platziert werden sollte, sind z. B. folgende:  
  
   1. Einem Steuerelement zugeordnete Ereignisse, z. B. Klicken, Drücken der Eingabetaste usw.  
  
   2. Ereignisse, die dem Start bzw. Herunterfahren der Anwendung zugeordnet sind, z. B. Laden, Aktivierung usw.  
  
   3. Fokusereignisse und Validierungsereignisse.  
  
      Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](http://msdn.microsoft.com/library/6514e530-c6b8-489c-a8d2-eda7b7072701).  
  
3. Auf der **Debuggen** Menü klicken Sie auf **starten**.  
  
4. Debuggen Sie mit die vorgestellten [Debugger – Grundlagen](../debugger/debugger-basics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von verwaltetem Code](../debugger/debugging-managed-code.md)   
 [C#-, F#- und Visual Basic-Projekttypen](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Vorgehensweise: Festlegen von Debug- und Releasekonfigurationen](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Project Settings for  C# Debug Configurations (Projekteinstellungen für C#-Debugkonfigurationen)](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Project Settings for a Visual Basic Debug Configuration (Projekteinstellungen für eine Visual Basic-Debugkonfiguration)](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Fügen an laufende Prozesse an](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](http://msdn.microsoft.com/library/627df1e9-b254-41af-bbac-9a4f02810c54)




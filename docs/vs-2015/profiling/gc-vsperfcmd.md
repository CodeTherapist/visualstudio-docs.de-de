---
title: GC (VSPerfCmd) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c9a57a8fa4b0610cc3cceb00e09749a2e5b077e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51727868"
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die Option **GC** aktiviert das Erfassen von Daten zur Speicherbelegung durch .NET-Framework und zur Objektlebensdauer. Die Option **GC** kann nur gemeinsam mit der Sampling-Profilerstellungsmethode und der Option **Launch** (Start) verwendet werden.  
  
 Wenn Sie die Option **GC** verwenden, ist der VSPerfClrEnv-Befehl **/sampleon** nicht erforderlich.  
  
 Wenn keine Parameter angegeben sind, oder wenn der Parameter **Speicherbelegung** angegeben ist, werden nur Daten zur Speicherbelegung durch .NET-Framework erfasst. Wenn der Parameter **Lebensdauer** angegeben ist, werden sowohl Daten zur Speicherbelegung durch .NET-Framework als auch zur Objektlebensdauer erfasst.  
  
## <a name="syntax"></a>Syntax  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parameter  
 **Speicherbelegung**  
 Standard. Erfasst Daten zur Speicherbelegung durch .NET-Framework.  
  
 **Lebensdauer**  
 Erfasst sowohl Daten zur Speicherbelegung durch .NET-Framework als auch zur Lebensdauer von .NET Framework-Objekten.  
  
## <a name="required-options"></a>Erforderliche Optionen  
 Die Option **GC** kann nur mit der Option **Launch** (Start) verwendet werden.  
  
 **Starten:** `AppName`  
 Startet die angegebene Anwendung und beginnt die Profilerstellung mit der Samplingmethode.  
  
## <a name="example"></a>Beispiel  
 Mithilfe des folgenden Beispiels wird eine Anwendung gestartet und Daten zur Speicherbelegung durch .NET-Framework erfasst.  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)




---
title: Console | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 512e04bc3da16c57a97536e02a12475182746e56
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51786677"
---
# <a name="console"></a>Konsole
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die VSPerfCmd.exe-Option **Console** startet die angegebene Anwendung in einem neuen Eingabeaufforderungsfenster. **Console** kann nur mit der VSPerfCmd-Option **Launch** verwendet werden. Wenn die Anwendung keine Befehlszeilenanwendung ist, hat **Console** keine Auswirkungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>Parameter  
 Keiner  
  
## <a name="required-options"></a>Erforderliche Optionen  
 **Console** kann nur in einer Befehlszeile angegeben werden, die auch die Option **Launch** enthält.  
  
 **Starten:** `AppName`  
 Startet den Profiler und die von `AppName` festgelegten Anwendungen.  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)




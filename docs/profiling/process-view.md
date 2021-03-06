---
title: Prozessansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4924f38bf893bc17a599802d9962d664da01c26d
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254523"
---
# <a name="process-view"></a>Prozessansicht
Die Prozessansicht zeigt Profilerstellungsdaten für die Prozesse und Threads, die während der Profilerstellung ausgeführt wurden.  
  
 Prozesse werden nach Namen aufgelistet. Threads werden als untergeordnete Knoten des Prozesses aufgeführt, in dem sie erstellt wurden. Threads werden von der Funktion benannt, die den Thread gestartet hat, oder von der Bezeichnung **[ntdll.dll]**, falls keine Symbole verfügbar sind.  
  
 Klicken Sie zum Hinzufügen oder Entfernen von Spalten mit der rechten Maustaste in die Ansicht, und wählen Sie anschließend **Spalten hinzufügen/entfernen** aus. Zusätzlich können Sie die Daten durch Klicken auf einen Spaltennamen sortieren. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Spalten in der Berichtsansicht der Profilerstellungstools](../profiling/how-to-customize-report-view-columns.md).  
  
 Die Spalten der Prozessansicht sind die gleichen Spalten wie für die Daten, die mithilfe der Sampling- und Instrumentierungsmethoden generiert wurden, sowie für Daten, die .NET-Speicherdaten enthalten. In der folgenden Tabelle sind die Spaltenwerte beschrieben.  
  
|Spalte|Beschreibung |  
|------------|-----------------|  
|**Eindeutige ID**|Ein durch die Profilerstellung generierter Bezeichner, der für den Prozess oder Thread eindeutig ist.|  
|**ID**|Der von einem System generierte Bezeichner für den Prozess oder Thread.|  
|**Name**|Der Name des Prozesses oder Threads.|  
|**Anfangszeit**|Die Anzahl von Millisekunden oder Prozessorzyklen vom Anfang der Profilerstellung zum Anfang des Prozesses oder Threads.|  
|**Endzeit**|Die Anzahl von Millisekunden oder Prozessorzyklen vom Anfang der Profilerstellung bis zum Anfang des Prozesses oder Threads.|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenansichten der Samplingmethode](../profiling/profiler-sampling-method-data-views.md)   
 [Instrumentation method data views (Datenansichten der Instrumentierungsmethode)](../profiling/instrumentation-method-data-views.md)   
 [.NET-Arbeitsspeicherdatenansichten](../profiling/dotnet-memory-data-views.md)
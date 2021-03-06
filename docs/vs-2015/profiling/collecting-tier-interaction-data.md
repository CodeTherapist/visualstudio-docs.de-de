---
title: Erfassen von Ebeneninteraktionsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31e2d46992b48b987966bac7d7dc68787f4016c2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51761191"
---
# <a name="collecting-tier-interaction-data"></a>Erfassen von Ebeneninteraktionsdaten
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die Profilerstellung für Ebeneninteraktion stellt weitere Informationen zu den Ausführungszeiten der Funktionen von Anwendungen mit mehreren Ebenen, die über ADO.NET-Dienste mit Datenbanken kommunizieren, bereit. Es werden nur Daten für synchrone Funktionsaufrufe gesammelt.  
  
 **Visual Studio-Editionen**  
  
 Profilerstellungsdaten für die Ebeneninteraktion können mit Visual Studio Ultimate, Visual Studio Premium oder Visual Studio Professional gesammelt werden. Allerdings können Profilerstellungsdaten für die Ebeneninteraktion nur in VS Ultimate und VS Premium angezeigt werden.  
  
 **Windows 8 und Windows Server 2012**  
  
 Um Ebeneninteraktionsdaten für Windows 8-Desktop-Apps und Windows Server 2012-Apps zu erfassen, müssen Sie die Instrumentierungsmethode verwenden. Sie können Ebeneninteraktionsdaten nicht für Windows Store-Apps sammeln. Siehe [Profilerstellungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Sie können Ebeneninteraktionsdaten in alle Profilerstellungsmethoden einer anderen unterstützten Version von Windows einschließen.  
  
 **Leistungs-Assistent**  
  
 Aufgrund eines Fehlers im Leistungs-Assistenten müssen Sie die Option zur Erfassung von Ebeneninteraktionsdaten einer Profilerstellung im Leistungs-Explorer hinzufügen. Sie müssen das Projekt, die ausführbare Datei oder die Website außerdem dem Zielknoten des Leistungs-Explorers hinzufügen.  
  
### <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>So fügen Sie einer Profilerstellung Ebeneninteraktionsdaten mithilfe der Eigenschaftenseiten der Leistungssitzung hinzu  
  
1.  Wählen Sie im Leistungs-Explorer im Kontextmenü **Eigenschaften** aus.  
  
2.  Wählen Sie die Seite **Ebeneninteraktionen** aus, und aktivieren Sie das Kontrollkästchen **Profilerstellung für Ebeneninteraktion aktivieren**.  
  
3.  Wählen Sie im Leistungs-Explorer den Knoten **Ziele** aus, und geben Sie das Projekt, die ausführbare Datei oder die Website an, für das/die Sie ein Profil erstellen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Ansicht "Ebeneninteraktionen"](../profiling/tier-interactions-view.md)




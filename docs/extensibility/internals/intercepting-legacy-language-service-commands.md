---
title: Abfangen von Befehlen von Legacysprachdiensten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 669d03043ad36ad1e96084cb4cc8833ab20f0998
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49832857"
---
# <a name="intercepting-legacy-language-service-commands"></a>Abfangen von Befehlen von Legacysprachdiensten
Mit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], dass die Konstante Glied Befehlen von legacysprachdiensten, die andernfalls von die Textansicht behandelt würden. Dies ist nützlich für die sprachspezifisches Verhalten, die nicht die Textansicht verwaltet. Sie können diese Befehle abfangen, durch das Hinzufügen von ein oder mehrere-Befehlsfilter der Textansicht aus den Sprachdienst.  
  
## <a name="getting-and-routing-the-command"></a>Abrufen und den Befehl Routing  
 Ein Befehlsfilter ist ein <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> -Objekt, das bestimmte Zeichenfolgen oder die wichtigsten Befehle überwacht. Sie können mehr als ein Befehlsfilter mit einer einzelnen Textansicht zuordnen. Jede Textansicht verwaltet eine Befehlsketten-Filter. Nachdem Sie einen neuen Befehlsfilter erstellen, fügen Sie den Filter auf die Kette für die Ansicht entsprechenden Text hinzu.  
  
 Rufen Sie die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> Methode für die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Befehlsfilter der Kette hinzu. Beim Aufruf <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] gibt einen anderen Befehl Filtern, können Sie die Befehle, die Ihre Befehlsfilter nicht behandelt wird übergeben.  
  
 Sie haben die folgenden Optionen für die Behandlung von Befehlen aus:  
  
- Behandeln Sie den Befehl aus, und klicken Sie dann übergeben Sie den Befehl an den nächsten Befehlsfilter, in der Kette.  
  
- Behandeln Sie den Befehl aus, und übergeben Sie den Befehl an den nächsten Befehlsfilter nicht.  
  
- Behandeln Sie den Befehl nicht, aber übergeben Sie den Befehl an den nächsten Befehlsfilter.  
  
- Ignorieren Sie den Befehl. Nicht im aktuellen Filter behandelt, und übergeben Sie ihn nicht an den nächsten Filter.  
  
  Informationen über die Befehle der Sprachdienst behandeln sollten, finden Sie unter [wichtige Befehle für Sprachdienstfilter](../../extensibility/internals/important-commands-for-language-service-filters.md).
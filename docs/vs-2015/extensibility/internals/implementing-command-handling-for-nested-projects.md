---
title: Implementieren der Befehlsbehandlung für geschachtelte Projekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 113cc2c061b008892921aac348f3eb56a7bef0d3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51742570"
---
# <a name="implementing-command-handling-for-nested-projects"></a>Implementieren der Befehlsbehandlung für geschachtelte Projekte
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die IDE Befehle, die durchlaufen werden kann übergeben, die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> und <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Schnittstellen für geschachtelte Projekte oder übergeordnete Projekte filtern oder überschreiben Sie die Befehle können.  
  
> [!NOTE]
>  Nur Befehle, die normalerweise behandelt, indem das übergeordnete Projekt können gefiltert werden. Befehle wie **erstellen** und **bereitstellen** erfolgt, die mit die IDE kann nicht gefiltert werden.  
  
 Die folgenden Schritte beschreiben den Prozess zum Implementieren der Befehlsbehandlung.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-implement-command-handling"></a>Zum Implementieren der Befehlsbehandlung  
  
1. Wenn der Benutzer eines geschachtelten Projekts oder eines Knotens in einem geschachtelten Projekt auswählt:  
  
   1. Die IDE-Aufrufe der <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Methode.  
  
      - oder -  
  
   2. Wenn der Befehl in einem Fenster "Aufrufhierarchie", wie z. B. den Befehl im Kontextmenü im Projektmappen-Explorer, stammt die IDE Ruft die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> Methode für das Projekt des übergeordneten.  
  
2. Das übergeordnete Projekt sehen zum Übergeben von Parametern an `QueryStatus`, z. B. `pguidCmdGroup` und `prgCmds`, um zu bestimmen, ob das übergeordnete Projekt die Befehle filtern soll. Wenn das übergeordnete Projekt implementiert wird, um Befehle zu filtern, sollten sie Folgendes festlegen:  
  
   ```  
   prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
   // make sure it is disabled  
   prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
   ```  
  
    Das übergeordnete Projekt zurückgeben sollte `S_OK`.  
  
    Wenn das übergeordnete Projekt den Befehl nicht gefiltert werden, sollte es nur zurückgeben `S_OK`. In diesem Fall leitet die IDE automatisch den Befehl ab, auf das untergeordnete Projekt.  
  
    Das übergeordnete Projekt muss nicht den Befehl an das untergeordnete Projekt weitergeleitet. Die IDE führt diese Aufgabe...  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Befehle, Menüs und Symbolleisten](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [Schachteln von Projekten](../../extensibility/internals/nesting-projects.md)


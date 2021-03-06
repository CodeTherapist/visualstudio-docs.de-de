---
title: IEnumDebugCodeContexts2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugCodeContexts2
helpviewer_keywords:
- IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 484ad1b1a084d40fe86c3ba36c90fdbc5cc4effa
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51773833"
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Schnittstelle Listet die Codekontexte auf, mit der Debugsitzung oder einem bestimmten Programm oder Dokument zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle, um eine Liste von Kontexten, Code für eine Position im bestimmten Text in einem Programm oder eine Liste von Kontexten, Code für ein bestimmtes Dokumentkontext darstellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Rufen Sie [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) beim Abrufen der diese Schnittstelle, die eine Liste von Kontexten, Code für eine bestimmte Textposition im Quelldokument eines Programms darstellt.  
  
 Rufen Sie [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md) beim Abrufen der diese Schnittstelle, die eine Liste mit allen Code-Kontexten in einem bestimmten Quelldokument darstellt.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumDebugCodeContexts2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|Ruft eine angegebene Anzahl von Kontexten, Code in einer Enumerationsfolge ab.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|Überspringt eine angegebene Anzahl von Kontexten, Code in einer Enumerationsfolge.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|Setzt eine Enumerationsfolge auf den Anfang zurück.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle Enumerator enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|Ruft die Anzahl von Kontexten, Code in einen Enumerator ab.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio-Aufrufe [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) zum Auffüllen einer Liste von Kontexten, Code wahlweise kann der Benutzer aus, wenn die nächste Anweisung festlegen oder die Disassemblierung für eine Quelldatei angezeigt. Mehrere Codekontexte können beispielsweise auftreten, wenn mehrere Instanzen einer Vorlage im C++-Stil vorhanden sind.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)


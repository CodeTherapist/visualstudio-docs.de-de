---
title: IDebugMessageEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMessageEvent2
helpviewer_keywords:
- IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d0cb1f270d3d3ae77c43ea89fba5b7483e80412
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116167"
---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
Diese Schnittstelle wird durch die Debugging-Modul (DE) verwendet, zum Senden einer Nachricht zu Visual Studio, die eine Antwort vom Benutzer erforderlich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugMessageEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die DE implementiert diese Schnittstelle zum Senden einer Nachricht zu Visual Studio, die eine Antwort des Benutzers erfordert. Die [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) -Schnittstelle muss auf das gleiche Objekt wie diese Schnittstelle implementiert werden. Verwendet die SDM [QueryInterface](/cpp/atl/queryinterface) für den Zugriff auf die `IDebugEvent2` Schnittstelle.  
  
 Die Implementierung dieser Schnittstelle muss Visual Studio-Aufruf der kommunizieren [SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) de. Z. B. Dies erreichen Sie mit einer Nachricht an die DE Meldungsbehandlung-Thread gesendet oder das Objekt implementiert diese Schnittstelle konnte enthalten einen Verweis auf die DE und mit der übergebenen Antwort ein Rückruf de `IDebugMessageEvent2::SetResponse`.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Die DE erstellt und sendet diese Ereignisobjekt eine Meldung an den Benutzer angezeigt, die eine Antwort erforderlich sind. Das Ereignis wird gesendet, mit der [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) Rückruffunktion, die durch die SDM bereitgestellt wird, wenn es an das derzeit debuggte Programm angefügt ist.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugMessageEvent2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|Ruft die Meldung ab, die angezeigt werden.|  
|[SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|Legt die Antwort fest, sofern vorhanden, aus der MessageBox.|  
  
## <a name="remarks"></a>Hinweise  
 Die DE wird diese Schnittstelle verwenden, wenn eine bestimmte Reaktion des Benutzers für eine bestimmte Nachricht erforderlich ist. Wenn DE Fehlermeldung "Zugriff verweigert" nach einem Versuch, Remote an ein Programm angefügt wird, sendet der DE jeweilige Nachricht z. B. zu Visual Studio in einem `IDebugMessageEvent2` Ereignis "mit" Message Box-Stil `MB_RETRYCANCEL`. Dies ermöglicht es dem Benutzer zu wiederholen oder Abbrechen anzufügen.  
  
 Die DE gibt an, wie diese Meldung behandelt werden, indem Sie gemäß den Konventionen der Win32-Funktion `MessageBox` (finden Sie unter [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) Einzelheiten).  
  
 Verwenden der [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) Schnittstelle zum Senden von Nachrichten an Visual Studio, die nicht über eine Antwort des Benutzers erfordern.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
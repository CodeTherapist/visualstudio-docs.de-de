---
title: IDebugBreakpointBoundEvent2::EnumBoundBreakpoints | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
helpviewer_keywords:
- IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
ms.assetid: 1f588feb-522e-488d-be92-7bc19b9e3688
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 514e34830fde908b9cea0e4f213ae200d31ec678
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49926890"
---
# <a name="idebugbreakpointboundevent2enumboundbreakpoints"></a>IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
Erstellt einen Enumerator von Haltepunkten, die auf dieses Ereignis gebunden wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumBoundBreakpoints(   
   IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int EnumBoundBreakpoints(   
   out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Gibt eine [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) -Objekt, das Listet alle Haltepunkte von diesem Ereignis gebunden.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`. Gibt `S_FALSE` treten keine gebundene Haltepunkte; andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Liste der gebundene Haltepunkte für diese Grenze auf dieses Ereignis ist und möglicherweise nicht die gesamte Liste der Haltepunkte ein ausstehender Haltepunkt gebunden. Rufen Sie zum Abrufen einer Liste aller Haltepunkte, die an ein ausstehender Haltepunkt gebunden der [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) -Methode zum Abrufen von der zugeordneten [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) Objekt und rufen Sie dann die [ EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md) -Methode zum Abrufen einer [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) Objekt, das die gebundene Haltepunkte für den ausstehenden Haltepunkt enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Implementierung dieser Methode für eine **CBreakpointSetDebugEventBase** -Objekt, das macht die [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) Schnittstelle.  
  
```cpp  
STDMETHODIMP CBreakpointSetDebugEventBase::EnumBoundBreakpoints(  
    IEnumDebugBoundBreakpoints2 **ppEnum)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppEnum )  
    {  
        if ( m_pEnumBound )  
        {  
            hRes = m_pEnumBound->Clone(ppEnum);  
  
            if ( EVAL(S_OK == hRes) )  
                (*ppEnum)->Reset();  
        }  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
---
title: IDebugPortSupplier3::EnumPersistedPorts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1bb9348c0dfae477d0c306868991acd13e7a487
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49856053"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
Diese Methode ruft ein Objekt, das ermöglicht die Enumeration, der die Liste der persistenten Ports ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `PortNames`  
 [in] Ein [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) Struktur, die eine Liste der Anschlussnamen gesucht und zurückgegeben, die zwischen der beibehaltenen Ports enthält. Nur die beibehaltenen Ports mit diesen Namen werden zurückgegeben.  
  
 `ppEnum`  
 [out] Ein Objekt, implementiert die [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Persistente Ports werden geladen, wenn ein portanbieters instanziiert und gespeichert, wenn die anschlusslieferant zerstört wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)
---
title: IDebugProcess3::GetDebugReason | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::GetDebugReason
helpviewer_keywords:
- IDebugProcess3::GetDebugReason
ms.assetid: f23fbabc-8b18-4278-bebf-4cdc7091513c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 60b664680c806f5553e45854a6e678befac952fb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822229"
---
# <a name="idebugprocess3getdebugreason"></a>IDebugProcess3::GetDebugReason
Diese Methode gibt den Grund, dass der Prozess zum Debuggen gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDebugReason(  
   DEBUG_REASON* pReason  
);  
```  
  
```csharp  
int GetDebugReason(  
   out enum_DEBUG_REASON pReason  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pReason`  
 [out] Gibt einen Wert aus der [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md) Enumeration.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls gibt den Fehlercode zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md)
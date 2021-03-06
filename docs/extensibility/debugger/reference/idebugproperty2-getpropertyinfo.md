---
title: IDebugProperty2::GetPropertyInfo | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetPropertyInfo
helpviewer_keywords:
- IDebugProperty2::GetPropertyInfo
ms.assetid: 39d6e942-df72-4c84-a5d9-a386d112714c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 80f1f35e8699c04101936bcfa31abfdde751a236
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49823098"
---
# <a name="idebugproperty2getpropertyinfo"></a>IDebugProperty2::GetPropertyInfo
Ruft die [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) -Struktur, die eine Eigenschaft beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPropertyInfo (   
   DEBUGPROP_INFO_FLAGS dwFields,  
   DWORD                nRadix,  
   DWORD                dwTimeout,  
   IDebugReference2**   rgpArgs,  
   DWORD                dwArgCount,  
   DEBUG_PROPERTY_INFO* pPropertyInfo  
);  
```  
  
```cpp  
int GetPropertyInfo (   
   enum_DEBUGPROP_INFO_FLAGS dwFields,  
   uint                      nRadix,  
   uint                      dwTimeout,  
   IDebugReference2[]        rgpArgs,  
   uint                      dwArgCount,  
   DEBUG_PROPERTY_INFO[]     pPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwFields`  
 [in] Eine Kombination von Werten aus der [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) Enumeration, der angibt, welche Felder sind in ausgefüllt werden, müssen die `pPropertyInfo` Struktur.  
  
 `nRadix`  
 [in] Die Basis bei der Formatierung von numerischen Informationen verwendet werden.  
  
 `dwTimeout`  
 [in] Gibt die maximale Zeit in Millisekunden, warten Sie vor der Rückgabe dieser Methode an. Verwendung `INFINITE` für Warten ohne Timeout.  
  
 `rgpArgs`  
 [in, out] Für die zukünftige Verwendung reserviert. Legen Sie auf einen null-Wert.  
  
 `dwArgCount`  
 [in] Für die zukünftige Verwendung reserviert. Legen Sie auf 0 (null).  
  
 `pPropertyInfo`  
 [out] Ein [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) -Struktur, die mit der Beschreibung der Eigenschaft gefüllt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`; gibt andernfalls den Fehlercode zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
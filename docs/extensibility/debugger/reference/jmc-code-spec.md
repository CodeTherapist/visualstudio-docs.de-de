---
title: JMC_CODE_SPEC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b24c052bc3345443e8bcbe474f881906f420a74c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49821707"
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
Diese Struktur wird verwendet, die JustMyCode-Informationen für ein Modul festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _JMC_CODE_SPEC {  
   BOOL fIsUserCode;  
   BSTR bstrModuleName;  
} JMC_CODE_SPEC;  
```  
  
```csharp  
public struct JMC_CODE_SPEC {  
   public int    fIsUserCode;  
   public string bstrModuleName;  
};  
```  
  
## <a name="members"></a>Member  
 fIsUserCode  
 Ungleich 0 (`TRUE`) Wenn das Modul ist, Benutzercode; berücksichtigt werden, andernfalls NULL (`FALSE`) ist das Modul als externer Code behandelt werden und nicht debuggt werden.  
  
 bstrModuleName  
 Der Name des betreffenden Moduls.  
  
## <a name="remarks"></a>Hinweise  
 Diese Struktur wird als eine Liste dieser Strukturen zu übergeben, die die [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen und Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)
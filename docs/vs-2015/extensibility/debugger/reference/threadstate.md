---
title: THREADSTATE | Microsoft-Dokumentation
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
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1bc74c4b893cd7eb9aa389af31780c1b9cc8d35c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51817307"
---
# <a name="threadstate"></a>THREADSTATE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Gibt den Zustand des Threads.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```csharp  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## <a name="members"></a>Member  
 THREADSTATE_RUNNING  
 Gibt an, dass der Thread ausgeführt wird.  
  
 THREADSTATE_STOPPED  
 Gibt an, dass der Thread aufgrund von einem Haltepunkt angehalten wurde.  
  
 THREADSTATE_FRESH  
 Gibt an, dass der Thread erstellt wurde, aber noch nicht Code ausgeführt wird.  
  
 THREADSTATE_DEAD  
 Gibt an, dass der Thread inaktiv ist.  
  
 THREADSTATE_FROZEN  
 Gibt an, dass der Thread gesperrt ist (es kann keine Ausführung ausgeführt werden).  
  
## <a name="remarks"></a>Hinweise  
 Verwendet für die `dwThreadState` Feld der [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)


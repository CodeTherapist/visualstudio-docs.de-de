---
title: BP_UNBOUND_REASON | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1e1e344ff5adb51d118370f81de10ba01c8950e1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49904218"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
Gibt den Grund an, die, den ein Haltepunkt aufgehoben wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>Member  
 BPUR_UNKNOWN  
 Der Grund dafür ist unbekannt.  
  
 BPUR_CODE_UNLOADED  
 Der Code mit dem Haltepunkt wurde entladen.  
  
 BPUR_BREAKPOINT_REBIND  
 Der Haltepunkt wurde an einen anderen Speicherort erneut gebunden wurde. Dies kann auftreten, die nach dem Bearbeiten und Vorgänge fortgesetzt, wenn der Haltepunkt verschoben wird oder wenn der Breakpoint in einer Datei mit einem Pfad gebunden ist, die nicht mehr gültig ist.  
  
 BPUR_ BREAKPOINT_ERROR  
 Der Haltepunkt wird bestimmt, um die Fehler werden, nachdem er gebunden ist. Dies geschieht mit verwalteten Haltepunkte, deren Bedingungen nicht mehr gültig sind.  
  
## <a name="remarks"></a>Hinweise  
 Zurückgegeben von der [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)
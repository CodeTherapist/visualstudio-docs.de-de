---
title: EVALFLAGS90 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 43c8c7dcba7ea1125c031f0cc64a902d88f67017
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49849424"
---
# <a name="evalflags90"></a>EVALFLAGS90
Listet die gültigen Werte für die Flags, die Auswertung des Ausdrucks steuern. Diese Enumeration erweitert die [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) Enumeration.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 EVAL90_RETURNVALUE  
 Gibt an, dass der Rückgabewert, sofern vorhanden, ausgewertet werden.  
  
 EVAL90_NOSIDEEFFECTS  
 Gibt an, dass Nebenwirkungen nicht zugelassen werden.  
  
 EVAL90_ALLOWBPS  
 Gibt die für Haltepunkte wird beendet.  
  
 EVAL90_ALLOWERRORREPORT  
 Gibt an, Fehlerberichte an den Host, zulässig sein soll. In erster Linie verwendet für die Auswertung des Ausdrucks im Skript in Internet Explorer.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 Erzwingt, dass Funktionen wie Adressen, anstelle von Aufrufen der Funktion ausgewertet werden soll.  
  
 EVAL90_NOFUNCEVAL  
 Verhindert, dass Funktion ausgewertet wird. Betrachten Sie beispielsweise die `int` token im Ausdruck `myExpression(int) + 10`. Diese Funktion kann als eine Adresse, aber nicht als Wert ordnungsgemäß ausgewertet werden.  
  
 EVAL90_NOEVENTS  
 Flag, um anzugeben, dass Ereignisse während der Auswertung des Ausdrucks nicht sitzungsbasierter Debug-Manager (SDM) oder die IDE gesendet werden sollen.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Ermöglicht die ausdrucksauswertung zur Entwurfszeit.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Ermöglicht implizite Variable erstellen.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Erzwingt die Auswertung sofort durchgeführt. Dies ist nützlich, wenn eine Anforderung, z. B. eine benutzeranforderung zu verarbeiten.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
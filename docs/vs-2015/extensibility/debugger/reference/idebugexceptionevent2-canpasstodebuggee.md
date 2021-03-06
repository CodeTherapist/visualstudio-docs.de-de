---
title: IDebugExceptionEvent2::CanPassToDebuggee | Microsoft-Dokumentation
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
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 519a1077bd9f090f733b24dc5e127089613d5ddf
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51722140"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bestimmt, ob die Debug-Engine (DE) die Möglichkeit unterstützt, übergeben diese Ausnahme an die Anwendung gedebuggt wird, wenn die Ausführung fortsetzt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` (die Ausnahme kann an das Programm übergeben werden) oder `S_FALSE` (die Ausnahme kann nicht auf übergeben werden).  
  
## <a name="remarks"></a>Hinweise  
 Die DE muss es sich um eine Standardaktion für die Übergabe an die zu debuggende Komponente verfügen. Die IDE wird möglicherweise die [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) Ereignis, und rufen die [Weiter](../../../extensibility/debugger/reference/idebugprocess3-continue.md) -Methode ohne Aufruf der `CanPassToDebuggee` Methode. Aus diesem Grund müssen die DE Standardfall übergeben Sie die Ausnahme auf, oder nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)


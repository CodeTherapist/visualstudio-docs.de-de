---
title: IDebugProcessEx2::AddImplicitProgramNodes | Microsoft-Dokumentation
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
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b416fdfd3c3a08d028bb01945f2ceb02ae5f8e3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733584"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Methode fügt einen Programm-Knoten für jede Debug-Engine (DE) angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```csharp  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `guidLaunchingEngine`  
 [in] Die `GUID` von einer bereitgestellten Kompatibilitätsrichtlinie, die verwendet werden soll, um Programme zu starten (und wird davon ausgegangen, dass eine eigene Anwendung Knoten hinzufügen).  
  
 `rgguidSpecificEngines`  
 [in] Array von `GUID`s DEs, welches Programm Knoten hinzugefügt werden.  
  
 `celtSpecificEngines`  
 [in] Die Anzahl der `GUID`s in der `rgguidSpecificEngines` Array.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 [Programmieren von Knoten](../../../extensibility/debugger/program-nodes.md) hinzugefügt werden für jede DE in aufgeführt `rgguidSpecificEngines`– mit Ausnahme der starten-Engine (wie in `guidLaunchingEngine`), dieser wird angenommen, einen eigene Anwendung-Knoten hinzufügen, wenn sie ein Programm gestartet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Programmknoten](../../../extensibility/debugger/program-nodes.md)


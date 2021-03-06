---
title: IDebugProgramPublisher2::PublishProgram | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b0ac385eaff1344d21b47e902e7c76d7f4c39343
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49869756"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
Auf diese Weise wird ein Programm für Debug-Engines (DEs) und sitzungsbasierter Debug-Manager.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```csharp  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Engines`  
 [in] Ein Array von GUIDs für DEs, die gestartet oder angehängt werden, um dieses Programm kann.  
  
 `szFriendlyName`  
 [in] Der Anzeigename für das Programm (Dies wird in Menüs oder dem Benutzer angezeigten Dialogfelder angezeigt).  
  
 `pDebuggeeInterface`  
 [in] `IUnknown` Schnittstelle für das Programm (dieser Wert wird als ein Cookie verwendet, um die Anwendung eindeutig zu identifizieren, der gleiche Wert wird verwendet, das Programm "Veröffentlichung")  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Um ein Programm nicht mehr für das Debuggen verfügbar machen, rufen Sie [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)
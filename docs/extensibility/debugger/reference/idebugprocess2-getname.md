---
title: IDebugProcess2::GetName | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::GetName
helpviewer_keywords:
- IDebugProcess2::GetName
ms.assetid: a2f66ab5-53e5-4cdc-a1b5-3b8afa8ee646
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 06b4d22a0d15a3e600afa286abd1b86756c61c85
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49926279"
---
# <a name="idebugprocess2getname"></a>IDebugProcess2::GetName
Ruft ab, der Titel, der Anzeigename oder der Dateiname des Prozesses.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName(   
   GETNAME_TYPE  gnType,  
   BSTR*         pbstrName  
);  
```  
  
```csharp  
int GetName(   
   enum_GETNAME_TYPE  gnType,  
   out string         pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `gnType`  
 [in] Ein Wert aus der [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md) Enumeration, der angibt, welche Art von Namen zurückgegeben.  
  
 `pbstrName`  
 [out] Gibt den Namen des Prozesses.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)
---
title: IDebugSymbolProviderDirect::GetAppIDFromAddress | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetAppIDFromAddress
- GetAppIDFromAddress
ms.assetid: d76a0f36-79c4-4c58-9db3-880b00d11610
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: efb01f1a3cc76cf30f95bd161353233fa33fa1a0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765832"
---
# <a name="idebugsymbolproviderdirectgetappidfromaddress"></a>IDebugSymbolProviderDirect::GetAppIDFromAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Ruft den Bezeichner der Anwendungsdomäne Wenn Sie die debugadresse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetAppIDFromAddress(  
   IDebugAddress* pAddress,  
   DWORD*         pAppID  
);  
```  
  
```csharp  
int GetAppIDFromAddress(  
   IDebugAddress pAddress,  
   out uint      pAppID  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAddress`  
 [in] Debuggen Sie die Adresse, die durch dargestellt wird die [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) Schnittstelle.  
  
 `pAppID`  
 [out] Der Bezeichner der Anwendungsdomäne.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)


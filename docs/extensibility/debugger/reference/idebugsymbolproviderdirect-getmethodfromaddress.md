---
title: IDebugSymbolProviderDirect::GetMethodFromAddress | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetMethodFromAddress
- GetMethodFromAddress
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8a4f9e99dc1eb0c1cedc6d82690330eb6420098
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49880142"
---
# <a name="idebugsymbolproviderdirectgetmethodfromaddress"></a>IDebugSymbolProviderDirect::GetMethodFromAddress
Ruft Informationen über die Methode an der angegebenen Debug-Adresse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodFromAddress(  
   IDebugAddress* pAddress,  
   GUID*          pGuid,  
   DWORD*         pAppID,  
   _mdToken*      pTokenClass,  
   _mdToken*      pTokenMethod,  
   DWORD*         pdwOffset,  
   DWORD*         pdwVersion  
);  
```  
  
```csharp  
int GetMethodFromAddress(  
   IDebugAddress pAddress,  
   out Guid      pGuid,  
   out uint      pAppID,  
   out uint      pTokenClass,  
   out uint      pTokenMethod,  
   out uint      pdwOffset,  
   out uint      pdwVersion  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAddress`  
 [in] Debuggen Sie die Adresse, die durch dargestellt wird die [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) Schnittstelle.  
  
 `pGuid`  
 [out] Eindeutiger Bezeichner des Moduls.  
  
 `pAppID`  
 [out] Der Bezeichner der Anwendungsdomäne.  
  
 `pTokenClass`  
 [out] Token, die die enthaltende Klasse darstellt.  
  
 `pTokenMethod`  
 [out] Token, die das Modul darstellt.  
  
 `pdwOffset`  
 [out] Ein Offset in Bytes vom Anfang der `pAddress` Parameter.  
  
 `pdwVersion`  
 [out] Die Versionsnummer der Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)
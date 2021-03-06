---
title: IDebugParsedExpression::EvaluateSync | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugParsedExpression::EvaluateSync
helpviewer_keywords:
- IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cdf9fa9057e946d68da9f1e02d5aaf90b34e569a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49931765"
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
Diese Methode wertet den analysierten Ausdruck und wandelt optional das Ergebnis in einen anderen Datentyp.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EvaluateSync(   
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BSTR                  bstrResultType,  
   IDebugProperty2**     ppResult  
);  
```  
  
```csharp  
int EvaluateSync(  
   uint                 dwEvalFlags,   
   uint                 dwTimeout,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   string               bstrResultType,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwEvalFlags`  
 [in] Eine Kombination von [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) Konstanten, die steuern, wie der Ausdruck ausgewertet werden soll.  
  
 `dwTimeout`  
 [in] Gibt die maximale Zeit in Millisekunden, warten Sie vor der Rückgabe dieser Methode an. Verwendung `INFINITE` für Warten ohne Timeout.  
  
 `pSymbolProvider`  
 [in] Die symbolanbieter, ausgedrückt als eine [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) Schnittstelle.  
  
 `pAddress`  
 [in] Der aktuelle Ausführungsort innerhalb einer Methode, ausgedrückt als eine [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) Schnittstelle.  
  
 `pBinder`  
 [in] Der Binder, ausgedrückt als eine [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) Schnittstelle.  
  
 `bstrResultType`  
 [in] Der Typ das Ergebnis sollte in umgewandelt werden. Dieses Argument kann ein null-Wert sein.  
  
 `ppResult`  
 [out] Gibt die [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Schnittstelle, die die Ergebnisse der Auswertung darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Kontexts für die ausdrucksauswertung wird angegeben, durch `pAddress`, wodurch es möglich, um zu bestimmen, die enthaltende Methode, und klicken Sie dann den Wert der Symbole im Ausdruck bestimmen Regeln verwenden die Sprache festlegen des Gültigkeitsbereichs.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)
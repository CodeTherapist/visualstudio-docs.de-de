---
title: IDebugDocumentContext2::Compare | Microsoft-Dokumentation
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
- IDebugDocumentContext2::Compare
helpviewer_keywords:
- IDebugDocumentContext2::Compare
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d440f585cca5b531fbd97cbbfe6b1ff852cec9d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744912"
---
# <a name="idebugdocumentcontext2compare"></a>IDebugDocumentContext2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vergleicht diese Dokumentkontext in ein angegebenes Array von Dokument-Kontexten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Compare(   
   DOCCONTEXT_COMPARE       compare,  
   IDebugDocumentContext2** rgpDocContextSet,  
   DWORD                    dwDocContextSetLen,  
   DWORD*                   pdwDocContext  
);  
```  
  
```csharp  
int Compare(   
   enum_ DOCCONTEXT_COMPARE compare,  
   IDebugDocumentContext2[] rgpDocContextSet,  
   uint                     dwDocContextSetLen,  
   out uint                 pdwDocContext  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `compare`  
 [in] Ein Wert aus der [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md) Enumeration, die den Typ des Vergleichs angibt.  
  
 `rgpDocContextSet`  
 [in] Ein Array von [idebugdocumentcontext2 angegeben](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) Objekte, die darstellen, die dokumentenkontexte, die mit dem verglichen wird.  
  
 `dwDocContextSetLen`  
 [in] Die Länge des Arrays von dokumentenkontexte, verglichen werden soll.  
  
 `pdwDocContext`  
 [out] Gibt den Index in die `rgpDocContextSet` Array mit den ersten Dokumentenkontext, die den Vergleich zu erfüllen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` , wenn eine Übereinstimmung gefunden wurde. Gibt `S_FALSE` , wenn keine Übereinstimmung gefunden wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die [idebugdocumentcontext2 angegeben](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) Objekte, die im Array übergeben werden müssen implementiert werden, indem Sie die gleichen Debug-Engine, die implementiert die `IDebugDocumentContext2` Objekt aufgerufen wird, andernfalls der Vergleich ist ungültig.  
  
## <a name="see-also"></a>Siehe auch  
 [Idebugdocumentcontext2 angegeben](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md)


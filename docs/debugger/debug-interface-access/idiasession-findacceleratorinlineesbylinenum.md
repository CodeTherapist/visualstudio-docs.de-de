---
title: IDiaSession::findAcceleratorInlineesByLinenum | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b90a253baefad62bba205ccbf0fb8b8fff81712d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49917465"
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
Gibt eine Enumeration von Symbolen für Inlineframes, die entsprechen zum Speicherort angegebenen Quelle zurück.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `parent`  
 [in] Ein `IDiaSymbol` , entspricht die Accelerator-Stub-Funktion, die durchsucht werden soll.  
  
 `file`  
 [in] Die `IDiaSourceFile` des Quellspeicherorts.  
  
 `linenum`  
 [in] Die Nummer der Zeile des Quellspeicherorts.  
  
 `colnum`  
 [in] Die Spaltennummer des Quellspeicherorts.  
  
 `ppResult`  
 [out] Ein Zeiger auf ein `IDiaEnumLineNumbers` Schnittstellenzeiger, der mit dem Ergebnis initialisiert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
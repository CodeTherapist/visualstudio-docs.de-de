---
title: DataKind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f2b46e420db8addf19ef8694112058bdb8b2f91
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49867623"
---
# <a name="datakind"></a>DataKind
Gibt an, die bestimmten Bereich eines Datenwerts.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Elements  
 DataIsUnknown  
 Symbol "Daten" kann nicht bestimmt werden.  
  
 DataIsLocal  
 Datenelement ist eine lokale Variable.  
  
 DataIsStaticLocal  
 Datenelement ist eine statische lokale Variable.  
  
 DataIsParam  
 Datenelement ist ein formaler Parameter.  
  
 DataIsObjectPtr  
 Datenelement ist einem Zeiger (`this`).  
  
 DataIsFileStatic  
 Datenelement ist eine Variable im Bereich einer Datei.  
  
 DataIsGlobal  
 Datenelement ist eine globale Variable.  
  
 DataIsMember  
 Datenelement ist eine Objektvariable des Elements.  
  
 DataIsStaticMember  
 Datenelement ist eine statische Klasse-Variable.  
  
 DataIsConstant  
 Datenelement ist ein konstanter Wert.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte in dieser Enumeration werden zurückgegeben, durch die [idiasymbol:: Get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 Header: cvconst.h  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen und Strukturen](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
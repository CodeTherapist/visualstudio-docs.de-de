---
title: SccQueryChanges-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7b3a9454daa0f2e3c5cf91a9dc483afe1f635a1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49915710"
---
# <a name="sccquerychanges-function"></a>SccQueryChanges-Funktion
Diese Funktion Listet die angegebenen Dateien mit Informationen zu Änderungen des Computernamens für jede Datei über eine Callback-Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 "pContext"  
 [in] Der Datenquellen-Steuerelement-Plug-in Kontextzeiger.  
  
 nFiles  
 [in] Anzahl der Dateien im `lpFileNames` Array.  
  
 lpFileNames  
 [in] Array von Dateinamen, zu dem Informationen abgerufen werden soll.  
  
 pfnCallback  
 [in] Rückruffunktion für jedes Dateinamen in der Liste (finden Sie unter [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) Einzelheiten).  
  
 pvCallerData  
 [in] Wert, der unverändert an die Rückruffunktion übergeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Source-Steuerelement-Plug-in-Implementierung dieser Funktion muss einen der folgenden Werte zurückgeben:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SCC_OK|Der Abfragevorgang erfolgreich abgeschlossen wurde.|  
|SCC_E_PROJNOTOPEN|Das Projekt wurde nicht in der quellcodeverwaltung geöffnet.|  
|SCC_E_ACCESSFAILURE|Es wurde ein Problem, das Zugriff auf das Quellcodeverwaltungssystem, möglicherweise aufgrund eines Netzwerk-oder-Konflikte bestehen.|  
|SCC_E_NONSPECIFICERROR|Ein Unbekannter oder allgemeiner Fehler aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Änderungen, die abgefragt wird, die auf den Namespace sind: insbesondere umbenennen, hinzufügen und Entfernen einer Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Quellcodeverwaltungsfunktionen-Plug-in-API](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [Fehlercodes](../extensibility/error-codes.md)
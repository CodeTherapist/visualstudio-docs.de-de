---
title: CvCreateMarkerSeriesWithCodePageA-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 63fe3de8c4322e378f110813ac93fa523f3453ba
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750375"
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA-Funktion
Erstellt Markerreihen für einen angegebenen Anbieter und eine angegebene Codepage. Mit dieser Funktion kann die Codepage für den von Marker-API-ANSI-Funktionen ausgeschriebenen Text explizit angegeben werden. Das Festlegen der Codepage kann in Fällen nützlich sein, in denen die Ablaufverfolgung aufgezeichnet und anschließend auf unterschiedlichen Computern mit unterschiedlichen Gebietsschemas/Sprachen analysiert wird. Standardmäßig wird die von der GetACP()-Funktion zurückgegebene Codepage verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```C  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pProvider`  
 Durch CvInitProvider bereits initialisiertes Anbieterobjekt. Darf nicht NULL sein.  
  
 `pSeriesName`  
 Markerreihenname. Darf nicht NULL sein, aber eine leere Zeichenfolge ist zulässig.  
  
 `nTextCodePage`  
 Gültige Codepage.  
  
 `ppMarkerSeries`  
 Adresse einer Ausgabevariablen, mit der Markerreihenkontext gespeichert wird. Darf nicht NULL sein.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn Markerreihen erfolgreich erstellt wurden, oder Fehlercode, wenn Fehler aufgetreten sind. Prüfen Sie mit den Makros SUCCEEDED bzw. FAILED, ob Fehler vorliegen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** *cvmarkers.h*  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Bibliotheksreferenz](../profiling/cpp-library-reference.md)
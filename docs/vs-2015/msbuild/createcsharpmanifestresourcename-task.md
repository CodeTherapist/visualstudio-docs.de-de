---
title: CreateCSharpManifestResourceName-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 32aa7fdb5779d7ae042e8efa9652f25df70a2754
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247844"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName-Aufgabe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Erstellt einen Manifestnamen im [!INCLUDE[csprcs](../includes/csprcs-md.md)]-Stil aus einem angegebenen RESX-Dateinamen oder aus einer anderen Ressource  
  
## <a name="parameters"></a>Parameter  
 Die folgende Tabelle beschreibt die Parameter der Aufgabe [CreateCSharpManifestResourceName](../msbuild/createcsharpmanifestresourcename-task.md).  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`ManifestResourceNames`|Schreibgeschützter <xref:Microsoft.Build.Framework.ITaskItem>-`[]`-Ausgabeparameter<br /><br /> Die resultierenden Manifestnamen|  
|`ResourceFiles`|Erforderlicher `String` -Parameter.<br /><br /> Der Name der Ressourcendatei, von der der [!INCLUDE[csprcs](../includes/csprcs-md.md)]-Manifestname erstellt werden soll.|  
|`RootNamespace`|Optionaler `String` -Parameter.<br /><br /> Der Stammnamespace der Ressourcendatei, der normalerweise aus der Projektdatei übernommen wird. Kann `null` sein.|  
|`PrependCultureAsDirectory`|Optionaler `Boolean` -Parameter.<br /><br /> Wenn der Wert `true` ist, wird der Name der Kultur als Verzeichnisname unmittelbar vor dem Manifestressourcennamen hinzugefügt. Der Standardwert ist `true`sein.|  
|`ResourceFilesWithManifestResourceNames`|Optionaler schreibgeschützter `String`-Ausgabeparameter<br /><br /> Gibt den Namen der Ressourcendatei zurück, die jetzt den Manifestressourcennamen enthält|  
  
## <a name="remarks"></a>Hinweise  
 Die Aufgabe [CreateVisualBasicManifestResourceName](../msbuild/createvisualbasicmanifestresourcename-task.md) bestimmt den richtigen Manifestressourcennamen, der einer bestimmten RESX- oder einer anderen Ressourcendatei zugewiesen werden soll. Die Aufgabe stellt einen logischen Namen für eine Ressourcendatei bereit und fügt sie dann an einen Ausgabeparameter als Metadatenelement an.  
  
 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)   
 [Aufgabenreferenz](../msbuild/msbuild-task-reference.md)




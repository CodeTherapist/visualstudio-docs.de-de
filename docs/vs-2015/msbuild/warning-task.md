---
title: Warnungsaufgabe | Microsoft-Dokumentation
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
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0447c3803de6845dcfb02a30270cfe9b96b96f0a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213592"
---
# <a name="warning-task"></a>Warning-Aufgabe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Protokolliert während eines Builds eine Warnung, die auf einer ausgewerteten Bedingungsanweisung basiert  
  
## <a name="parameters"></a>Parameter  
 In der folgenden Tabelle werden die Parameter des `Warning`-Tasks beschrieben.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Code`|Optionaler `String` -Parameter.<br /><br /> Der Warncode, der der Warnung zugeordnet werden soll.|  
|`File`|Optionaler `String` -Parameter.<br /><br /> Gibt die relevante Datei an, falls vorhanden. Wenn keine Datei angegeben wird, wird die Datei verwendet, die die Warnungsaufgabe enthält.|  
|`HelpKeyword`|Optionaler `String` -Parameter.<br /><br /> Das Help-Schlüsselwort, das der Warnung zugeordnet wird.|  
|`Text`|Optionaler `String` -Parameter.<br /><br /> Der Warnungstext, den [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] protokolliert, wenn der `Condition`-Parameter `true` ergibt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Warning`-Aufgabe ermöglicht es [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]-Projekten, zu prüfen, ob eine erforderliche Konfiguration oder Eigenschaft vorhanden ist, bevor Sie mit dem nächsten Schritt des Buildvorgangs fortfahren.  
  
 Wenn der `Condition`-Parameter der `Warning`-Aufgabe `true` ergibt, wird der Wert des `Text`-Parameters protokolliert und der Build weiter ausgeführt. Wenn kein `Condition`-Parameter vorhanden ist, wird der Warnungstext protokolliert. Weitere Informationen zur Protokollierung finden Sie unter [Erhalten von Buildprotokollen](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Beispiel  
 Mithilfe des folgenden Codebeispiels können Sie nach Eigenschaften suchen, die in der Befehlszeile festgelegt sind. Wenn keine Eigenschaften festgelegt sind, löst das Projekt ein Warnungsereignis aus und protokolliert den Wert des `Text`-Parameters der `Warning`-Aufgabe.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Warning  
            Text=" The 0 property was not set on the command line."  
            Condition="'$(0)' == ''" />  
        <Warning  
            Text=" The FREEBUILD property was not set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erhalten von Buildprotokollen](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md) (Referenz zum Projektdateischema von MSBuild)




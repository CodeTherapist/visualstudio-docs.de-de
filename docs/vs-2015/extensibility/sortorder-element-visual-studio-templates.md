---
title: SortOrder-Element (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec82bd69257e32afed0ded6d1486324fc370860f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51755623"
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder-Element (Visual Studio-Vorlagen)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Gibt einen Wert an, die zum Anordnen von gegenüber anderen Vorlagen in der gleichen Kategorie, der Vorlage verwendet wird, entsprechend der Anzeige in einem der **neues Projekt** oder **neues Element hinzufügen** Dialogfeld.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<SortOrder >  
  
## <a name="syntax"></a>Syntax  
  
```  
<SortOrder> ... </SortOrder>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Erforderliches Element.<br /><br /> Kategorisiert die Vorlage und definiert, wie diese in den Dialogfeldern **Neues Projekt** oder **Neues Element hinzufügen** angezeigt wird.|  
  
## <a name="text-value"></a>Textwert  
 Ein Textwert ist erforderlich.  
  
 Ein `integer` , das den Sortierreihenfolgenwert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `SortOrder` ist ein optionales Element. Der Standardwert ist 100, und alle Werte müssen ein Vielfaches von 10 sein.  
  
 Die `SortOrder` Element wird für benutzerdefinierte Vorlagen ignoriert. Alle Benutzer erstellte Vorlagen sind alphabetisch sortiert.  
  
 Vorlagen mit niedrigen Sortierwerte angezeigt werden, entweder in der **neues Projekt** oder **neues Element hinzufügen** Dialogfeld vor dem Vorlagen, die hohe Sortierwerte enthalten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Metadaten für die Standard [!INCLUDE[csprcs](../includes/csprcs-md.md)] -Klassenvorlage.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 In diesem Beispiel die `SortOrder` Element ist relativ hoch. Ist es wahrscheinlich, dass andere [!INCLUDE[csprcs](../includes/csprcs-md.md)] Elementvorlagen müssen eine `SortOrder` Werts kleiner als `290` und wird angezeigt, bevor Sie diese Vorlage in der **neues Element** Dialogfeld.  
  
## <a name="see-also"></a>Siehe auch  
 [Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)


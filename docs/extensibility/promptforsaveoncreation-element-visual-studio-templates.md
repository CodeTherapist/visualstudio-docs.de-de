---
title: PromptForSaveOnCreation-Element (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#PromptForSaveOnCreation
helpviewer_keywords:
- PromptForSaveOnCreation element [Visual Studio project templates]
ms.assetid: 75174674-0c3c-4b57-b2fd-6ea8e817b67d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2c5b04bfa04b1b6fd6599e5fdd06d6c58210f635
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39638442"
---
# <a name="promptforsaveoncreation-element-visual-studio-templates"></a>PromptForSaveOnCreation-Element (Visual Studio-Vorlagen)
Gibt an, ob der Benutzer, für ein Projekt Speicherort über aufgefordert wird die **neues Projekt** Dialogfeld beim Erstellen eines Projekts. Wenn dieses Element auf `true` festgelegt wird, wird der Benutzer aufgefordert, einen Speicherort anzugeben. Wird `false` angegeben, wird er dazu nicht aufgefordert. (In diesem Fall wird ein temporäres Projekt erstellt.)  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<PromptForSaveOnCreation>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<PromptForSaveOnCreation> true/false </PromptForSaveOnCreation>  
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
  
 Der Text muss entweder `true` oder `false` lauten. `true` gibt an, dass der Benutzer bei Erstellung eines neuen Projekts zur Angabe eines Speicherorts aufgefordert wird.  
  
## <a name="remarks"></a>Hinweise  
 `PromptForSaveOnCreation` ist ein optionales Element. Der Standardwert ist `false`.  
  
 Temporäre Projekte sind Projekte, die Sie erstellen und ändern können, ohne den Inhalt des Projekts auf einem Datenträger zu speichern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Wert von `PromptForSaveOnCreation` gleich `false` festgelegt. Dadurch wird angegeben, dass das Projekt als temporäres Projekt erstellt werden kann.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <PromptForSaveOnCreation>false</PromptForSaveOnCreation>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schemareferenz zu Visual Studio-Vorlage](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)
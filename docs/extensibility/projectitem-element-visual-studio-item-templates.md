---
title: ProjectItem-Element (Visual Studio-Projektelementvorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- <ProjectItem> element [Visual Studio item templates]
- ProjectItem element [Visual Studio item templates]
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae7b54e6311a58d93c5cc11cfc073c4032df32dd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49855988"
---
# <a name="projectitem-element-visual-studio-item-templates"></a>ProjectItem-Element (Visual Studio-Projektelementvorlagen)
Gibt eine Datei, die in der Elementvorlage enthalten ist.  
  
> [!NOTE]
>  Die `ProjectItem` -Element akzeptiert verschiedene Attribute je nachdem, ob die Vorlage für ein Projekt oder ein Element. In diesem Thema wird erläutert, die `ProjectItem` -Element für Element. Eine Erläuterung der `ProjectItem` -Element für Projektvorlagen finden Sie unter [ProjectItem-Element (Visual Studio-Projektvorlagen)](../extensibility/projectitem-element-visual-studio-project-templates.md).  
  
 \<VSTemplate>  
 \<TemplateContent >  
 \<ProjectItem >  
  
## <a name="syntax"></a>Syntax  
  
```  
<ProjectItem  
    SubType="Form/Component/CustomControl/UserControl"  
    CustomTool="string"  
    ItemType="string"  
    ReplaceParameters="true/false"  
    TargetFileName="TargetFileName.ext">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden attribute-Elemente sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
| Attribut | Beschreibung |
|---------------------| - |
| `SubType` | Optionales Attribut.<br /><br /> Gibt den Untertyp eines Elements in einer Elementvorlage mit mehreren Dateien an. Dieser Wert wird verwendet, um den Editor zu bestimmen, die [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] verwendet, um das Element zu öffnen. |
| `CustomTool` | Optionales Attribut.<br /><br /> Legt die CustomTool für das Element in der Projektdatei fest. |
| `ItemType` | Optionales Attribut.<br /><br /> Legt den ItemType für das Element in der Projektdatei fest. |
| `ReplaceParameters` | Optionales Attribut.<br /><br /> Ein boolescher Wert, der angibt, ob das Element Parameterwerte verfügt, die ersetzt werden muss, wenn ein Projekt aus der Vorlage erstellt wird. Der Standardwert ist `false`sein. |
| `TargetFileName` | Optionales Attribut.<br /><br /> Gibt den Namen des Elements, das aus der Vorlage erstellt wird. Dieses Attribut ist nützlich für die Verwendung von parameterersetzungen erstellen Sie einen Elementnamen ein. |
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Gibt den Inhalt der Vorlage.|  
  
## <a name="text-value"></a>Textwert  
 Ein Textwert ist erforderlich.  
  
 Ein `string` , die den Namen einer Datei in der Vorlage darstellt *ZIP* Datei.  
  
## <a name="remarks"></a>Hinweise  
 `ProjectItem` ist ein optionales untergeordnetes Element des `TemplateContent`.  
  
 Die `TargetFileName` Attribut zum Umbenennen von Dateien mit Parametern verwendet werden kann. Z. B. wenn die Datei *MyFile.vb* vorhanden ist, im Stammverzeichnis der Vorlage *ZIP* -Datei, Sie möchten aber die Datei benannt wird basierend auf den Dateinamen, die vom Benutzer im angegebenen die **neues Element hinzufügen**  (Dialogfeld), verwenden Sie den folgenden XML-Code:  
  
```xml  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 Wenn ein Element aus dieser Vorlage erstellt wird, der Dateiname wird auf Grundlage der Name des Benutzers im der **neues Element hinzufügen** Dialogfeld. Dies ist nützlich, beim Erstellen von Elementvorlagen mit mehreren Dateien. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen mit mehreren Dateien](../ide/how-to-create-multi-file-item-templates.md) und [Vorlagenparameter](../ide/template-parameters.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Metadaten für die standard-Elementvorlage für eine [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Klasse.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schemareferenz zu Visual Studio-Vorlage](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)   
 [Gewusst wie: Erstellen von Elementvorlagen mit mehreren Dateien](../ide/how-to-create-multi-file-item-templates.md)   
 [Vorlagenparameter](../ide/template-parameters.md)
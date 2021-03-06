---
title: Fügen Sie benutzerdefinierter Eigenschaften zu Abhängigkeit-Diagramme hinzu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 368d1a794f51d827aa62cc913039edda59ae7ae6
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33864189"
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>Fügen Sie benutzerdefinierter Eigenschaften zu Abhängigkeit-Diagramme hinzu

Wenn Sie Erweiterungscode Abhängigkeit Diagramme schreiben, können Sie Werte mit jedem Element in einem Diagramm Abhängigkeit speichern. Die Werte bleiben erhalten, wenn das Diagramm gespeichert und erneut geöffnet wird. Außerdem können Sie diese Eigenschaften werden in der **Eigenschaften** Fenster, damit Benutzer angezeigt und werden bearbeitet können. Beispielsweise können Sie Benutzer für jede Ebene einen regulären Ausdruck angeben lassen und Validierungscode schreiben, um sicherzustellen, dass die Namen der Klassen in jeder Ebene dem Muster entsprechen, das vom Benutzer angegeben wird.

## <a name="non-visible-properties"></a>Nicht sichtbare Eigenschaften

Wenn Sie nur Code Werte auf jedes Element in einem Diagramm Abhängigkeit anfügen möchten, müssen Sie eine MEF-Komponente zu definieren. Es gibt ein Wörterbuch namens `Properties` in <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>. Fügen Sie einfach Werte zum Wörterbuch jedes Ebenenelements hinzu, die gemarshallt werden können. Sie werden als Teil des Diagramms Abhängigkeit gespeichert werden. Weitere Informationen finden Sie unter [navigieren und Update überlagern Sie die Modelle im Programmcode](../modeling/navigate-and-update-layer-models-in-program-code.md).

## <a name="editable-properties"></a>Bearbeitbaren Eigenschaften

**Erste Vorbereitung**

> [!IMPORTANT]
> Um Eigenschaften anzuzeigen, stellen Sie die folgende Änderung auf jedem Computer, auf dem Ebeneneigenschaften sichtbar sein soll:
>
> 1. Führen Sie mithilfe von Editor **als Administrator ausführen**. Open *%ProgramFiles%\Microsoft Visual Studio [Version] \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest*.
> 2. Innerhalb der **Content** Element hinzuzufügen:
>
>     ```xml
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>
>     ```
> 3. Klicken Sie unter der **Visual Studio-Tools** Abschnitt der Visual Studio-Anwendung im Startmenü öffnen **Entwicklereingabeaufforderung**. Geben Sie Folgendes ein:
>
>      `devenv /rootSuffix /updateConfiguration`
>
>      `devenv /rootSuffix Exp /updateConfiguration`
> 4. Starten Sie Visual Studio neu.

**Stellen Sie sicher, dass der Code in einem VSIX-Projekt ist**

Wenn die Eigenschaft Teil eines Befehls, Gestenhandler oder Validierungsprojekt ist, müssen Sie nichts hinzufügen. Der Code für die benutzerdefinierte Eigenschaft sollte in einem Visual Studio-Erweiterungsprojekt definiert werden, das als MEF-Komponente definiert wird. Weitere Informationen finden Sie unter [Hinzufügen von Befehlen und Bewegungen zu Abhängigkeit Diagrammen](../modeling/add-commands-and-gestures-to-layer-diagrams.md) oder [Hinzufügen von benutzerdefinierten architekturüberprüfung zu Abhängigkeit Diagrammen](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).

**Definieren der benutzerdefinierten Eigenschaft**

Um eine benutzerdefinierte Eigenschaft zu erstellen, definieren Sie eine Klasse folgendermaßen:

```csharp
[Export(typeof(IPropertyExtension))]
public class MyProperty : PropertyExtension<ILayerElement>
{
  // Implement the interface.
}
```

Sie können Eigenschaften für <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> oder eine der abgeleiteten Klassen definieren, darunter folgende:

-   `ILayerModel` - das Modell

-   `ILayer` - jede Ebene

-   `ILayerDependencyLink` - die Links zwischen Ebenen

-   `ILayerComment`

-   `ILayerCommentLink`

## <a name="example"></a>Beispiel

Der folgende Code entspricht einem typischen benutzerdefinierten Eigenschaftendeskriptor. Er definiert eine boolesche Eigenschaft für das Ebenenmodell (`ILayerModel`), mit dem der Benutzer Werte für eine benutzerdefinierte Validierungsmethode bereitstellen kann.

```csharp
using System;
using System.ComponentModel.Composition;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;

namespace MyNamespace
{
  /// <summary>
  /// Custom properties are added to the Layer Designer via a custom
  /// Property Descriptor. We have to export this Property Descriptor
  /// using MEF to make it available in the Layer Designer.
  /// </summary>
  [Export(typeof(IPropertyExtension))]
  public class AllTypesMustBeReferencedProperty
      : PropertyExtension<ILayerModel>
  {
    /// <summary>
    /// Each custom property must have a unique name.
    /// Usually we use the full name of this class.
    /// </summary>
    public static readonly string FullName =
      typeof(AllTypesMustBeReferencedProperty).FullName;

    /// <summary>
    /// Construct the property. Notice the use of FullName.
    /// </summary>
    public AllTypesMustBeReferencedProperty()
            : base(FullName)
    {  }

    /// <summary>
    /// The display name is shown in the Properties window.
    /// We therefore use a localizable resource.
    /// </summary>
    public override string DisplayName
    {
      get { return Strings.AllTypesMustBeReferencedDisplayName; }
    }

    /// <summary>
    /// Description shown at the bottom of the Properties window.
    /// We use a resource string for easier localization.
    /// </summary>
    public override string Description
    {
      get { return Strings.AllTypesMustBeReferencedDescription; }
    }

    /// <summary>
    /// This is called to set a new value for this property. We must
    /// throw an exception if the value is invalid.
    /// </summary>
    /// <param name="component">The target ILayerElement</param>
    /// <param name="value">The new value</param>
    public override void SetValue(object component, object value)
    {
      ValidateValue(value);
      base.SetValue(component, value);
    }
    /// <summary>
    /// Helper to validate the value.
    /// </summary>
    /// <param name="value">The value to validate</param>
    private static void ValidateValue(object value)
    {  }

    public override Type PropertyType
    { get { return typeof(bool); } }

    /// <summary>
    /// The segment label of the properties window.
    /// </summary>
    public override string Category
    {
      get
      {
        return Strings.AllTypesMustBeReferencedCategory;
      }
    }
  }
}
```

## <a name="see-also"></a>Siehe auch

- [Erweitern von Abhängigkeitsdiagrammen](../modeling/extend-layer-diagrams.md)

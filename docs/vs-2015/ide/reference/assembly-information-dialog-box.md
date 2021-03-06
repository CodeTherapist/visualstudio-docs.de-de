---
title: Dialogfeld „Assemblyinformationen“ | Microsoft-Dokumentation
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
- vb.ProjectPropertiesAssemblyInfo
helpviewer_keywords:
- Assembly Information dialog box
ms.assetid: 8f1f6449-e03d-4a5b-9076-d3b1f84ada48
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8526dfbe970c43e1ab55534c13a1e6708b2b4693
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248026"
---
# <a name="assembly-information-dialog-box"></a>Dialogfeld "Assemblyinformationen"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Im Dialogfeld **Assemblyinformationen** werden die Werte der globalen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Assemblyattribute festgelegt, die in der AssemblyInfo-Datei gespeichert sind, die mit dem Projekt automatisch erstellt wird. Im **Projektmappen-Explorer** befindet sich die Datei im Knoten **Mein Projekt** in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (klicken Sie zum Anzeigen auf **Alle Dateien anzeigen**). Sie befindet sich unter **Eigenschaften** in [!INCLUDE[csprcs](../../includes/csprcs-md.md)]. Weitere Informationen zu Assemblyattributen finden Sie unter [Attributes (Attribute)](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205).  
  
 Wählen Sie zum Aufrufen des Dialogfelds einen Projektknoten im **Projektmappen-Explorer** aus, und klicken Sie anschließend im Menü **Projekt** auf **Eigenschaften**. Wenn der **Projekt-Designer** angezeigt wird, klicken Sie auf die Registerkarte **Anwendung**. Klicken Sie auf der Seite **Anwendung** auf die Schaltfläche **Assemblyinformationen**.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Titel**  
 Gibt einen Titel für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyTitleAttribute>  
  
 **Beschreibung**  
 Gibt eine optionale Beschreibung für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyDescriptionAttribute>  
  
 **Firma**  
 Gibt einen Firmennamen für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyCompanyAttribute>  
  
 **Produkt**  
 Gibt einen Produktnamen für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyProductAttribute>  
  
 **Copyright**  
 Gibt Copyrightinformationen für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyCopyrightAttribute>  
  
 **Marke**  
 Gibt eine Marke für das Assemblymanifest an. Entspricht <xref:System.Reflection.AssemblyTrademarkAttribute>  
  
 **Assemblyversion**  
 Gibt die Version der Assembly an. Entspricht <xref:System.Reflection.AssemblyVersionAttribute>  
  
 **Dateiversion**  
 Gibt eine Versionsnummer an, die den Compiler anweist, eine bestimmte Version der Versionsressource der Win32-Datei zu verwenden. Entspricht <xref:System.Reflection.AssemblyFileVersionAttribute>  
  
 **GUID**  
 Eine eindeutige GUID zur Identifizierung der Assembly. Wenn Sie ein Projekt erstellen, generiert Visual Studio eine GUID für die Assembly. Entspricht <xref:System.Guid>  
  
 **Neutrale Sprache**  
 Gibt an, welche Kultur die Assembly unterstützt. Entspricht <xref:System.Resources.NeutralResourcesLanguageAttribute> Der Standardwert lautet **(Keine)**.  
  
 **Assembly COM-sichtbar machen**  
 Gibt an, ob Typen in der Assembly für COM verfügbar sind. Entspricht <xref:System.Runtime.InteropServices.ComVisibleAttribute>  
  
## <a name="see-also"></a>Siehe auch  
 [Application Page, Project Designer (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)   
 [Attribute](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)




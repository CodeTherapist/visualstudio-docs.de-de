---
title: 'Gewusst wie: Programmgesteuertes Liste zuletzt verwendeter Arbeitsmappendateien'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d3e909ad3e1509689d953e0ad6c6b8346ff97f91
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257588"
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>Gewusst wie: Programmgesteuertes Liste zuletzt verwendeter Arbeitsmappendateien
  Die <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> -Eigenschaft gibt eine Auflistung, die die Namen aller Dateien enthält, die in der Microsoft Office Excel-Liste der zuletzt geöffneten Dateien angezeigt werden. Die Länge der Liste variiert abhängig von der Anzahl der Dateien, die der Benutzer ausgewählt hat, beibehalten werden sollen. Sie können die Ergebnisse in einem Bereich anzeigen.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Auf die Liste der zuletzt verwendete Arbeitsmappen eines Range-Objekts  
  
1.  Durchlaufen Sie die Liste der zuletzt verwendeten Dateien und die Anzeigenamen in den Zellen relativ zu einem <xref:Microsoft.Office.Interop.Excel.Range> Objekt.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Arbeitsmappen](../vsto/working-with-workbooks.md)   
 [NamedRange-Steuerelement](../vsto/namedrange-control.md)   
 [Optionaler Parameter in Office-Projektmappen](../vsto/optional-parameters-in-office-solutions.md)  
  
  
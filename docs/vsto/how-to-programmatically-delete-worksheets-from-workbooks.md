---
title: 'Gewusst wie: Programmgesteuertes Löschen von Arbeitsblättern aus Arbeitsmappen'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, deleting worksheets
- worksheets, deleting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 73c501d545f76012b63bde291001b38c214c3eb6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950224"
---
# <a name="how-to-programmatically-delete-worksheets-from-workbooks"></a>Gewusst wie: Programmgesteuertes Löschen von Arbeitsblättern aus Arbeitsmappen
  Sie können jedes beliebige Arbeitsblatt in einer Arbeitsmappe löschen. Verwenden Sie zum Löschen eines Arbeitsblatts das Arbeitsblatt-Hostelement, oder greifen Sie auf das Arbeitsblatt mithilfe der Sheets-Auflistung der Arbeitsmappe zu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-the-worksheet-host-item"></a>Verwenden Sie das Arbeitsblatt-Hostelement  
 Wenn das Arbeitsblatt zur Entwurfszeit in einer Anpassung auf Dokumentebene hinzugefügt wurde, verwenden Sie die Methode <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A>, um ein angegebenes Arbeitsblatt zu löschen. Der folgende Code löscht ein Arbeitsblatt aus einer Arbeitsmappe durch direktes Verweisen auf das Arbeitsblatt-Hostelement.  
  
> [!IMPORTANT]
>  Dieser Code wird nur in Projekten ausgeführt, die Sie mithilfe einer der folgenden Projektvorlagen erstellen:  
> 
> - Excel 2013-Arbeitsmappe  
> - Excel 2013-Vorlage  
> - Excel 2010-Arbeitsmappe  
> - Excel 2010-Vorlage  
> 
>   Wenn Sie einen anderen Typ von Projekt diese Aufgabe ausführen möchten, müssen Sie hinzufügen, einen Verweis auf die **Microsoft.Office.Interop.Excel** Assembly vorliegt und Sie müssen Klassen aus dieser Assembly verwenden, um eine Arbeitsmappe öffnen und Löschen eines Arbeitsblatts. Weitere Informationen finden Sie unter [Vorgehensweise: Target Office-Anwendungen durch primäre Interopassemblys](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) und [Referenz für die primäre interop-Assembly von Excel 2010](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
### <a name="to-delete-a-worksheet-by-using-a-worksheet-host-item"></a>So löschen Sie ein Arbeitsblatt mithilfe eines Arbeitsblatt-Hostelements  
  
1.  Rufen Sie die <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> -Methode von `Sheet1`auf.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#17)]  
  
## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Verwenden der Sheets-Auflistung der Excel-Arbeitsmappe  
 Greifen Sie auf Arbeitsblätter über die Microsoft Office Excel-Auflistung <xref:Microsoft.Office.Interop.Excel.Sheets> in den folgenden Fällen zu:  
  
- Sie möchten ein Arbeitsblatt in einem VSTO-Add-In löschen.  
  
- Das Arbeitsblatt, das Sie löschen möchten, wurde zur Laufzeit in einer Anpassung auf Dokumentebene erstellt.  
  
  Der folgende Code Löscht ein Arbeitsblatt aus einer Arbeitsmappe durch Verweisen auf das Blatt über die Indexnummer des der **Blätter** Auflistung. Dieser Code geht davon aus, dass ein neues Arbeitsblatt programmgesteuert erstellt wurde.  
  
> [!IMPORTANT]  
>  Wenn Sie einen anderen Typ von Projekt diese Aufgabe ausführen möchten, müssen Sie hinzufügen, einen Verweis auf die **Microsoft.Office.Interop.Excel** Assembly vorliegt und Sie müssen Klassen aus dieser Assembly verwenden, um eine Arbeitsmappe öffnen und Löschen eines Arbeitsblatts. Weitere Informationen finden Sie unter [Vorgehensweise: Target Office-Anwendungen durch primäre Interopassemblys](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) und [Referenz für die primäre interop-Assembly von Excel 2010](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
### <a name="to-delete-a-worksheet-by-using-the-sheets-collection-of-the-excel-workbook"></a>So löschen Sie ein Arbeitsblatt mithilfe der Sheets-Auflistung der Excel-Arbeitsmappe  
  
1.  Rufen Sie die Methode <xref:Microsoft.Office.Interop.Excel._Worksheet.Delete%2A> der Auflistung <xref:Microsoft.Office.Interop.Excel.Sheets> auf.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#18)]  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Arbeitsblättern](../vsto/working-with-worksheets.md)   
 [Gewusst wie: Programmgesteuertes Ausblenden von Arbeitsblättern](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Gewusst wie: Programmgesteuertes Verschieben von Arbeitsblättern in Arbeitsmappen](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Gewusst wie: Programmgesteuertes auswählen von Arbeitsblättern](../vsto/how-to-programmatically-select-worksheets.md)   
 [Gewusst wie: Programmgesteuertes Hinzufügen neuer Arbeitsblätter zu Arbeitsmappen](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Arbeitsblatthostelement](../vsto/worksheet-host-item.md)   
 [Globaler Zugriff auf Objekte in Office-Projekten](../vsto/global-access-to-objects-in-office-projects.md)   
 [Einschränkungen für programmgesteuerte Aufgaben von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  
---
title: Anzeigen von Dateien öffnen mit-Befehl mit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 716e9f1551681b9e194bd300522f55ab5e927dab
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816453"
---
# <a name="displaying-files-by-using-the-open-with-command"></a>Anzeigen von Dateien mit dem Befehl „Öffnen mit“
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ein Projekt lassen die IDE zum Anzeigen der **Öffnen mit** Dialogfeld. Diese Anforderung fordert den Benutzer zum Öffnen einer Datei, die eine Auswahl von standard-Editoren. Die folgenden Schritte beschreiben, diesen Prozess.  
  
1.  Die projektaufrufe <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, geben Sie einen Wert OSE_UseOpenWithDialog für die `OSEOpenDocEditor` Parameter.  
  
2.  Basierend auf der Dateinamenerweiterung des Dokuments ab, die IDE bestimmt, welche Editoren aufgeführt, die in der Registrierung kann das angegebene Dokument geöffnet und zeigt diese Informationen in den **Öffnen mit** Dialogfeld.  
  
    > [!NOTE]
    >  Projekte, die einen systeminternen Editor verfügen, die im enthalten sein müssen die **Öffnen mit** im Dialogfeld eine Editorfactory für jeden solchen Editor registrieren muss. Systeminterne Editoren funktionieren nur zusammen mit der eine bestimmte Art von Projekt, das in der Implementierung der erzwungen wird die <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> Methode. Die IDE hat eine integrierten Editorfactory für die kerntext-Editor und dem Binär-Editor. Die IDE erstellt auch eine Instanz von einer Editorfactory für jede registrierte Windows-dateizuordnung. Ein Beispiel für eine solche Datei ist Microsoft Word.  
  
3.  Sobald der Benutzer ein Element auswählt der **Öffnen mit** (Dialogfeld), klicken Sie dann die IDE Öffnet das Dokument durch Aufrufen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> Methode. Weitere Informationen finden Sie unter [How to: Open-Standard-Editoren](../../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sie öffnen und Speichern von Projektelementen](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Anzeigen von Dateien mit dem Befehl Open File](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [Gewusst wie: Öffnen von Standard-Editoren](../../extensibility/how-to-open-standard-editors.md)


---
title: Formatierung, XML, Text-Editor, Dialogfeld "Optionen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb539b3a-027c-4b2f-906e-403e0e22ba8d
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5c8379393dd5327359789f8621cf67ed55e89209
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256671"
---
# <a name="formatting-xml-text-editor-options-dialog-box"></a>Formatierung, XML, Texteditor, Dialogfeld "Optionen"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
In diesem Dialogfeld können Sie die Formatierungseinstellungen für den XML-Editor angeben. Sie können den Zugriff auf die **Optionen** das Dialogfeld die **Tools** Menü.  
  
> [!NOTE]
>  Diese Einstellungen sind verfügbar, wenn Sie auswählen der **Text-Editor** Ordner die **XML** Ordner, und klicken Sie dann die **Formatierung** option die **Optionen** Dialogfeld.  
  
## <a name="attributes"></a>Attribute  
 **Manuelle attributformatierung beibehalten**  
 Attribute werden nicht neu formatiert. Dies ist die Standardeinstellung.  
  
> [!NOTE]
>  Wenn sich die Attribute auf mehreren Zeilen befinden, zieht der Editor jede Attributzeile ein, sodass das Einzugsmuster des übergeordneten Elements festgelegt wird.  
  
 **Attribute jeweils in einer eigenen Zeile ausrichten**  
 Richtet das zweite und die nachfolgenden Attribute vertikal aus, damit sie dem Einzug des ersten Attributs entsprechen. Der folgende XML-Text veranschaulicht, wie die Attribute ausgerichtet werden.  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95">  
</item>  
```  
  
## <a name="auto-reformat"></a>Automatisch neu formatieren  
 **Bei einfügen aus der Zwischenablage**  
 Formatiert den aus der Zwischenablage eingefügten XML-Text neu.  
  
 **Nach Abschluss des Endtags**  
 Formatiert das Element neu, wenn das Endtag vervollständigt wird.  
  
## <a name="mixed-content"></a>	Gemischter Inhalt  
 **Gemischten Inhalt standardmäßig beibehalten**  
 Bestimmt, ob der Editor gemischten Inhalt neu formatiert. Der Editor versucht standardmäßig, gemischten Inhalt neu zu formatieren, es sei denn, der Inhalt befindet sich in einem `xml:space="preserve"`-Gültigkeitsbereich.  
  
 Wenn ein Element eine Mischung aus Text und Markup enthält, wird der Inhalt als gemischter Inhalt betrachtet. Es folgt als Beispiel ein Element mit gemischtem Inhalt.  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
</dir>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumenteigenschaften, Eigenschaftenfenster](../xml-tools/xml-document-properties-properties-window.md)   
 [Komponenten des XML-Editors](../xml-tools/xml-editor-components.md)




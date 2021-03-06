---
title: 'Vorgehensweise: bietet einen Überblick über ein Schemaset, das mithilfe der Graph-Ansicht | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3722af4aef2f56d6da1c2a79840c05edd2a87b65
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49181362"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Gewusst wie: Anzeigen einer Übersicht über ein Schemaset in der Diagrammansicht
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
In diesem Thema wird beschrieben, wie Sie mit der [Diagrammansicht](../xml-tools/graph-view.md) um einen allgemeinen Überblick über die Knoten in einem Schemaset und die Beziehungen zwischen den Knoten anzuzeigen.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>So erstellen Sie eine neue XSD-Datei und zeigen Sie das Stammelement in der Inhaltsmodellansicht an  
  
1.  Erstellen Sie eine neue XML-Schemadatei, und speichern Sie die Datei unter dem Namen "Relationships.xsd".  
  
2.  Klicken Sie auf die **verwenden Sie den XML-Editor anzeigen und bearbeiten die zugrunde liegende XML-Schemadatei** Link in der Ausgangsansicht auf.  
  
3.  Kopieren Sie die XML-schemabeispielcode aus [XML-Beispielschema: Beziehungen](../xml-tools/sample-xsd-file-relationships.md) und fügen Sie ihn, um den Standardcode zu ersetzen, das die neue XSD-Datei standardmäßig hinzugefügt wurde.  
  
4.  Mit der rechten Maustaste in der XML-Editor, und wählen Sie **Ansicht-Designer**.  
  
5.  Wählen Sie auf der XSD-Symbolleiste die Diagrammansicht aus.  
  
6.  Wählen Sie **Schemaset** Knoten im XML-Schema-Explorer und ziehen Sie den Knoten Suface der Diagrammansicht zu entwerfen. Nun sollten alle globalen Knoten und Verbindungspfeile zwischen den Knoten mit Beziehungen angezeigt werden.  
  
     ![Diagrammansicht](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  Klicken Sie auf der Entwurfsoberfläche auf einen Knoten, und überprüfen Sie in der Breadcrumb-Leiste, wo sich der ausgewählte Knoten im Schemaset befindet.  
  
8.  Rick, klicken Sie auf einen Elementknoten in das Muster, die Entwurfsoberfläche, und wählen **Beispiel-XML generieren** XML-Instanzendokument angezeigt.




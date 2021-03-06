---
title: Eigenschaften von Depotformen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords:
- Domain-Specific Language, compartment shape
ms.assetid: 9a9e112d-210d-413b-a44f-0e976a4a78bc
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: bb5730093a9eda6464bd6b67fa09976a4e9cd2f6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49216384"
---
# <a name="properties-of-compartment-shapes"></a>Eigenschaften von Depotformen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Depot-Formen sind eine Form, die Sie verwenden können, um eine Domänenklasse in einer domänenspezifischen Sprache anzuzeigen. Sie können die Depots reduzieren und erweitern.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Definieren Sie eine domänenspezifische Sprache](../modeling/how-to-define-a-domain-specific-language.md). Weitere Informationen zum Verwenden dieser Eigenschaften finden Sie unter [anpassen und Erweitern einer domänenspezifischen Sprache](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Depot-Formen haben Eigenschaften, die in der folgenden Tabelle aufgeführt sind.  
  
|Eigenschaft|Beschreibung|Standard|  
|--------------|-----------------|-------------|  
|Standardmäßige erweitern reduziert werden kann|Wenn `Expanded`, werden die Depots bei der Erstellung angezeigt. Wenn `Collapsed`, sind sie nicht.|Erweitert|  
|Füllfarbe|Die Füllfarbe dieser Form.|Weiß|  
|Der Farbverlaufmodus|Die füllverlaufsmodus dieser Form.|Horizontal|  
|Geometry|Die Geometrie dieser Form (Rechteck oder abgerundetes Rechteck).|Rechteck|  
|Verfügt über Standard-Verbindungspunkte|Wenn `True`, verwendet die Form oben, unten, links und rechten Verbindungspunkte im generierten Designer.|False|  
|Wird der Depot-Header angezeigt|Wenn `False`, und die Form über ein Depot verfügt, des Headers des Depots nicht sichtbar.|True|  
|Konturfarbe|Die Konturfarbe dieser Form.|Schwarz|  
|Konturstrichstil|Der konturstrichstil dieser Form (einfarbig, Bindestrich, Punkt, DashDot, Strich, Benutzerdefiniert).|Basis|  
|Umrissstärke|Die konturlinienstärke dieser Form.|0.03125|  
|Textfarbe|Die Farbe für Text-Decorator-Elemente, die mit dieser Form verknüpft sind.|Schwarz|  
|Zugriffsmodifizierer|Die Ebene der Zugriff auf die Depot-Form (`public` oder `internal`).|Public|  
|Benutzerdefinierte Attribute|Verwendet, um die Attribute der Quellklasse Code hinzufügen, die von dieser depotform generiert wird|\<Keine >|  
|Double-Wert generiert abgeleitet|Wenn `True`, sowohl eine Basisklasse und eine partielle Klasse (zur Unterstützung von Anpassung über überschreibungen) generiert werden. Weitere Informationen finden Sie unter [überschreiben und Erweitern der generierten Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Hat benutzerdefinierten Konstruktor|Wenn `True`, ein benutzerdefinierter Konstruktor wird im Quellcode angegeben werden. Weitere Informationen finden Sie unter [überschreiben und Erweitern der generierten Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Vererbungsmodifizierer|Beschreibt die Art der Vererbung, der die Quellklasse in der Code ein, das mit der Depot-Form generiert (`none`, `abstract` oder `sealed`).|Keiner|  
|Basisdepotform|Die Basisklasse dieser Form.|(keine)|  
|name|Der Name dieser Form.|Aktuelle name|  
|Namespace|Der Namespace, der diese Form zugeordnet ist.|Aktuellen namespace|  
|QuickInfo-Typ|Wie die QuickInfo definiert ist (fest, Variable oder keine). Wenn fest, klicken Sie dann den Wert des der `Fixed Tooltip Text` Eigenschaft wird als QuickInfo verwendet, wenn die Variable, klicken Sie dann die QuickInfo wird im benutzerdefinierten Code definiert.|Keine|  
|Hinweise|Informelle Hinweise, die mit dieser Form verknüpft sind.|\<Keine >|  
|Die ursprüngliche Höhe|Die ursprüngliche Höhe dieser Form in Zoll. Dies ist die Höhe des Headerabschnitts nur Depot-Formen und kann nicht geändert werden.|1|  
|Die ursprüngliche Breite|Die ursprüngliche Breite dieser Form in Zoll.|1.5|  
|Als Eigenschaft verfügbar gemachte Füllfarbe<br /><br /> Verfügbar gemachte Füllverlaufsmodus<br /><br /> Konturfarbe als Eigenschaft verfügbar gemacht.<br /><br /> Konturstrichstil als Eigenschaft verfügbar gemacht.<br /><br /> Umrissstärke als Eigenschaft verfügbar<br /><br /> Stellt Text Color|Wenn `True`, der Benutzer kann die angegebene Eigenschaft einer Form festlegen. Um dies festzulegen, mit der rechten Maustaste in der Definition der Form, und klicken Sie auf **verfügbare hinzufügen**.|False|  
|Beschreibung|Dokumentieren des generierten Designers verwendet.|\<Keine >|  
|Anzeigename|Der Name, der im generierten Designer für diese Form angezeigt werden soll.|\<Keine >|  
|Feste QuickInfo-Text|Der Text, der für eine feste QuickInfo verwendet wird.|\<Keine >|  
|Hilfsschlüsselwort|Das Schlüsselwort, das zum Indizieren der F1-Hilfe für diese Form verwendet wird.|\<Keine >|  
  
## <a name="see-also"></a>Siehe auch  
 [DSL-Tools – Glossar](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)




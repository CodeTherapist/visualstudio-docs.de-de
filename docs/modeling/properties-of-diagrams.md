---
title: Eigenschaften von Diagrammen
ms.date: 10/31/2018
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 39e3cc044913a592d5f49e685d8075cd43803e55
ms.sourcegitcommit: 768d7877fe826737bafdac6c94c43ef70bf45076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "50966478"
---
# <a name="properties-of-diagrams"></a>Eigenschaften von Diagrammen
Sie können Eigenschaften festlegen, die angeben, wie Diagramme im generierten Designer angezeigt werden. Beispielsweise können Sie eine Standardfarbe für Text in das Diagramm angeben.

 Weitere Informationen finden Sie unter [Gewusst wie: Definieren Sie eine domänenspezifische Sprache](../modeling/how-to-define-a-domain-specific-language.md). Weitere Informationen zum Verwenden dieser Eigenschaften finden Sie unter [anpassen und erweitern eine domänenspezifischen Sprache](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Die folgende Tabelle enthält die Eigenschaften von Diagrammen.

|Eigenschaft|Beschreibung|Standard|
|-|-|-|
|Füllfarbe|Die Füllfarbe für das Diagramm.|Weiß|
|Textfarbe|Die Farbe des Texts, der im Diagramm angezeigt wird.|Schwarz|
|Zugriffsmodifizierer|Der Zugriffsmodifizierer der-Klasse (öffentlich oder intern).|Public|
|Benutzerdefinierte Attribute|Verwendet, um die Attribute der generierten Codeklasse hinzuzufügen.|\<Keine >|
|Double-Wert generiert abgeleitet|Wenn `True`, sowohl eine Basisklasse und eine partielle Klasse (zur Unterstützung von Anpassung über überschreibungen) generiert werden. Weitere Informationen finden Sie unter [überschreiben und Erweitern der generierten Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Hat benutzerdefinierten Konstruktor|Wenn `True`, ein benutzerdefinierter Konstruktor wird im Quellcode angegeben werden. Weitere Informationen finden Sie unter [überschreiben und Erweitern der generierten Klassen](../modeling/overriding-and-extending-the-generated-classes.md)...|False|
|Vererbungsmodifizierer|Beschreibt die Art der Vererbung, der die Quellklasse für Code, der aus dem Diagramm generiert wird (`none`, `abstract`, oder `sealed`).|Keiner|
|Basisdiagramm|Die Basisklasse des Diagramms.|(keine)|
|name|Der Name des Diagramms.|Aktuelle name|
|Namespace|Der Namespace, der in diesem Diagramm zugeordnet ist.|Aktuellen namespace|
|Dargestellte Klasse|Die Stamm-Domänenklasse, die in diesem Diagramm darstellt.|Aktuelle Stammklasse ggf.|
|Hinweise|Informelle Hinweise, die mit diesem Element verknüpft sind.|\<Keine >|
|Macht die Füllfarbe als Eigenschaft|Wenn `True`, der Benutzer kann die Füllfarbe des Diagramms des generierten Designers festlegen. Klicken Sie zum Festlegen dieser Eigenschaft mit der rechten Maustaste der Diagrammform, und klicken Sie auf **verfügbare hinzufügen**.|False|
|Textfarbe als Eigenschaft zur Verfügung gestellt|Wenn `True`, der Benutzer kann die Textfarbe des Diagramms im generierten Designer festlegen. Klicken Sie zum Festlegen dieser Eigenschaft mit der rechten Maustaste der Diagrammform, und klicken Sie auf **verfügbare hinzufügen**.|False|
|Beschreibung|Die Beschreibung, die zum Dokumentieren des generierten Designers verwendet wird.|\<Keine >|
|Anzeigename|Der Name, der im generierten Designer für dieses Diagramm angezeigt werden soll.|\<Keine >|
|Hilfsschlüsselwort|Das Schlüsselwort, das zum Indizieren der F1-Hilfe für dieses Diagramm verwendet wird.|\<Keine >|

## <a name="see-also"></a>Siehe auch

[DSL-Tools – Glossar](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)

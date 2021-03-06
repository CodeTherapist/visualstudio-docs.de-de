---
title: 'CA1822: Member als statisch markieren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7b85d12038d4c505f912dd2f9440829f2c80679c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49183494"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Member als statisch markieren
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Dokumentation für Visual Studio 2017 finden Sie unter [CA1822: Member als statisch markieren](https://docs.microsoft.com/visualstudio/code-quality/ca1822-mark-members-as-static) auf docs.microsoft.com.  
  
|||  
|-|-|  
|TypeName|MarkMethodsAsStatic|  
|CheckId|CA1822|  
|Kategorie|Microsoft.Performance|  
|Unterbrechende Änderung|Nicht unterbrechend – Wenn das Element nicht außerhalb der Assembly sichtbar ist müssen unabhängig von der Änderung. Nicht unterbrechend – Wenn Sie das Element auf einen Instanzmember mit ändern Sie einfach die `this` Schlüsselwort.<br /><br /> Unterbrechend – Wenn Sie das Element über ein Instanzmember in einen statischen Member ändern und außerhalb der Assembly sichtbar ist.|  
  
## <a name="cause"></a>Ursache  
 Ein Element, das nicht auf Instanzdaten zugreift, ist nicht als statisch markiert (Shared in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Member, die nicht auf Instanzdaten zugreifen oder keine Instanzmethoden aufrufen, können als static markiert werden (Shared in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]). Danach gibt der Compiler nicht virtuelle Aufrufsites an diese Member aus. Ausgeben von Aufrufsites wird zur Laufzeit für jeden Aufruf eine Überprüfung, die sicherstellt, dass der aktuelle Objektzeiger ungleich Null ist, verhindert. Dies kann zu eine messbaren Leistungssteigerung für leistungsabhängigen Code erreichen. In einigen Fällen stellt der Fehler auf die aktuelle Objektinstanz ein Problem der Richtigkeit dar.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Markieren Sie den Member als statisch (oder im freigegebenen [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) oder verwenden Sie "this" / "Me" in der Methode Anforderungstext, falls zutreffend.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Es ist sicher eine Warnung dieser Regel für die zuvor abgelieferten Codes zu unterdrücken, für die die Lösung eine unterbrechende Änderung sein würde.  
  
## <a name="related-rules"></a>Verwandte Regeln  
 [CA1811: Nicht aufgerufenen privaten Code vermeiden](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Nicht instanziierte interne Klassen vermeiden](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1804: Nicht verwendete lokale Variablen entfernen](../code-quality/ca1804-remove-unused-locals.md)


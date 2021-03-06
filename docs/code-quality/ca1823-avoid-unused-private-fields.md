---
title: 'CA1823: Nicht verwendete private Felder vermeiden'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a9ef0e63e13ab6e05025ef1a24c4032feb5eacd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49923705"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: Nicht verwendete private Felder vermeiden

|||
|-|-|
|TypeName|AvoidUnusedPrivateFields|
|CheckId|CA1823|
|Kategorie|Microsoft.Performance|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Mit dieser Regel wird gemeldet, wenn ein privates Feld in Ihrem Code vorhanden ist, jedoch nicht von jedem Codepfad verwendet werden.

## <a name="rule-description"></a>Regelbeschreibung
 Es wurden private Felder erkannt, auf die in der Assembly anscheinend kein Zugriff erfolgt.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, entfernen Sie das Feld, oder fügen Sie Code, der verwendet wird.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Es ist sicher, unterdrücken Sie eine Warnung dieser Regel.

## <a name="related-rules"></a>Verwandte Regeln
 [CA1812: Nicht instanziierte interne Klassen vermeiden](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Nicht verwendete Parameter überprüfen](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Nicht verwendete lokale Variablen entfernen](../code-quality/ca1804-remove-unused-locals.md)

 [CA1811: Nicht aufgerufenen privaten Code vermeiden](../code-quality/ca1811-avoid-uncalled-private-code.md)
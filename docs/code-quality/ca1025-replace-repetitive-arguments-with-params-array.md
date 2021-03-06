---
title: 'CA1025: Sich wiederholende Argumente durch ein Parameterarray ersetzen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 027ec9b19bcf8a4a10e8b973b86e57be2dbc6be7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49838321"
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: Sich wiederholende Argumente durch ein Parameterarray ersetzen

|||
|-|-|
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|
|CheckId|CA1025|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Eine öffentliche oder geschützte Methode in einem öffentlichen Typ über mehr als drei Parameter verfügt und die letzten drei Parameter sind vom gleichen Typ.

## <a name="rule-description"></a>Regelbeschreibung
 Verwenden Sie ein Parameterarray statt sich wiederholender Argumente, wenn die genaue Anzahl von Argumenten unbekannt ist und der Variablen Argumente den gleichen Typ aufweisen oder als gleicher Typ übergeben werden können. Z. B. die <xref:System.Console.WriteLine%2A> Methode bietet eine allgemeine Überladung, die ein Parameterarray verwendet wird, um eine beliebige Anzahl von akzeptieren <xref:System.Object> Argumente.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, ersetzen Sie die wiederholte Argumente mit einem Parameterarray.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Es ist sicherer, unterdrücken Sie eine Warnung dieser Regel; Dieses Design kann jedoch Probleme hinsichtlich der Verwendbarkeit verursachen.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ, der gegen diese Regel verstößt.

 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]
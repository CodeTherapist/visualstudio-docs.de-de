---
title: 'CA1026: Standardparameter sollten nicht verwendet werden | Microsoft-Dokumentation'
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
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5ab5fd842363c39f23981bdec93635974e2b2582
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49894364"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: Standardparameter sollten nicht verwendet werden
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein extern sichtbarer Typ enthält eine extern sichtbare Methode, die einen Standardparameter verwendet werden.

## <a name="rule-description"></a>Regelbeschreibung
 Methoden, die Standardparameter verwenden, sind unter der Common Language Specification (CLS) zulässig. die CLS lässt jedoch Compiler, um die Werte zu ignorieren, die diese Parameter zugewiesen werden. Code, der für Compiler geschrieben wird, die ignoriert werden Standardparameterwerte muss die Argumente für jeden Standardparameter explizit bereitgestellt werden. Um das Verhalten zu gewährleisten, das verschiedenen Programmiersprachen werden sollen, sollte Methoden, die Standardparameter verwenden durch methodenüberladungen ersetzt werden, die die Standardparameter bereitgestellt.

 Der Compiler ignoriert die Werte der Standardparameter für Managed Extensions für C++, beim Zugriff auf verwaltetem Code. Visual Basic-Compiler unterstützt Methoden, die standardmäßigen Parameter verfügen, verwenden die [Optional](http://msdn.microsoft.com/library/4571ce88-a539-4115-b230-54eb277c6aa7) Schlüsselwort.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Ersetzen Sie die Methode, die Standardparameter durch überladene Methoden verwendet werden, die die Standardparameter angeben, um einen Verstoß gegen diese Regel zu beheben.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt eine Methode, die Standardparameter verwendet und die überladene Methoden, die eine entsprechende Funktionalität bereitzustellen.

 [!code-vb[FxCop.Design.DefaultParameters#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DefaultParameters/vb/FxCop.Design.DefaultParameters.vb#1)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA1025: Sich wiederholende Argumente durch ein Parameterarray ersetzen](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>Siehe auch
 [Sprachunabhängigkeit und sprachunabhängige Komponenten](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)




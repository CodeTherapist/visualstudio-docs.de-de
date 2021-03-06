---
title: 'CA2004: Aufrufe an GC.KeepAlive entfernen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bea4af6c0ae0e21e15a79d52f4c7205a51a3ea46
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49819120"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Aufrufe an GC.KeepAlive entfernen

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategorie|Microsoft.Reliability|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Klassen geben mit `SafeHandle` , aber dennoch enthält Aufrufe von `GC.KeepAlive`.

## <a name="rule-description"></a>Regelbeschreibung
 Wenn Sie zum Konvertieren `SafeHandle` Nutzung, entfernen Sie alle Aufrufe `GC.KeepAlive` (Objekt). In diesem Fall Klassen dürfen keine aufzurufende `GC.KeepAlive`, vorausgesetzt, sie haben keinen Finalizer, sondern basieren auf `SafeHandle` das Betriebssystemhandle für diese durchführen.  Obwohl die Kosten für einen Aufruf von `GC.KeepAlive` möglicherweise unerheblich, wie die Wahrnehmung der Leistung gemessen, die einen Aufruf von `GC.KeepAlive` erforderlich oder ausreichend, um eine Lebensdauer zu lösen, Problem, das möglicherweise nicht mehr vorhanden. Dadurch wird der Code schwieriger zu, verwalten.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Entfernen Sie Aufrufe von `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Sie können diese Warnung unterdrücken, nur dann, wenn er nicht technisch korrekt zu konvertieren ist `SafeHandle` Nutzung in Ihrer Klasse.
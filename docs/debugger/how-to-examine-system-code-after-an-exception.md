---
title: 'Vorgehensweise: Untersuchen von Systemcode nach einer Ausnahme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8a1da63e47514771a868b69ee798f71265fdb42
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472464"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>Gewusst wie: Untersuchen von Systemcode nach einer Ausnahme
Wenn eine Ausnahme auftritt, müssen Sie unter Umständen Code in einem Systemaufruf prüfen, um die Ursache für die Ausnahme zu ermitteln. Im folgenden Verfahren wird die entsprechende Vorgehensweise erläutert, wenn Sie keine Symbole für den Systemcode geladen haben oder wenn Nur mein Code aktiviert ist.  
  
### <a name="to-examine-system-code-following-an-exception"></a>So prüfen Sie Systemcode nach einer Ausnahme  
  
1.  In der **Aufrufliste** Fenster, mit der rechten Maustaste, klicken Sie dann klicken Sie auf **externen Code anzeigen**.  
  
     Wenn Nur mein Code nicht aktiviert ist, ist diese Option nicht im Kontextmenü verfügbar, und Systemcode wird standardmäßig angezeigt.  
  
2.  Mit der rechten Maustaste die externen Codeframes, die jetzt in angezeigt werden, der die **Aufrufliste** Fenster.  
  
3.  Zeigen Sie auf **Symbole laden aus** , und klicken Sie dann auf **Microsoft-Symbolserver**.  
  
    1.  Wenn Nur mein Code aktiviert wurde, wird ein Dialogfeld angezeigt. Es gibt an, dass Nur mein Code jetzt deaktiviert wurde. Dies ist für die schrittweise Ausführung von Systemaufrufen erforderlich.  
  
    2.  Die **öffentliche Symbole werden heruntergeladen** Dialogfeld wird angezeigt. Nach Abschluss des Downloadvorgangs wird das Dialogfeld geschlossen.  
  
4.  Sie können jetzt den Systemcode im Untersuchen der **Aufrufliste** Fenster und anderen Fenstern. Sie können z. B. einen Aufruflistenrahmen zum Anzeigen des Codes in einer Datenquelle doppelklicken oder **Disassembly** Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Ausnahmen mit dem Debugger](../debugger/managing-exceptions-with-the-debugger.md)
---
title: 'Fehler: Der Microsoft Visual Studio-Remotedebugmonitor auf dem Remotecomputer ist nicht berechtigt, die mit diesem Computer herstellen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, Windows version error
ms.assetid: ba08a59b-6dbc-4bbc-9c52-379d3bf5241f
caps.latest.revision: 24
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e3ebc483c581d3283e6c2bd640144aef7554905
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51777915"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Fehler: Der Microsoft Visual Studio-Remotedebugmonitor auf dem Remotecomputer verfügt nicht über die Berechtigung, eine Verbindung mit diesem Computer herzustellen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dieser Fehler tritt auf, wenn der Benutzer, der versucht, den Visual Studio-Remotedebugmonitor (msvsmon) auszuführen, kein Konto auf dem lokalen Computer hat.  
  
### <a name="to-fix-this-problem"></a>So beheben Sie dieses Problem  
  
- Fügen Sie dem Hostcomputer mit dem Visual Studio Debugger ein Benutzerkonto mit demselben Namen und Kennwort wie dem Benutzerkonto hinzu, unter dem msvsmon auf dem Remotecomputer ausgeführt wird.  
  
   \- oder –  
  
- Führen Sie msvsmon als Benutzer aus, der berechtigt ist, auf dem lokalen Computer Aufrufe durchzuführen. Dies bedeutet, dass der Benutzer ein Domänenbenutzer sein und Administratorrechte auf dem msvsmon-Computer besitzen muss.  Sie haben zwei Möglichkeiten, um das Benutzerkonto zum Ausführen von msvsmon anzugeben:  
  
  - Mit der rechten Maustaste in des Msvsmon-Symbols, und wählen Sie **ausführenden** im Kontextmenü  
  
    \- oder –  
  
  - Führen Sie an der Eingabeaufforderung `runas.exe` aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Remotedebuggen über Domänen hinweg](http://msdn.microsoft.com/library/8e697ce1-55e8-4ab0-a05f-f87225e2f29b)   
 [Remotedebuggen – Fehler und Problembehandlung](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)




---
title: 'Vorgehensweise: Aktivieren von ClickOnce-Sicherheitseinstellungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 73f4e16dc0d088ca617b49ee1250f51c4ae769e2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49226023"
---
# <a name="how-to-enable-clickonce-security-settings"></a>Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Codezugriffssicherheit für ClickOnce-Anwendungen muss aktiviert sein, um die Anwendung zu veröffentlichen. Dies erfolgt automatisch bei der Veröffentlichung einer Anwendung mithilfe des Veröffentlichungs-Assistenten.  
  
 In einigen Fällen kann die Leistung, die bei der Erstellung oder Debuggen der Anwendung aktivieren auf die Codezugriffssicherheit auswirken werden; in diesen Fällen können Sie die Sicherheitseinstellungen vorübergehend deaktivieren möchten.  
  
 ClickOnce-Sicherheitseinstellungen können aktiviert oder deaktiviert die **Sicherheit** auf der Seite die **Projekt-Designer**.  
  
### <a name="to-enable-clickonce-security-settings"></a>ClickOnce-Sicherheitseinstellungen aktivieren  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Sicherheit** .  
  
3.  Aktivieren Sie das Kontrollkästchen **ClickOnce-Sicherheitseinstellungen aktivieren** .  
  
     Sie können jetzt die Sicherheitseinstellungen für Ihre Anwendung auf der Seite "Sicherheit" anpassen.  
  
    > [!NOTE]
    >  Dieses Kontrollkästchen ausgewählt ist automatisch jedes Mal, die die Anwendung veröffentlicht wird, mit der **veröffentlichen** Assistenten.  
  
### <a name="to-disable-clickonce-security-settings"></a>So deaktivieren Sie die ClickOnce-Sicherheitseinstellungen  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Sicherheit** .  
  
3.  Deaktivieren der **Enable ClickOnce Security Settings** Kontrollkästchen.  
  
     Die Anwendung wird mit den Sicherheitseinstellungen für volle Vertrauenswürdigkeit ausgeführt werden; Alle Einstellungen für die **Sicherheit** Seite ignoriert werden.  
  
    > [!NOTE]
    >  Jedes Mal, wenn die Anwendung mit dem Webpublishing-Assistenten veröffentlicht wird, wird dieses Kontrollkästchen aktiviert werden; Sie müssen Sie erneut nach jeder erfolgreichen Veröffentlichung löschen.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ClickOnce-Anwendungen](../deployment/securing-clickonce-applications.md)   
 [Code Access Security for ClickOnce Applications (Codezugriffssicherheit für ClickOnce-Anwendungen)](../deployment/code-access-security-for-clickonce-applications.md)   
 [Sichern von ClickOnce-Anwendungen](../deployment/securing-clickonce-applications.md)




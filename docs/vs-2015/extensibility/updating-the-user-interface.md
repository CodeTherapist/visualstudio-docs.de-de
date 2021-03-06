---
title: Aktualisieren der Benutzeroberfläche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user interfaces, updating
- commands, updating UI
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
caps.latest.revision: 42
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4e6b282ac58e523e8a2047e7f882d90b9f202bf
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765550"
---
# <a name="updating-the-user-interface"></a>Aktualisieren der Benutzeroberfläche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nachdem Sie einen Befehl implementiert haben, können Sie Code zum Aktualisieren der Benutzeroberfläche mit dem Status der Ihre neue Befehle hinzufügen.  
  
 In einer typischen Win32-Anwendung der Befehlssatz ständig abgefragt werden kann, und der Status der einzelnen Befehle angepasst werden kann, wie die Benutzer diese anzeigt. Aber da die [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Shell kann eine unbegrenzte Anzahl von VSPackages, umfangreiche Abruf verringert möglicherweise die Reaktionsfähigkeit, insbesondere über zwischen verwaltetem Code und COM-interop-Assemblys abrufen  
  
### <a name="to-update-the-ui"></a>Zur Aktualisierung der Benutzeroberfläche  
  
1.  Führen Sie einen der folgenden Schritte aus:  
  
    -   Rufen Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A>-Methode auf.  
  
         Ein <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> Schnittstelle abgerufen werden kann, aus der <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> -Dienst wie folgt.  
  
        ```csharp  
        void UpdateUI(Microsoft.VisualStudio.Shell.ServiceProvider sp)  
        {  
            IVsUIShell vsShell = (IVsUIShell)sp.GetService(typeof(IVsUIShell));  
            if (vsShell != null)  
            {  
                int hr = vsShell.UpdateCommandUI(0);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
            }  
        }  
  
        ```  
  
         Wenn der Parameter, der die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> ungleich NULL ist (`TRUE`), und klicken Sie dann das Update synchron und sofort ausgeführt wird. Es wird empfohlen, Sie 0 (NULL übergeben) (`FALSE`) für diesen Parameter, um sicherzustellen, dass eine guten Leistung. Wenn Sie die Zwischenspeicherung vermeiden möchten, wenden Sie die `DontCache` zu kennzeichnen, wenn Sie den Befehl in der VSCT-Datei erstellen. Dennoch das Flag mit Vorsicht verwenden, oder kann die Leistung verringern. Weitere Informationen zu Befehlsflags, finden Sie unter den [Commandflag-Element](../extensibility/command-flag-element.md) Dokumentation.  
  
    -   In VSPackages, auf denen ein ActiveX-Steuerelement mit dem direkten Aktivierung-Modell in einem Fenster gehostet wird, ist es möglicherweise bequemer, mithilfe der <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> Methode. Die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> -Methode in der die <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> Schnittstelle und die <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> -Methode in der die <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> Schnittstelle sind funktional äquivalent. Beide dazu führen, dass die Umgebung den Status aller Befehle erneut abfragen. In der Regel wird ein Update nicht sofort ausgeführt werden. Stattdessen wird ein Update Leerlaufzeit verzögert. Die Shell speichert der Befehlsstatus, um sicherzustellen, dass eine guten Leistung. Wenn Sie die Zwischenspeicherung vermeiden möchten, wenden Sie die `DontCache` zu kennzeichnen, wenn Sie den Befehl in der VSCT-Datei erstellen. Dennoch verwenden Sie das Flag mit Vorsicht, da die Leistung verringern kann.  
  
         Beachten Sie, die Sie erhalten die <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> Schnittstelle durch Aufrufen der `QueryInterface` Methode für ein <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager> Objekt oder durch Abrufen der Schnittstelle vom die <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> Service.  
  
## <a name="see-also"></a>Siehe auch  
 [Wie VSPackages Benutzeroberflächenelemente hinzufügen](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementation (Implementierung)](../extensibility/internals/command-implementation.md)


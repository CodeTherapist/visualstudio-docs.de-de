---
title: 'Vorgehensweise: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4003dd1434d55bb43f52ee02801da0f843563456
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077476"
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Gewusst wie: Festlegen benutzerdefinierter Berechtigungen für eine ClickOnce-Anwendung
Sie können eine [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] -Anwendung bereitstellen, die Standardberechtigungen für die Zonen „Internet“ oder „Lokales Intranet“ verwendet. Alternativ können Sie eine benutzerdefinierte Zone für die spezifischen Berechtigungen erstellen, die die Anwendung benötigt. Diese Berechtigungen können Sie erstellen, indem Sie die Sicherheitsberechtigungen auf der Seite **Sicherheit** des **Projekt-Designers**anpassen.  
  
### <a name="to-customize-a-permission"></a>So passen Sie eine Berechtigung an  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Sicherheit** .  
  
3.  Aktivieren Sie das Kontrollkästchen **ClickOnce-Sicherheitseinstellungen aktivieren** .  
  
4.  Wählen Sie das Optionsfeld **Teilweise vertrauenswürdige Anwendung** aus.  
  
     Die Steuerelemente im Abschnitt **ClickOnce-Sicherheitsberechtigungen** sind aktiviert.  
  
5.  Klicken Sie in der Dropdownliste **Zone, aus der die Anwendung installiert wird** auf **(Benutzerdefiniert)**.  
  
6.  Klicken Sie auf **Berechtigungs-XML bearbeiten**.  
  
     Die *"App.manifest"* Datei wird in der XML-Editor geöffnet.  
  
7.  Fügen Sie vor dem `</applicationRequestMinimum>` -Element den XML-Code für Berechtigungen hinzu, den Ihre Anwendung benötigt.  
  
    > [!NOTE]
    >  Sie können die `ToXml`-Methode einer Berechtigung verwenden, die zum Generieren des XML-Codes für das Anwendungsmanifest festgelegt wurde. Rufen Sie z.B. zum Generieren des XML-Codes für die <xref:System.Security.Permissions.EnvironmentPermission> -Berechtigung die <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> -Methode auf.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ClickOnce-Anwendungen](../deployment/securing-clickonce-applications.md)   
 [Codezugriffssicherheit für ClickOnce-Anwendungen](../deployment/code-access-security-for-clickonce-applications.md)   

---
title: Abonnieren eines Ereignisses | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- running document table (RDT), responding to events
- running document table (RDT), subscribing to events
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
caps.latest.revision: 36
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 77f277a63d08752ddbcb7e25bae4aa82867d280e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512184"
---
# <a name="subscribing-to-an-event"></a>Abonnieren eines Ereignisses
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Abonnieren eines Ereignisses](https://docs.microsoft.com/visualstudio/extensibility/subscribing-to-an-event).  
  
In dieser exemplarischen Vorgehensweise wird erläutert, wie ein Toolfenster erstellen, die auf Ereignisse in eine aktive Dokumenttabelle (RDT) reagiert wird. Ein Toolfenster hostet, ein Benutzersteuerelement, das implementiert <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>. Die <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> Methode verbindet die Schnittstelle für die Ereignisse.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Ab Visual Studio 2015, sind Sie nicht Visual Studio SDK aus dem Downloadcenter installieren. Er ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das VS-SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren von Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="subscribing-to-rdt-events"></a>Abonnieren von RDT-Ereignissen  
  
#### <a name="to-create-an-extension-with-a-tool-window"></a>Zum Erstellen einer Erweiterung mit einem Toolfenster  
  
1.  Erstellen Sie ein Projekt mit dem Namen **RDTExplorer** mithilfe der VSIX-Projektvorlage aus, und fügen Sie der Elementvorlage ein benutzerdefiniertes Tool-Fenster, der mit dem Namen **RDTExplorerWindow**.  
  
     Weitere Informationen zu eine Erweiterung mit einem Toolfenster erstellen, finden Sie unter [erstellen eine Erweiterung mit einem Toolfenster](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
#### <a name="to-subscribe-to-rdt-events"></a>Abonnieren von RDT-Ereignissen  
  
1.  Öffnen Sie die Datei RDTExplorerWindowControl.xaml und die Schaltfläche mit dem Namen "löschen" `button1`. Hinzufügen einer <xref:System.Windows.Forms.ListBox> steuern und den Standardnamen übernehmen. Das Grid-Element sollte folgendermaßen aussehen:  
  
    ```xml  
    <Grid>  
        <StackPanel Orientation="Vertical" Margin="-10,10,10,0">  
            <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock>  
            <ListBox x:Name="listBox" Height="100" />  
        </StackPanel>  
    </Grid>  
    ```  
  
2.  Öffnen Sie die RDTExplorerWindow.cs-Datei, in der Codeansicht. Fügen Sie die folgenden using-Anweisungen am Anfang der Datei.  
  
    ```csharp  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  Ändern der `RDTExplorerWindow` -Klasse daher, dass zusätzlich zum Ableiten von der <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> -Klasse implementiert die <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> Schnittstelle.  
  
    ```csharp  
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents  
    {. . .}  
    ```  
  
4.  Implementieren Sie <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>.  
  
    -   Implementieren der Schnittstelle. Setzen Sie den Cursor auf den Namen des IVsRunningDocTableEvents. Eine Glühbirne am linken Rand sollte angezeigt werden. Klicken Sie auf den Pfeil rechts neben die Glühbirne verlagert, und wählen Sie **Schnittstelle implementieren**.  
  
5.  Ersetzen Sie die Zeile in jeder Methode in der Schnittstelle `throw new NotImplementedException();` dabei:  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
6.  Fügen Sie ein Cookiefeld der RDTExplorerWindow-Klasse.  
  
    ```csharp  
    private uint rdtCookie;   
    ```  
  
     Dies gilt, dass das Cookie, das von zurückgegebene der <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> Methode.  
  
7.  Überschreiben Sie die RDTExplorerWindows Initialize()-Methode für RDT-Ereignissen registriert. Sie sollten immer die ToolWindowPanes Initialize()-Methode, nicht im Konstruktor Dienste abrufen.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
        this.GetService(typeof(SVsRunningDocumentTable));  
        rdt.AdviseRunningDocTableEvents(this, out rdtCookie);  
    }  
    ```  
  
     Die <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> Diensts wird aufgerufen, um das Abrufen einer <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> Schnittstelle. Die <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> Methode verbindet RDT-Ereignissen auf ein Objekt, das implementiert <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>, in diesem Fall ein RDTExplorer-Objekt.  
  
8.  Aktualisieren Sie die RDTExplorerWindows Dispose()-Methode.  
  
    ```csharp  
    protected override void Dispose(bool disposing)  
    {  
        // Release the RDT cookie.  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
            Package.GetGlobalService(typeof(SVsRunningDocumentTable));  
        rdt.UnadviseRunningDocTableEvents(rdtCookie);  
  
        base.Dispose(disposing);  
    }  
    ```  
  
     Die <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnadviseRunningDocTableEvents%2A> -Methode löscht die Verbindung zwischen `RDTExplorer` und RDT-ereignisbenachrichtigung.  
  
9. Fügen Sie die folgende Zeile in den Hauptteil der <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> Handler auf, kurz vor dem Ausführen der `return` Anweisung.  
  
    ```csharp  
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
10. Fügen Sie eine ähnliche Zeile in den Hauptteil der <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterFirstDocumentLock%2A> Handler und mit anderen Ereignissen, die Sie im Listenfeld angezeigt werden sollen.  
  
    ```csharp  
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
11. Erstellen Sie das Projekt, und starten Sie das Debugging. Die experimentelle Instanz von Visual Studio wird angezeigt.  
  
12. Öffnen der **RDTExplorerWindow** (**anzeigen / andere Windows / RDTExplorerWindow**).  
  
     Die **RDTExplorerWindow** Fenster wird geöffnet, mit einer leeren Ereignisses aus.  
  
13. Öffnen Sie oder erstellen Sie eine Lösung.  
  
     Als `OnBeforeLastDocument` und `OnAfterFirstDocument` Ereignisse werden ausgelöst, Benachrichtigung über jedes Ereignis wird in dieser Liste angezeigt.

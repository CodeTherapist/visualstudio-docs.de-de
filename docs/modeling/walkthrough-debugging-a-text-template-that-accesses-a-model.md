---
title: 'Exemplarische Vorgehensweise: Debuggen einer Textvorlage, die auf ein Modell zugreift'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: d2c58579cce95c3117aa7653d62733f4e297bcc4
ms.sourcegitcommit: 768d7877fe826737bafdac6c94c43ef70bf45076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "50966465"
---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>Exemplarische Vorgehensweise: Debuggen einer Textvorlage, die auf ein Modell zugreift
Wenn Sie ändern oder Hinzufügen von Textvorlagen in einer DSL-Projektmappe, erhalten Sie möglicherweise Fehler, wenn die Engine die Vorlage auf den Quellcode oder transformiert bei der Kompilierung des generierten Codes. Die folgende exemplarische Vorgehensweise veranschaulicht einige der Dinge, die Sie tun können, um das Debuggen einer Textvorlage.

> [!NOTE]
>  Weitere Informationen zu Vorlagen im Allgemeinen finden Sie unter [Codegenerierung und T4-Textvorlagen](../modeling/code-generation-and-t4-text-templates.md). Weitere Informationen zum Debuggen von Textvorlagen finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer Textvorlage](debugging-a-t4-text-template.md).

## <a name="creating-a-domain-specific-language-solution"></a>Erstellen einer Lösung einer domänenspezifischen Sprache
 In diesem Verfahren erstellen Sie eine domänenspezifische Sprache-Lösung, die die folgenden Merkmale aufweist:

- Name: DebuggingTestLanguage

- Lösungsvorlage: minimale Sprache

- Dateierweiterung: .ddd

- Firmenname: Fabrikam

  Weitere Informationen zum Erstellen einer DSL-Projektmappe finden Sie unter [Vorgehensweise: Erstellen einer domänenspezifischen Sprachlösung](../modeling/how-to-create-a-domain-specific-language-solution.md).

## <a name="creating-a-text-template"></a>Erstellen einer Textvorlage
 Fügen Sie eine Textvorlage, um Ihre Lösung.

#### <a name="to-create-a-text-template"></a>Zum Erstellen einer Textvorlage

1.  Erstellen Sie die Projektmappe, und starten Sie ihn in den Debugger ausführen. (Auf der **erstellen** Menü klicken Sie auf **Projektmappe neu erstellen**, und klicken Sie dann auf die **Debuggen** im Menü klicken Sie auf **Debuggen starten**.) Eine neue Instanz von Visual Studio öffnet das Projekt debuggen.

2.  Fügen Sie eine Textdatei namens `DebugTest.tt` auf das Projekt debuggen.

3.  Stellen Sie sicher, dass die **benutzerdefiniertes Tool** von DebugTest.tt-Eigenschaftensatz auf `TextTemplatingFileGenerator`.

## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>Debuggen von Direktiven, die Zugriff auf ein Modell aus einer Textvorlage
 Bevor Sie ein Modell über die Anweisungen und Ausdrücke in einer Textvorlage zugreifen können, müssen Sie zuerst auf einen generierten Direktivenprozessor aufrufen. Aufrufen der generierten Direktivenprozessors stellt die Klassen in Ihrem Modell zur Verfügung der Textvorlagencode als Eigenschaften. Weitere Informationen finden Sie unter [zugreifen auf Modelle aus Textvorlagen](../modeling/accessing-models-from-text-templates.md).

 In den folgenden Verfahren Debuggen Sie einen falschen Namen für die Richtlinie und eine falsche Eigenschaftennamen.

#### <a name="to-debug-an-incorrect-directive-name"></a>So debuggen Sie einen falschen Namen für die Richtlinie

1.  Ersetzen Sie den Code in "DebugTest.tt" durch den folgenden Code ein:

    > [!NOTE]
    >  Der Code enthält einen Fehler. Sie werden den Fehler eingeführt, um es zu debuggen.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  In **Projektmappen-Explorer**mit der rechten Maustaste auf "DebugTest.tt", und klicken Sie dann auf **benutzerdefiniertes Tool ausführen**.

     Die **Fehlerliste** dieser Fehler angezeigt:

     **Der Prozessor, der mit dem Namen "DebuggingTestLanguageDirectiveProcessor" unterstützt nicht die Anweisung, die mit dem Namen "ModelRoot". Die Transformation wird nicht ausgeführt werden.**

     In diesem Fall enthält der Direktive Aufruf einen falschen Namen für die Richtlinie an. Sie haben angegeben `modelRoot` wie den Anweisungsnamen, den richtigen Namen für die Richtlinie ist jedoch `DebuggingTestLanguage`.

3.  Doppelklicken Sie auf den Fehler in der **Fehlerliste** Fenster aus, um den Code springen.

4.  Um den Code zu korrigieren, ändern Sie den Anweisungsnamen, `DebuggingTestLanguage`.

     Die Änderung wird hervorgehoben.

    ```csharp
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

    ```vb
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

5.  In **Projektmappen-Explorer**mit der rechten Maustaste auf "DebugTest.tt", und klicken Sie dann auf **benutzerdefiniertes Tool ausführen**.

     Nachdem das System die Textvorlage transformiert und die entsprechende Ausgabedatei generiert. Sie sehen keine Fehler in der **Fehlerliste** Fenster.

#### <a name="to-debug-an-incorrect-property-name"></a>So debuggen Sie einen Namen für die ungültige Eigenschaft

1.  Ersetzen Sie den Code in "DebugTest.tt" durch den folgenden Code ein:

    > [!NOTE]
    >  Der Code enthält einen Fehler. Sie werden den Fehler eingeführt, um es zu debuggen.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  In **Projektmappen-Explorer**mit der rechten Maustaste auf "DebugTest.tt", und klicken Sie dann auf **benutzerdefiniertes Tool ausführen**.

     Die **Fehlerliste** Fenster angezeigt, und einer dieser Fehler angezeigt:

     (C#)

     **Kompilieren von Transformation: Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation "enthält keine Definition für"ExampleModel"**

     (Visual Basic)

     **Kompilieren von Transformation: 'ExampleModel' ist kein Member von "Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation ".**

     In diesem Fall enthält der Textvorlagencode einen Namen für die ungültige Eigenschaft. Sie haben angegeben `ExampleModel` als Namen der Eigenschaft, aber die korrekte Eigenschaft heißt `LibraryModel`. Sie finden den richtigen Eigenschaftennamen in der enthält Parameter, wie im folgenden Code gezeigt:

    ```
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>
    ```

3.  Doppelklicken Sie auf den Fehler in das Fenster "Fehlerliste", um auf den Code zu springen.

4.  Um den Code zu korrigieren, ändern Sie den Namen der Eigenschaft, um `LibraryModel` im Textvorlagencode.

     Die Änderungen werden hervorgehoben.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.LibraryModel #>
    <#
    foreach (ExampleElement element in this.LibraryModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.LibraryModel #>
    <#
    For Each element as ExampleElement in Me.LibraryModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

5.  In **Projektmappen-Explorer**mit der rechten Maustaste auf "DebugTest.tt", und klicken Sie dann auf **benutzerdefiniertes Tool ausführen**.

     Nachdem das System die Textvorlage transformiert und die entsprechende Ausgabedatei generiert. Sie sehen keine Fehler in der **Fehlerliste** Fenster.
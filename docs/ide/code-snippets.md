---
title: Codeausschnitte
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 8ed3f2f8e588aa908827516fee44c1a38ad6a008
ms.sourcegitcommit: bc43970c000f07c9cc2051f1264a9742943a9755
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51348486"
---
# <a name="code-snippets"></a>Codeausschnitte

Codeausschnitte sind kleine Blöcke mit wiederverwendbarem Code, die in einer Codedatei über einen Befehl im Kontextmenü oder eine Kombination von Hotkeys eingefügt werden können. Sie enthalten normalerweise häufig verwendete Codeblöcke, wie z.B. `try-finally`- oder `if-else`-Blöcke, können aber zum Einfügen von ganzen Klassen oder Methoden verwendet werden.

> [!NOTE]
> Dieses Thema gilt für Visual Studio unter Windows. Informationen zu Visual Studio für Mac finden Sie unter [Codeausschnitte (Visual Studio für Mac)](/visualstudio/mac/snippets).

Codeausschnitte sind für viele Sprachen verfügbar, einschließlich C#, C++, Visual Basic, XML und T-SQL. Öffnen Sie den **Codeausschnitt-Manager** in Visual Studio über das Menü **Extras**, und wählen Sie aus der Dropdownliste im oberen Bereich eine Sprache aus. Dann werden Ihnen alle verfügbaren installierten Codeausschnitte für die jeweilige Sprache angezeigt.

![Dialogfeld Codeausschnitt-Manager](media/code-snippets-manager.png)

Es gibt folgende Möglichkeiten, auf Codeausschnitte zuzugreifen:

- Klicken Sie in der Menüleiste auf **Bearbeiten** > **IntelliSense** > **Ausschnitt einfügen**.

- Klicken Sie im Kontextmenü (Rechtsklick) im Code-Editor auf **Ausschnitt** > **Ausschnitt einfügen**.

- Drücken Sie auf der Tastatur die Tasten**STRG**+**K**+**X**.

## <a name="expansion-snippets-and-surround-with-snippets"></a>Erweiterungsausschnitte und umschließende Ausschnitte

In Visual Studio gibt es zwei Arten von Codeausschnitten: Erweiterungsausschnitte, die an einer angegebenen Einfügemarke hinzugefügt werden und eine Ausschnittsverknüpfung ersetzen können, und umschließende Ausschnitte (nur in C# und C++), die um einen ausgewählten Codeblock herum eingefügt werden.

Ein Beispiel für einen Erweiterungsausschnitt: In C# wird die Verknüpfung tryf verwendet, um einen try/finally-Block einzufügen:

```csharp
try
{

}
finally
{

}
```

Sie können diesen Ausschnitt einfügen, indem Sie auf **Ausschnitt einfügen** im Kontextmenü des Codefensters und anschließend auf **Visual C#** klicken, `tryf` eingeben und dann die **TAB-TASTE** drücken. Stattdessen können Sie auch `tryf` eingeben und zweimal die **TAB-TASTE** drücken.

Ein Beispiel für einen Umschließungsausschnitt: In C++ kann die Verknüpfung `if` als Einfügungsausschnitt oder als Umschließungsausschnitt verwendet werden. Wenn Sie eine Codezeile aktivieren (z.B. `return FALSE;`) und dann auf **Umschließen mit** > **if** klicken, wird der Ausschnitt um folgende Zeile erweitert:

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>Ersatzparameter für Ausschnitte

Ausschnitte können Ersatzparameter enthalten, die Platzhalter sind und ersetzt werden müssen, um genau den Code anzupassen, den Sie schreiben. Im vorherigen Beispiel ist `true` ein Ersatzparameter, den Sie durch die entsprechende Bedingung ersetzen. Diese Ersetzung wird für jede Instanz des Ersatzparameters im Ausschnitt wiederholt.

In Visual Basic gibt es z.B. einen Codeausschnitt, der eine Eigenschaft einfügt. Klicken Sie in einer Visual Basic-Codedatei im Kontextmenü (Rechtsklick) auf **Ausschnitt** > **Ausschnitt einfügen**, um den Ausschnitt einzufügen. Klicken Sie dann auf **Codemuster** > **Eigenschaften, Prozeduren, Ereignisse** > **Eigenschaft definieren**.

![Codeausschnittmenü für „Eigenschaft definieren“](media/code-snippets-vb-property.png)

Der folgende Code wird eingefügt:

```vb
Private newPropertyValue As String
Public Property NewProperty() As String
    Get
        Return newPropertyValue
    End Get
    Set(ByVal value As String)
        newPropertyValue = value
    End Set
End Property
```

Wenn Sie `newPropertyValue` in `m_property` ändern, wird jede Instanz von `newPropertyValue` geändert. Wenn Sie `String` in der Eigenschaftendeklaration in `Int` ändern, wird der Wert in der set-Methode ebenfalls in `Int` geändert.

## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Erstellen eines Codeausschnitts](../ide/walkthrough-creating-a-code-snippet.md)
- [Vorgehensweise: Verteilen von Codeausschnitten](../ide/how-to-distribute-code-snippets.md)
- [Bewährte Methoden für die Verwendung von Codeausschnitten](../ide/best-practices-for-using-code-snippets.md)
- [Problembehandlung bei Codeausschnitten](../ide/troubleshooting-snippets.md)
- [C#-Codeausschnitte](../ide/visual-csharp-code-snippets.md)
- [Visual C#-Codeausschnitte](../ide/visual-cpp-code-snippets.md)
- [Schemareferenz für Codeausschnitte](../ide/code-snippets-schema-reference.md)
- [Codeausschnitte (Visual Studio für Mac)](/visualstudio/mac/snippets)
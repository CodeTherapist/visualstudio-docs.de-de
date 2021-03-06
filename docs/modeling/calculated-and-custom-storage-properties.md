---
title: Berechnete und benutzerdefinierte Speichereigenschaften
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, programming domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: f54589d70bc7cab3959d7f0a7ad2a84d3b028754
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49877191"
---
# <a name="calculated-and-custom-storage-properties"></a>Berechnete und benutzerdefinierte Speichereigenschaften
Alle Domäneneigenschaften in einer domänenspezifischen Sprache (DSL) können für den Benutzer auf das Diagramm und in Ihrer Sprache-Explorer angezeigt werden, und können über Programmcode zugegriffen werden. Unterscheiden sich jedoch die Eigenschaften auf die Weise, dass ihre Werte gespeichert werden.

## <a name="kinds-of-domain-properties"></a>Arten von Domäneneigenschaften
 Sie können in der DSL-Definition Festlegen der **Art** einer Domäneneigenschaft, wie in der folgenden Tabelle aufgeführt:

|Art der Domäne-Eigenschaft|Beschreibung|
|-|-|
|**Standard** (Standard)|Eine Eigenschaft "Domain", die in gespeichert ist die *speichern* und in der Datei serialisiert.|
|**Berechnet**|Eine schreibgeschützte-Eigenschaft, die nicht im Speicher gespeichert, sondern aus anderen Werten berechnet.<br /><br /> Z. B. `Person.Age` konnte aus berechnet `Person.BirthDate`.<br /><br /> Sie müssen den Code bereitstellen, der Berechnung ausführt. In der Regel können Sie den Wert von anderen Domäneneigenschaften berechnen. Sie können jedoch auch externe Ressourcen verwenden.|
|**Benutzerdefinierten Speicher**|Eine Domäneneigenschaft, die nicht direkt im Speicher gespeichert, aber sowohl get- und Set werden kann.<br /><br /> Sie müssen die Methoden bereit, die den Wert abrufen und festlegen.<br /><br /> Z. B. `Person.FullAddress` konnte gespeichert werden, `Person.StreetAddress`, `Person.City`, und `Person.PostalCode`.<br /><br /> Sie können auch externe Ressourcen, z. B. zum Abrufen und Festlegen von Werten aus einer Datenbank zugreifen.<br /><br /> Ihr Code sollte nicht die Werte festgelegt, im Speicher bei `Store.InUndoRedoOrRollback` ist "true". Finden Sie unter [Transaktionen und benutzerdefinierten Setter](#setters).|

## <a name="providing-the-code-for-a-calculated-or-custom-storage-property"></a>Den Code bereitstellen für eine Eigenschaft für die berechneten oder benutzerdefinierten Speicher.
 Wenn Sie die Art der Eigenschaft "Domain" eine berechnete oder benutzerdefinierten Speicher festlegen, müssen Sie Methoden für den Datenzugriff zu bieten. Wenn Sie die Projektmappe erstellen, informiert ein Fehlerbericht Sie was erforderlich ist.

#### <a name="to-define-a-calculated-or-custom-storage-property"></a>Zum Definieren einer berechneten oder benutzerdefinierte Storage-Eigenschaft

1.  Wählen Sie in "DslDefinition.DSL", die Eigenschaft "Domain" im Diagramm oder im **DSL-Explorer**.

2.  In der **Eigenschaften** legen die **Art** Feld **berechnete** oder **benutzerdefinierten Speicher**.

     Stellen Sie sicher, dass Sie auch festlegen, haben die **Typ** auf die gewünschte.

3.  Klicken Sie auf **alle Vorlagen transformieren** auf der Symbolleiste des **Projektmappen-Explorer**.

4.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

     Sie erhalten die folgende Fehlermeldung angezeigt: "*Ihreklasse* enthält keine Definition für Get*YourProperty*."

5.  Doppelklicken Sie auf die Fehlermeldung angezeigt.

     Dsl\GeneratedCode\DomainClasses.cs oder DomainRelationships.cs wird geöffnet. Über den hervorgehobenen Methodenaufruf, ein Kommentar aufgefordert, eine Implementierung für Get bereitstellen*YourProperty*().

    > [!NOTE]
    >  Diese Datei wird aus "DslDefinition.DSL" generiert. Wenn Sie diese Datei bearbeiten, Ihre Änderungen verloren das nächste Mal, die Sie klicken **alle Vorlagen transformieren**. Fügen Sie stattdessen die erforderliche Methode in einer separaten Datei hinzu.

6.  Erstellen oder öffnen Sie eine Datei in einem separaten Ordner, z. B. CustomCode\\*YourDomainClass*. Cs.

     Stellen Sie sicher, dass der Namespace des generierten Codes identisch ist.

7.  Schreiben Sie eine partielle Implementierung der Domänenklasse in der Klassendatei. Schreiben Sie in der Klasse, eine Definition für die fehlende `Get` -Methode, die das folgende Beispiel ähnelt:

    ```
    namespace Company.FamilyTree
    {  public partial class Person
       {  int GetAgeValue()
          { return System.DateTime.Today.Year - this.BirthYear; }
    }  }
    ```

8.  Setzen Sie **Art** zu **benutzerdefinierten Speicher**, außerdem müssen Sie zu einer `Set` Methode. Zum Beispiel:

    ```
    void SetAgeValue(int value)
    { if (!Store.InUndoRedoOrRollback)
        this.BirthYear =
            System.DateTime.Today.Year - value; }
    ```

     Ihr Code sollte nicht die Werte festgelegt, im Speicher bei `Store.InUndoRedoOrRollback` ist "true". Finden Sie unter [Transaktionen und benutzerdefinierten Setter](#setters).

9. Erstellen Sie die Projektmappe, und führen Sie sie aus.

10. Testen Sie die Eigenschaft an. Stellen Sie sicher, dass Sie versuchen **Rückgängig** und **wiederholen**.

##  <a name="setters"></a> Transaktionen und benutzerdefinierten Setter
 In der Set-Methode der Eigenschaft des benutzerdefinierten Speicher müssen Sie keinen zu eine Transaktion zu öffnen, da die Methode in der Regel innerhalb einer aktiven Transaktion aufgerufen wird.

 Die Set-Methode kann jedoch auch aufgerufen werden, wenn der Benutzer zum Rückgängigmachen oder Wiederholen aufruft, oder wenn eine Transaktion ein Rollback ausgeführt wird. Wenn <xref:Microsoft.VisualStudio.Modeling.Store.InUndoRedoOrRollback%2A> ist "true", die Set-Methode sollte Verhalten sich wie folgt:

- Es sollten keine Änderungen im Speicher, z. B. das Zuweisen von Werten zu einer anderen Domäneneigenschaften vornehmen. Der annullierungsmanager, werden ihre Werte festgelegt.

- Sie sollten jedoch alle externen Ressourcen, z. B. Datenbank bzw. des Dateiinhalts oder Objekten außerhalb des Speichers aktualisieren. Dadurch wird sichergestellt, die sie in Synchronism mit den Werten im Speicher gehalten werden.

  Zum Beispiel:

```
void SetAgeValue(int value)
{
  // If we are in Undo, no changes to Store objects:
  if (!this.Store.InUndoRedoOrRollback)
  {
    this.BirthYear = System.DateTime.Today.Year - value;
  }
  // But always update external objects:
  System.IO.File.WriteAllText(AgeFile, value);
}
```

 Weitere Informationen über Transaktionen finden Sie unter [Navigieren in und Aktualisieren von Modellen im Programmcode](../modeling/navigating-and-updating-a-model-in-program-code.md).

## <a name="see-also"></a>Siehe auch

- [Navigieren in und Aktualisieren von Modellen im Programmcode](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Eigenschaften von Domäneneigenschaften](../modeling/properties-of-domain-properties.md)
- [So definieren Sie eine domänenspezifische Sprache](../modeling/how-to-define-a-domain-specific-language.md)
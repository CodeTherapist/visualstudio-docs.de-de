---
title: 'Vorgehensweise: Erstellen eines Adapters für diagnostische Daten in Visual Studio'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating
ms.assetid: bd7ad36c-54cb-4d2a-9aea-9d10ad98d7ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 25b332fb822524f5fcab5e06ab97bfe2d6af8529
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49851607"
---
# <a name="how-to-create-a-diagnostic-data-adapter"></a>Vorgehensweise: Erstellen eines Adapters für diagnostische Daten

Zum Erstellen eines *Adapters für diagnostische Daten* müssen Sie mit Visual Studio eine Klassenbibliothek erstellen und dann die APIs der Adapter für diagnostische Daten hinzufügen, die Visual Studio Enterprise für die Klassenbibliothek bereitstellt. Senden Sie alle gewünschten Informationen als Datenstrom oder Datei an das vom Framework bereitgestellte <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>-Objekt, wenn Sie die Ereignisse behandeln, die während des Testlaufs ausgelöst werden. Die Streams oder Dateien, die an den <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> gesendet wurden, werden bei Beendigung des Tests als Anlagen zu den Testergebnissen gespeichert. Wenn Sie aus diesen Testergebnissen einen Fehler erstellen, oder wenn Sie [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)] verwenden, werden die Dateien ebenfalls mit dem Fehler verknüpft.

 Sie können einen Adapter für diagnostische Daten erstellen, der sich auf den Computer auswirkt, auf dem die Tests ausgeführt werden, oder einen Adapter mit Auswirkung auf einen Computer, der Teil der Umgebung ist, die für die Ausführung der getesteten Anwendung verwendet wird. Sie können beispielsweise Dateien auf dem Testcomputer, auf dem die Tests ausgeführt werden, oder Dateien auf dem Computer erfassen, der in der Webserverrolle für die Anwendung verwendet wird.

 Sie können dem Adapter für diagnostische Daten einen Anzeigenamen geben, der erscheint, wenn Sie die Testeinstellungen mithilfe von Microsoft Test Manager oder Visual Studio erstellen. Mit Testeinstellungen kann definiert werden, mit welcher Computerrolle bestimmte Adapter für diagnostische Daten in der Umgebung ausgeführt werden, wenn die Tests ausgeführt werden. Sie können die Adapter für diagnostische Daten auch beim Erstellen der Testeinstellungen konfigurieren. Sie können beispielsweise einen Adapter für diagnostische Daten erstellen, der benutzerdefinierte Protokolle vom Webserver abholt. Beim Erstellen von Testeinstellungen können Sie festlegen, dass dieser Adapter für diagnostische Daten auf dem Computer oder den Computern ausgeführt wird, die die Webserverrolle ausführen, und Sie können die Konfiguration Ihrer Testeinstellungen so ändern, dass nur die letzten drei erstellten Protokolle erfasst werden. Weitere Informationen zu Testeinstellungen finden Sie unter [Erfassen von Diagnoseinformationen mithilfe von Testeinstellungen](../test/collect-diagnostic-information-using-test-settings.md).

 Beim Ausführen der Tests werden Ereignisse ausgelöst, sodass der Adapter für diagnostische Daten Aufgaben an dieser Stelle im Test ausführen kann.

> [!IMPORTANT]
> Diese Ereignisse werden möglicherweise in verschiedenen Threads ausgelöst, insbesondere, wenn Tests auf mehreren Computern ausgeführt werden. Daher müssen Sie sich möglicher Threadingprobleme bewusst sein und darauf achten, nicht versehentlich die internen Daten des benutzerdefinierten Adapters zu beschädigen. Stellen Sie sicher, dass der Adapter für diagnostische Daten threadsicher ist.

 Nachfolgend sehen Sie eine partielle Liste mit Schlüsselereignissen, die Sie beim Erstellen des Adapters für diagnostische Daten verwenden können. Eine vollständige Liste von Ereignissen in Zusammenhang mit Adaptern für diagnostische Daten finden Sie in der abstrakten <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>-Klasse.

|event|Beschreibung |
|-|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionStart>|Start des Testlaufs|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionEnd>|Ende des Testlaufs|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseStart>|Start jedes Tests im Testlauf|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseEnd>|Ende jedes Tests im Testlauf|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepStart>|Start jedes Testschritts in einem Test|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepEnd>|Ende jedes Testschritts in einem Test|

> [!NOTE]
> Nach Abschluss eines manuellen Tests werden keine weiteren Datensammlungsereignisse mehr an den Adapter für diagnostische Daten gesendet. Wenn ein Test erneut ausgeführt wird, erhält er einen neuen Testfallbezeichner. Wenn ein Benutzer während eines Tests einen Test zurücksetzt (wodurch das <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseReset>-Ereignis ausgelöst wird) oder ein Testschrittergebnis geändert wird, wird kein Datensammlungsereignis an den Adapter für diagnostische Daten gesendet, doch der Testfallbezeichner bleibt identisch. Sie müssen den Testfallbezeichner im Adapter für diagnostische Daten verfolgen, um zu ermitteln, ob ein Testfall zurückgesetzt wurde.

 Führen Sie die folgenden Schritte aus, um einen Adapter für diagnostische Daten zu erstellen, der eine Datendatei auf der Basis von Informationen erfasst, die Sie beim Erstellen der Testeinstellungen konfigurieren.

 Ein vollständiges Beispielprojekt für Adapter für diagnostische Daten, einschließlich eines benutzerdefinierten Konfigurations-Editors, finden Sie unter [Beispielprojekt für das Erstellen eines Adapters für diagnostische Daten](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

##  <a name="create-and-install-a-diagnostic-data-adapter"></a>Erstellen und Installieren eines Adapters für diagnostische Daten

### <a name="to-create-and-install-a-diagnostic-data-adapter"></a>So erstellen und installieren Sie einen Adapter für diagnostische Daten

1. Erstellen Sie eine neue Klassenbibliothek.

   1.  Wählen Sie im Menü **Datei** die Option **Neu**, und zeigen Sie dann auf **Neues Projekt**.

   2.  Wählen Sie unter **Projekttypen** die zu verwendende Sprache aus.

   3.  Wählen Sie unter **Von Visual Studio installierte Vorlagen** die Option **Klassenbibliothek** aus.

   4.  Geben Sie einen Namen für den Adapter für diagnostische Daten ein.

   5.  Klicken Sie auf **OK**.

2. Fügen Sie die Assembly **Microsoft.VisualStudio.QualityTools.ExecutionCommon** hinzu.

   1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise**, und wählen Sie den Befehl **Verweis hinzufügen** aus.

   2.  Wählen Sie **.NET** aus, und suchen Sie **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

   3.  Klicken Sie auf **OK**.

3. Fügen Sie die Assembly **Microsoft.VisualStudio.QualityTools.Common** hinzu.

   1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise**, und wählen Sie den Befehl **Verweis hinzufügen** aus.

   2.  Wählen Sie **/.NET** aus, und suchen Sie **Microsoft.VisualStudio.QualityTools.Common.dll**.

   3.  Klicken Sie auf **OK**.

4. Fügen Sie der Klassendatei die folgenden `using`-Anweisungen hinzu:

   ```csharp
   using Microsoft.VisualStudio.TestTools.Common;
   using Microsoft.VisualStudio.TestTools.Execution;
   using System.Linq;
   using System.Text;
   using System.Xml;
   using System;
   ```

5. Fügen Sie das <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute> der Klasse für Ihren Adapter für diagnostische Daten hinzu, damit dieser als Adapter für diagnostische Daten identifiziert werden kann, und ersetzen Sie dabei **Firma**, **Produkt** und **Version** durch die entsprechenden Informationen für den Adapter für diagnostische Daten:

   ```csharp
   [DataCollectorTypeUri("datacollector://Company/Product/Version")]
   ```

6. Fügen Sie der Klasse das <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>-Attribut hinzu, und ersetzen Sie dabei die Parameter durch die entsprechenden Informationen für den Adapter für diagnostische Daten:

   ```csharp
   [DataCollectorFriendlyName("Collect Log Files", false)]
   ```

    Dieser Anzeigename wird in der Aktivität "Testeinstellungen" angezeigt.

   > [!NOTE]
   > Sie können auch das <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> hinzufügen, um den `Type` des benutzerdefinierten Konfigurations-Editors für diesen Datenadapter anzugeben und um optional die für den Editor zu verwendende Hilfedatei anzugeben.
   >
   > Sie können auch das <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute> anwenden, um anzugeben, dass es immer aktiviert werden soll.

7. Die Klasse für den Adapter für diagnostische Daten muss wie folgt von der <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector>-Klasse erben:

   ```csharp
   public class MyDiagnosticDataAdapter : DataCollector
   ```

8. Fügen Sie die lokalen Variablen wie folgt hinzu:

   ```csharp
   private DataCollectionEvents dataEvents;
   private DataCollectionLogger dataLogger;
   private DataCollectionSink dataSink;
   private XmlElement configurationSettings;
   ```

9. Fügen Sie die <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector.Initialize*>-Methode und eine **Dispose**-Methode hinzu. In der `Initialize`-Methode können Sie die Datensenke, möglicherweise vorhandene Konfigurationsdaten aus Testeinstellungen und die Ereignisse und die gewünschten Ereignishandler auf folgende Weise initialisieren:

    ```csharp
    public override void Initialize(
        XmlElement configurationElement,
        DataCollectionEvents events,
        DataCollectionSink sink,
        DataCollectionLogger logger,
        DataCollectionEnvironmentContext environmentContext)
    {
           dataEvents = events;  // The test events
           dataLogger = logger;  // The error and warning log
           dataSink = sink;      // Saves collected data
           // Configuration from the test settings
           configurationSettings = configurationElement;

           // Register common events for the data collector
           // Not all of the events are used in this class
        dataEvents.SessionStart +=
            new EventHandler<SessionStartEventArgs>(OnSessionStart);
        dataEvents.SessionEnd +=
            new EventHandler<SessionEndEventArgs>(OnSessionEnd);
        dataEvents.TestCaseStart +=
            new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
        dataEvents.TestCaseEnd +=
            new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
    }

    public override void Dispose(bool disposing)
    {
        if (disposing)
        {
            // Unregister the registered events
            dataEvents.SessionStart -=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd -=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart -=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd -=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
        }
    }
    ```

10. Verwenden Sie den folgenden Ereignishandlercode und die folgende private Methode, um die während des Tests generierte Protokolldatei zu sammeln:

    ```csharp
    public void OnTestCaseEnd(sender, TestCaseEndEventArgs e)
    {
        // Get any files to be collected that are
        // configured in your test settings
        List<string> files = getFilesToCollect();

        // For each of the files, send the file to the data sink
        // which will attach it to the test results or to a bug
        foreach (string file in files)
        {
            dataSink.SendFileAsync(e.Context, file, false);
        }
    }

    // A private method that returns the file names
    private List<string> getFilesToCollect()
    {
        // Get a namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                configurationSettings.OwnerDocument.NameTable);
        nsmgr.AddNamespace("ns",
            "http://MyCompany/schemas/MyDataCollector/1.0");

        // Find all of the "File" elements under our configuration
        XmlNodeList files =
            configurationSettings.SelectNodes(
                "//ns:MyDataCollector/ns:File");

        // Build the list of files to collect from the
        // "FullPath" attributes of the "File" nodes.
        List<string> result = new List<string>();
        foreach (XmlNode fileNode in files)
        {
            XmlAttribute pathAttribute =
                fileNode.Attributes["FullPath"];
            if (pathAttribute != null &&
                !String.IsNullOrEmpty(pathAttribute.Value))
            {
                result.Add(pathAttribute.Value);
            }
        }

        return result;
    }
    ```

     Diese Dateien werden an die Testergebnisse angefügt. Wenn Sie aus diesen Testergebnissen einen Fehler erstellen oder [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)] verwenden, werden die Dateien ebenfalls an den Fehler angefügt.

     Lesen Sie [How to: Create a Custom Editor for Data for Your Diagnostic Data Adapter (Vorgehensweise: Erstellen eines benutzerdefinierten Editors für Daten im Adapter für diagnostische Daten)](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md), wenn Sie Ihren eigenen Editor zum Sammeln von Daten für die Verwendung in Ihren Testeinstellungen verwenden möchten.

11. Wenn Sie beim Abschluss eines Tests eine Protokolldatei auf Grundlage von Testeinstellungen des Benutzers sammeln möchten, müssen Sie eine *App.config*-Datei erstellen und diese zur Projektmappe hinzufügen. Diese Datei hat das folgende Format und muss den URI für den Adapter für diagnostische Daten enthalten, um diesen zu identifizieren. Ersetzen Sie "Unternehmen", "Produktname" und "Version" durch echte Werte.

    > [!NOTE]
    > Wenn Sie keine Informationen für den Adapter für diagnostische Daten konfigurieren müssen, müssen Sie keine Konfigurationsdatei erstellen.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <configSections>
        <section name="DataCollectorConfiguration" type="Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationSection, Microsoft.VisualStudio.QualityTools.ExecutionCommon, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a "/>
      </configSections>
      <DataCollectorConfiguration xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/2010">
        <DataCollector typeUri="datacollector://MyCompany/MyProduct/1.0">
          <DefaultConfiguration>
            <!-- Your default config settings -->
            <Binaries>
              <Binary FullPath="C:\Example\Example.dll"/>
              <Binary FullPath="\\Server2\Example2.dll"/>
            </Binaries>
            <Symbols>
              <Symbol FullPath="\\ExampleServer\ExampleSymbol.pdb"/>
            </Symbols>
          </DefaultConfiguration>
        </DataCollector>
      </DataCollectorConfiguration>
    </configuration>
    ```

    > [!NOTE]
    > Das Standardkonfigurationselement kann alle Daten enthalten, die Sie benötigen. Wenn der Benutzer den Adapter für diagnostische Daten nicht in Testeinstellungen konfiguriert, werden die Standarddaten bei der Ausführung an den Adapter für diagnostische Daten übergeben. Da der XML-Code, den Sie im `<DefaultConfigurations>`-Abschnitt hinzufügen, wahrscheinlich nicht Teil des deklarierten Schemas ist, können Sie alle dadurch generierten XML-Fehler ignorieren.
    >
    > Weitere Beispiele für Konfigurationsdateien finden Sie abhängig vom Installationsverzeichnis im folgenden Pfad: *Program Files\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\DataCollectors*.

     Weitere Informationen zum Konfigurieren der Testeinstellungen zum Verwenden einer Umgebung beim Ausführen von Tests finden Sie unter [Collect diagnostic data in manual tests (Azure Test Plans) (Sammeln von Diagnosedaten in manuellen Tests (Azure Test Plans))](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts).

     Weitere Informationen zum Installieren der Konfigurationsdatei finden Sie unter [How to: Install a Custom Diagnostic Data Adapter (Vorgehensweise: Installieren eines benutzerdefinierten Adapters für diagnostische Daten)](../test/how-to-install-a-custom-diagnostic-data-adapter.md)

12. Erstellen Sie die Projektmappe, um das Assembly des Adapters für diagnostische Daten zu erstellen.

13. Informationen zum Installieren des benutzerdefinierten Editors finden Sie unter [How to: Install a Custom Diagnostic Data Adapter (Vorgehensweise: Installieren eines benutzerdefinierten Adapters für diagnostische Daten)](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

14. Weitere Informationen zum Konfigurieren der Testeinstellungen zum Verwenden einer Umgebung beim Ausführen von Tests finden Sie unter [Collect diagnostic data in manual tests (Azure Test Plans) (Sammeln von Diagnosedaten in manuellen Tests (Azure Test Plans))](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts).

15. Zum Auswählen des Adapters für diagnostische Daten müssen Sie zunächst vorhandene Testeinstellungen auswählen oder neue Testeinstellungen in Microsoft Test Manager oder Visual Studio erstellen. Der Adapter wird auf der Registerkarte **Daten und Diagnose** der Testeinstellungen mit dem Anzeigenamen angezeigt, den Sie der Klasse zugewiesen haben.

16. Legen Sie diese Testeinstellungen auf Aktiv fest. Weitere Informationen zu Testeinstellungen finden Sie unter [Erfassen von Diagnoseinformationen mithilfe von Testeinstellungen](../test/collect-diagnostic-information-using-test-settings.md).

17. Führen Sie die Tests unter Verwendung der Testeinstellungen aus, wenn der Adapter für diagnostische Daten ausgewählt ist.

    Die von Ihnen angegebene Datendatei wird an die Testergebnisse angefügt.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute>
- [Sammeln von Diagnoseinformationen mithilfe von Testeinstellungen](../test/collect-diagnostic-information-using-test-settings.md)
- [Collect diagnostic data in manual tests (Azure Test Plans) (Sammeln von Diagnosedaten in manuellen Tests (Azure Test Plans))](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts)
- [Collect diagnostic data while testing (Azure Test Plans) (Sammeln von Diagnosedaten beim Testen (Azure Test Plans))](/azure/devops/test/collect-diagnostic-data?view=vsts)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Editors für Daten für Ihren Adapter für diagnostische Daten](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
---
title: R-Tools für Visual Studio
description: R Tools für Visual Studio (RTVS) ist eine kostenlose Open-Source-Erweiterung, die viele Sprachfeatures bereitstellt, z.B. IntelliSense, Debuggen und Remotearbeitsbereiche.
ms.date: 11/13/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 05ffd249be3d7734979f3a131a3a10423b76cb9d
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "35667014"
---
# <a name="work-with-r-in-visual-studio"></a>Arbeiten mit R in Visual Studio

R ist eine hochgradig erweiterbare Sprache und Umgebung für die statistische Berechnungen und Grafiken. Die Sprache wird kostenlos unter der GNU General Public License (GNU GPL) bereitgestellt, wird von einer starken Community unterstützt und ist für ihre Fähigkeit bekannt, hochwertige Plots einschließlich mathematischer Symbole und Formeln zu erzeugen. Weitere Informationen zu R erhalten Sie unter [r-project.org](https://www.r-project.org/about.html) und [An Introduction to R](https://cran.r-project.org/doc/manuals/r-release/R-intro.html) (Einführung in R).

R Tools für Visual Studio (RTVS) ist eine kostenlose [Open Source](https://github.com/microsoft/RTVS)-Erweiterung für Visual Studio 2017 und Visual Studio 2015 Update 3 (oder höher) und wurde unter der MIT-Lizenz veröffentlicht. (Eine zweite Open Source-Komponente namens [RHost](https://github.com/microsoft/R-Host), die eine Verknüpfung mit den Binärdateien des R-Interpreters bietet, wurde unter der GNU Public License V2 veröffentlicht.)

> [!Note]
> RTVS wird derzeit nur in Visual Studio unter Windows und nicht in Visual Studio für Mac unterstützt.

Gehen Sie folgendermaßen vor, um mit R in Visual Studio zu arbeiten:

- [Installieren Sie R Tools](installing-r-tools-for-visual-studio.md).
- Befolgen Sie die Anweisungen im Leitfaden zu den [ersten Schritten](getting-started-with-r.md) sowie in den Artikeln [Beispiele](getting-started-samples.md) und [Anzeigen der Hilfe](getting-started-help.md).

Folgen Sie anschließend den unten stehenden Links, um mehr über R-Features sowie über die allgemeinen Features von Visual Studio zu erfahren.

| Feature | Beschreibung  | Allgemeine Visual Studio-Dokumentation |
| --- | --- | --- |
| [Visual Studio-Projektsystem](r-projects-in-visual-studio.md) | Organisieren und verwalten Sie verknüpfte Dateien in einer praktischen Struktur, und profitieren Sie von nützlichen Vorlagen für Elemente wie R-Code, R-Dokumentation, R Markdown, SQL-Abfragen und gespeicherte Prozeduren. Nutzen Sie zudem den [Paket-Manager](r-package-manager-in-visual-studio.md) und die [SQL Server-Integration](integrating-sql-server-with-r.md).  | [Projektmappen und Projekte in Visual Studio](../ide/solutions-and-projects-in-visual-studio.md) |
| [Arbeitsbereich](r-workspaces-in-visual-studio.md) | RTVS kann in lokale und Remotearbeitsbereiche eingebunden werden – so können Sie R-Code lokal mit kleineren Datasets entwickeln, den Code dann auf leistungsfähigeren cloudbasierten Computern mit wesentlich größeren Datasets ausführen. | n/v |
| [Optionen für R Tools](options-for-r-tools-in-visual-studio.md) | Steuern Sie verschiedene Aspekte von RTVS. | [Dialogfeld „Optionen“](../ide/reference/options-dialog-box-visual-studio.md) |
| [Vielfältige Bearbeitungsfunktionen, IntelliSense und Codeausschnitte](editing-r-code-in-visual-studio.md) | Umfasst Syntaxfarben, [IntelliSense](r-intellisense.md) über den gesamten Code und allen Bibliotheken hinweg, Codeformatierung, Signaturhilfe, „Gehe zu Definition“, „Alle Verweise suchen“, [Codeausschnitte](code-snippets-for-r.md) und vieles mehr. | [Features des Code-Editors](../ide/writing-code-in-the-code-and-text-editor.md) |
| [R Markdown](rmarkdown-with-r-in-visual-studio.md) | Mit R Markdown-Dokumenten können Sie Ihre Datenergebnisse mit integriertem R-Code in Markdowncodeblöcken freigeben. | n/v |
| [Interaktives Fenster](interactive-repl-for-r-in-visual-studio.md) | Dieses Fenster bietet eine vollständige REPL-Oberfläche für R, mit der Sie Code in einer Quelldatei im interaktiven Fenster ausführen können. | n/v |
| [Visualisieren von Daten](visualizing-data-with-r-in-visual-studio.md) | Plotting ist ein wesentlicher Bestandteil von R, und RTVS unterstützt mehrere, voneinander unabhängige Plotfenster. Jedes Fenster bietet einen eigenen Verlauf, und Sie können Plots zwischen Fenstern verschieben. Plots können in Bitmap- und PDF-Dateien gespeichert oder als Bitmap- oder Metadatei in die Zwischenablage kopiert werden.  | n/v |
| [Variablen-Explorer](variable-explorer.md) | Untersuchen Sie Variablen auf globaler oder paketspezifischer Ebene, zeigen Sie sortierbare Tabellen an, und exportieren Sie diese in das CSV-Format. | n/v |
| [Vollständige Debugfeatures](debugging-r-in-visual-studio.md) | Umfasst die Integration in das interaktive Fenster. | [Debuggen in Visual Studio](../debugger/debugging-in-visual-studio.md) |

Weitere Informationen finden Sie auch unter [Häufig gestellte Fragen](faq.md).

|   |   |
|---|---|
| ![Kamerasymbol für Video](../install/media/video-icon.png "Video ansehen") | [Im Video (youtube.com)](https://www.youtube.com/watch?v=dll3IS1bfWQ) finden Sie eine Übersicht zu R-Tools für Visual Studio (12 Minuten 36 Sekunden). Informationen finden Sie auch in [weiteren Videos über R-Tools](https://www.youtube.com/results?search_query=R+Tools+for+visual+studio). |

## <a name="send-us-your-feedback"></a>Senden Sie uns Ihr Feedback!

1. **GitHub-Probleme**: Sie erreichen das RTVS-Team am besten, indem Sie ein [Problem auf GitHub melden](https://github.com/Microsoft/RTVS/issues) oder das Menü **R Tools** > **Feedback** verwenden.

1. **Ein Lächeln oder ein Stirnrunzeln senden**: Das Menü **R Tools** > **Feedback** bietet eine schnelle Möglichkeit, Feedback zu senden und RTVS-Protokolldateien anzufügen, die bei der Diagnose Ihres Problems helfen können. (Protokolle werden in *%temp%/RTVSlogs.zip* geschrieben, falls Sie sie separat senden möchten.) Die Protokollierung ist deaktiviert, falls Sie die Visual Studio-Telemetrie über den Menübefehl **Hilfe** > **Feedback** > **Einstellungen** oder während der Installation deaktiviert haben.

1. **E-Mail**: Sie können unter *rtvsuserfeedback (at) microsoft.com* direktes Feedback an das Team senden.

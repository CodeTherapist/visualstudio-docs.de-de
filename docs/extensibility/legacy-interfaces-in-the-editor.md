---
title: Legacy-Schnittstellen im Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5fdabadc1c3a0b5deda42aa268607e0f764e9b7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49849930"
---
# <a name="legacy-interfaces-in-the-editor"></a>Legacy-Schnittstellen im editor
Sie können Visual Studio-Editor von legacy-Schnittstelle zugreifen. Visual Studio SDK umfasst Adapter, die als bekannt *Shims*, die es ermöglichen, diese Schnittstellen für die Interaktion mit den neuen Editor. Dennoch wird empfohlen, dass Sie Ihren Legacycode Verwendung des neuen Editors für API aktualisieren. Ihr Code bieten eine bessere Leistung und Sie können neue Technologien wie Windows Presentation Foundation (WPF) und das Managed Extensibility Framework (MEF).  

## <a name="related-topics"></a>Verwandte Themen  

| Titel | Beschreibung |
| - | - |
| [Anpassen von legacy-Code in den editor](../extensibility/adapting-legacy-code-to-the-editor.md) | Erläutert, wie Sie Ihren Code an den neuen Editor anpassen. |
| [Neues oder Geändertes Verhalten mit Editor-Adaptern](../extensibility/new-or-changed-behavior-with-editor-adapters.md) | Erläutert, wie sich das Verhalten der Editor für Adapter aus, die von früheren Versionen des Editors unterscheidet. |
| [In der Kern-editor](../extensibility/inside-the-core-editor.md) | Beschreibt die verschiedenen Komponenten von früheren Versionen des Editors. |
| [Instanziieren Sie die Kern-Editor, indem Sie die legacy-API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md) | Es wird erläutert, wie die legacy-API zu verwenden, um die Kern-Editor zu instanziieren. |
| [Editorfactorys](../extensibility/editor-factories.md) | Erläutert, wie Sie editorfactorys mit der legacy-API verwenden können. |
| [Gewusst wie: Registrieren des Editor-Dateitypen](../extensibility/how-to-register-editor-file-types.md) | Erläutert, wie eine Dateinamenerweiterung mit den Editor zu verknüpfen. |
| [Exemplarische Vorgehensweise: Erstellen Sie einen Kern-Editor, und registrieren Sie einen Editor-Dateityp](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md) | Erläutert, wie einen Kern-Editor erstellen und verknüpfen eine Dateinamenerweiterung, darauf. |
| [Gewusst wie: Bereitstellen von Kontext für Editoren](../extensibility/how-to-provide-context-for-editors.md) | Erläutert das Kontext für den Editor bereitzustellen. |
| [Sprachdienste und die Kern-editor](../extensibility/language-services-and-the-core-editor.md) | Erläutert, die Interaktionen zwischen einem Sprachdienst und einen Editor. |
| [Zugriff auf den Textpuffer mithilfe der legacy-API](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md) | Erläutert, wie auf den Textpuffer mithilfe der legacy-API. |
| [Access TheText-Ansicht mit der legacy-API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md) | Erläutert, wie die Ansicht für den Zugriff mithilfe der legacy-API auf. |
| [Anpassen von Fenstern des Code mit der legacy-API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md) | Erläutert das Codefenster anpassen, indem Sie mit der legacy-API. |
| [Text Datenzugriffsebenen mithilfe der legacy-API](../extensibility/accessing-text-layers-by-using-the-legacy-api.md) | Erläutert, wie auf verschiedenen Ebenen von Text mithilfe der legacy-API. |
| [Verwenden von Textmarkierungen mit der legacy-API](../extensibility/using-text-markers-with-the-legacy-api.md) | Erläutert das Textmarkierungen hinzufügen, indem Sie mit der legacy-API. |
| [Passen Sie Editor-Steuerelemente und Menüs an, indem Sie mithilfe der legacy-API](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md) | Erläutert das Editor-Steuerelemente anpassen, indem Sie mit der legacy-API. |
| [Verwalten von zum Rückgängigmachen und wiederherstellen, indem Sie mit der legacy-API](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md) | Erläutert, wie "Rückgängig" zu verwalten und wiederherstellen, indem Sie mit der legacy-API. |
| [Gewusst wie: Implementieren von Suchen und Ersetzen Sie Mechanismus](../extensibility/how-to-implement-the-find-and-replace-mechanism.md) | Erläutert, wie zum Verwalten von Suchen und ersetzen, indem Sie die legacy-API. |
| [Gewusst wie: Unterdrücken von dateiänderungsbenachrichtigungen](../extensibility/how-to-suppress-file-change-notifications.md) | Erläutert das dateiänderungsbenachrichtigungen zu unterdrücken, indem Sie mit der legacy-API. |
| [Erstellen von benutzerdefinierten Editoren und Designern](../extensibility/creating-custom-editors-and-designers.md) | Erläutert das Erstellen von benutzerdefinierten Editoren und Designern. |
| [Entwickeln eines Datendiensts legacysprache](../extensibility/internals/developing-a-legacy-language-service.md) | Enthält Links zu Dokumenten über Features, die der Anpassungsfunktionen zum Bereitstellen der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] durch Hinzufügen von Unterstützung für einen Sprachdienst-Kern-Editor. |
| [Verwenden von Schriftarten und Farben](../extensibility/using-fonts-and-colors.md) | Erläutert, wie Schriftarten und Farben mit legacy-Schnittstellen. |


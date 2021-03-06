---
title: AutoWiederherstellen, Umgebung, Dialogfeld "Optionen"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 804ea0baa47925e35a282a615598ea66c843b911
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2018
ms.locfileid: "52388801"
---
# <a name="autorecover-environment-options-dialog-box"></a>AutoWiederherstellen, Umgebung, Dialogfeld „Optionen“

Verwenden Sie diese Seite im Dialogfeld **Optionen**, um anzugeben, ob Dateien automatisch gesichert werden sollen oder nicht. Sie können außerdem angeben, ob geänderte Dateien wiederhergestellt werden sollen, wenn Visual Studio unerwartet beendet wird.

Sie greifen auf dieses Dialogfeld zu, indem Sie im Menü **Extras** auf **Optionen** klicken und dann **Umgebung** > **AutoWiederherstellen** auswählen. Wenn diese Seite nicht in der Liste angezeigt wird, aktivieren Sie im Dialogfeld **Optionen** das Kontrollkästchen **Alle Einstellungen anzeigen**.

**AutoWiederherstellen-Informationen speichern alle [n] Minuten**

Verwenden Sie diese Option, um anzupassen, wie oft eine Datei automatisch im Editor gespeichert wird. Bei zuvor gespeicherten Dateien wird eine Kopie der Datei in *%USERPROFILE%\Documents\Visual Studio\\[Version]>\Backup Files\\[Projektname]* gespeichert. Wenn es sich um eine neue Datei handelt und diese noch nicht gespeichert wurde, wird sie mit einem zufällig generierten Dateinamen automatisch gespeichert.

**Informationen für AutoWiederherstellen beibehalten für [n] Tage**

Verwenden Sie diese Option, um anzugeben, wie lange Visual Studio Dateien für die automatische Wiederherstellung beibehält.

### <a name="see-also"></a>Siehe auch

- [Dialogfeld „Optionen“](../../ide/reference/options-dialog-box-visual-studio.md)
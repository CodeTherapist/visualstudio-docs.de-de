---
title: Paket-Manager für R
description: Verwenden des R-Paket-Managers in Visual Studio zum Installieren und Verwalten von R-Paketen.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 4063787711ae825cd587f72d735710444906d99b
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "35666513"
---
# <a name="package-manager"></a>Paket-Manager

Der Paket-Manager von R Tools für Visual Studio (RTVS) ist eine Benutzeroberfläche für die Verwaltung der R-Pakete. Wählen Sie zum Öffnen **R Tools** > **Windows** > **Pakete** aus, oder drücken Sie **STRG**+**7**.

Der Paket-Manager enthält drei Registerkarten. Jede Registerkarte zeigt auf der linken Seite eine Liste von relevanten Paketen und auf der rechten Seite spezifische Details zu dem ausgewählten Paket an, einschließlich Paketversion, -beschreibung, -lizenz und -speicherort sowie Links zu anderen relevanten Informationen. Mit dem Suchfeld oben rechts lässt sich die Liste filtern.

> [!Tip]
> Der Begriff im Suchfeld bleibt beim Wechseln zwischen den Registerkarten aktiv.

- Auf der Registerkarte **Verfügbar** können Sie die zu installierenden Pakete durchsuchen. Wenn das Paket bereits installiert wurde, ändert sich die Schaltfläche **Installieren** rechts in **Deinstallieren**.

    ![Registerkarte mit den verfügbaren Paketen im Paket-Manager von R Tools für Visual Studio](media/package-manager-available.png)

- Auf der Registerkarte **Installiert** werden alle installierten und geladenen Pakete angezeigt. Ein grüner Punkt neben einem Paket gibt an, dass es in die R-Sitzung geladen wurde. Das rote X-Symbol in der linken Liste oder die Schaltfläche **Deinstallieren** rechts kann zum Deinstallieren des Pakets verwendet werden. Sollte eine neuere Version eines installierten Pakets verfügbar sein, aktualisiert ein blauer Pfeil nach oben rechts neben einem installierten Paket das Paket.

    ![Registerkarte mit den installierten Paketen im Paket-Manager von R Tools für Visual Studio](media/package-manager-installed.png)

- Die Registerkarte **Geladen** zeigt nur die Pakete, die in die R-Sitzung geladen wurden, die alle mit einem grünen Punkt angezeigt werden. Sie haben hier auch die Möglichkeit, Pakete zu deinstallieren und zu aktualisieren.

    ![Registerkarte mit den geladenen Paketen im Paket-Manager von R Tools für Visual Studio](media/package-manager-loaded.png)

## <a name="package-locations"></a>Paketspeicherorte

Paketen werden an den folgenden Speicherorten installiert:

- Core-Pakete, die in RTVS enthalten sind, werden unter *C:\Programme\Microsoft\R Client\R_SERVER\Bibliothek* installiert.
- Zusätzliche Pakete werden unter *%userprofile%\Dokumente\R\win-library\3.3* installiert.

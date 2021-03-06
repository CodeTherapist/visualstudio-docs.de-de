---
title: Sammeln von Anwendungsstatistiken für ASP.NET-Webanwendungen über die Befehlszeile mit der Profiler-Samplingmethode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling tools, sampling method
- sampling profling method
ms.assetid: f8383ab1-eb49-4d3f-8608-d8b4d51a81be
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c20e40ef740aba85fa4a778160adc940ad20b9ea
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51787600"
---
# <a name="collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line"></a>Sammeln von Anwendungsstatistiken für eine ASP.NET-Webanwendungen über die Befehlszeile mit der Profiler-Samplingmethode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

In diesem Abschnitt werden die Prozeduren und Optionen zum Sammeln von Leistungsstatistiken für eine ASP.NET-Webanwendung mithilfe der Befehlszeilentools **VSPerfASPNETCmd** und **VSPerfCmd** sowie mithilfe der Samplingmethode zur Profilerstellung beschrieben.  
  
> [!NOTE]
>  Verbesserte Sicherheitsfunktionen in Windows 8 und Windows Server 2012 erforderten tiefgreifende Änderungen bei der Datenerfassung des Visual Studio-Profilers auf diesen Plattformen. Außerdem benötigen Windows Store-Apps neue Erfassungsmethoden. Siehe [Profilerstellungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Mit dem Tool **VSPerfCmd** stehen Ihnen zwar sämtliche Funktionen der Profilerstellungstools zur Verfügung (beispielsweise Anhalten und Fortsetzen der Profilerstellung oder Sammeln zusätzlicher Daten aus Prozessor- und Windows-Leistungsindikatoren), es wird jedoch empfohlen, das Befehlszeilentool **VSPerfASPNETCmd** zu verwenden, wenn Sie diese Funktionen nicht benötigen. Das Befehlszeilentool **VSPerfASPNETCmd** ist die bevorzugte Methode für die Profilerstellung für ASP.NET-Websites mithilfe des eigenständigen Profilers. Anders als beim Befehlszeilentool [VSPerfCmd](../profiling/vsperfcmd.md) müssen keine Umgebungsvariablen festgelegt werden, und der Computer muss nicht neu gestartet werden. Weitere Informationen finden Sie unter [Schnelle Website-Profilerstellung mit VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Allgemeine Aufgaben  
  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Anfügen des Profilers an eine ASP.NET-Anwendung**|-   [Vorgehensweise: Anfügen des Profilers an eine ASP.NET-Webanwendung zum Sammeln von Anwendungsstatistiken über die Befehlszeile](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Verwandte Aufgaben  
  
### <a name="profiling-aspnet-web-applications"></a>Profilerstellung für ASP.NET-Webanwendungen  
  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Profilerstellung mit der Instrumentationsmethode**|-   [Sammeln ausführlicher Zeitsteuerungsdaten für eine ASP.NET-Webanwendung über die Befehlszeile mit der Profiler-Instrumentationsmethode](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**Profilerstellung der Speicherbelegung und Garbage Collection**|-   [Sammeln von Speicherdaten aus einer ASP.NET-Webanwendung über die Profiler-Befehlszeile](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**Profilerstellung für Ressourcenkonflikte und Threadaktivität**|-   [Sammeln von Parallelitätsdaten](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="sampling-method"></a>Samplingmethode  
  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Profilerstellung für eigenständige (Client-)Anwendungen**|-   [Sammeln von Anwendungsstatistiken für eigenständige Anwendungen über die Profiler-Befehlszeile](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|-   **Profilerstellung für Dienste**|-   [Sammeln von Anwendungsstatistiken für Dienste mithilfe der Profiler-Samplingmethode](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Analysieren von Ansichten und Berichten für Samplingdaten  
 [Datenansichten der Profiler-Samplingmethode](../profiling/profiler-sampling-method-data-views.md)




---
title: "使用分析工具命令列收集獨立應用程式的應用程式統計資料 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method
- profilng tools,sampling method
ms.assetid: be2dbdd0-fc88-45f9-a1d5-bcb4f64e17ad
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ce2cc34174131d1a8799d66381da0595d7ac4507
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line"></a>使用分析工具命令列以收集獨立應用程式的應用程式統計資料
本節說明從命令列使用取樣方法收集用戶端 (獨立) 應用程式之效能統計資料的程序和選項。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 增強式安全性功能需要的重大變更，會以 Visual Studio 分析工具在這些平台收集資料的方式表現。 UWP App 也需要新的收集技術。 請參閱 [Windows 8 和 Windows Server 2012 應用程式的效能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
## <a name="common-tasks"></a>一般工作  
  
|工作|相關內容|  
|----------|---------------------|  
|**使用分析啟動應用程式**|-   [如何：啟動獨立應用程式並收集應用程式統計資料](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**將分析工具附加至執行中的 .NET Framework 應用程式**|-   [如何：將分析工具附加至 .NET Framework 應用程式並收集應用程式統計資料](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)|  
|**將分析工具附加至執行中的 C/C++ 應用程式**|-   [如何：將分析工具附加至原生應用程式並收集應用程式統計資料](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)|  
|**新增階層互動資料**|-   [收集階層互動資料](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>相關工作  
  
### <a name="profiling-stand-alone-applications"></a>對獨立應用程式進行程式碼剖析  
  
|工作|相關內容|  
|----------|---------------------|  
|**檢測應用程式**|-   [使用檢測收集詳細計時資料](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**收集 .NET 記憶體配置和記憶體回收資料**|-   [收集 .NET Framework 記憶體資料](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**收集資源爭用和執行緒執行資料**|-   [收集並行資料](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-by-using-the-sampling-method"></a>使用取樣方法進行分析  
  
|工作|相關內容|  
|----------|---------------------|  
|**分析 ASP.NET Web 應用程式**|-   [使用取樣收集應用程式統計資料](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**分析服務**|-   [使用取樣收集應用程式統計資料](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)。 說明如何使用取樣方法收集 Windows 服務的效能統計資料。|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>分析取樣資料檢視和報表  
 [取樣方法資料檢視](../profiling/profiler-sampling-method-data-views.md)
---
title: "收集階層互動資料 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3c586b027bec7e480b3dc3b2b378b0ce9600a7d4
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2018
---
# <a name="collecting-tier-interaction-data"></a>收集階層互動資料

階層互動分析提供透過 ADO.NET 服務與資料庫通訊之多介層應用程式函式執行時間的其他資訊。 只針對同步函式呼叫收集資料。

**Visual Studio 版本**

階層互動分析資料可以使用任何版本的 Visual Studio 來收集。 不過，階層互動分析資料只能在 Visual Studio Enterprise 中檢視。

**Windows 8 和 Windows Server 2012**

若要在 Windows 8 傳統型應用程式和 Windows Server 2012 應用程式上收集階層互動資料，您必須使用檢測方法。 您無法收集 UWP App 的階層互動資料。 請參閱 [Windows 8 和 Windows Server 2012 應用程式的效能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。 其他支援的 Windows 版本上的所有程式碼剖析方法都可以包含階層互動資料。

**效能精靈**

因為效能精靈中有錯誤 (bug)，所以您必須從 [效能總管] 將階層互動資料收集選項加入分析執行。 您也必須將專案、可執行檔或網站加入 [效能總管] 的 [目標] 節點。

## <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>使用效能工作階段屬性頁將階層互動資料加入分析執行

1. 在 [效能總管] 中，從操作功能表選擇 [屬性]。

2. 選取 [階層互動] 頁面，然後按一下 [啟用階層互動分析] 核取方塊。

3. 在 [效能總管] 中，選取 [目標] 節點，然後指定您想要分析的專案、可執行檔或網站。

## <a name="see-also"></a>另請參閱

[階層互動檢視](../profiling/tier-interactions-view.md)
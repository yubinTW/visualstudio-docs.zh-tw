---
title: "歷程偵錯 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0107109cfa5b15b8db0c84b304e8e1daae5dfbfa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="historical-debugging"></a>歷程偵錯
歷程偵錯是取決於 IntelliTrace 所收集資訊的偵錯模式。 它可讓您向後和向前逐步執行您的應用程式，並檢查其狀態。  
  
 您可以在 Visual Studio Enterprise 版本 (而非 Professional 或 Community 版本) 中使用 IntelliTrace。  
  
## <a name="why-use-historical-debugging"></a>為何使用歷程偵錯？  
 設定中斷點來找出 Bug 可能相當容易出錯。 您可以在接近程式碼中懷疑為 Bug 所在的位置設定中斷點，然後在偵錯工具中執行應用程式，並希望您的中斷點找到錯誤位置，以及執行中斷可能會顯示 Bug 來源的位置。 如果沒有，您必須嘗試設定中斷點在程式碼中其他位置，然後重新執行偵錯工具，重複執行測試步驟，直到您找出問題。  
  
 ![設定中斷點](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 您可以使用 IntelliTrace 和歷程偵錯來漫遊您的應用程式，並檢查其狀態 （呼叫堆疊和區域變數） 而不需要設定中斷點、 重新啟動偵錯，並重複測試步驟。 這可以節省許多時間，特別是當 Bug 位於測試案例的較深處而需要花很長的時間執行時。  
  
## <a name="how-do-i-start-using-historical-debugging"></a>如何開始使用歷程偵錯？  
 預設會開啟 IntelliTrace。 您只需要是決定哪些事件和函式呼叫感興趣的您，以及您是否想要檢視完整的應用程式狀態的快照集。 如需定義您想要尋找的詳細資訊，請參閱[IntelliTrace 功能](../debugger/intellitrace-features.md)。  

 - 若要檢視的快照集使用歷程偵錯，請參閱[檢視使用 IntelliTrace 步驟後的快照集](../debugger/how-to-use-intellitrace-step-back.md)
 - 若要了解如何檢查變數，以及巡覽程式碼，請參閱[檢查您的應用程式使用歷程偵錯](../debugger/historical-debugging-inspect-app.md)
 - 若要深入了解 IntelliTrace 事件進行偵錯，請參閱[逐步解說： 使用 IntelliTrace](../debugger/walkthrough-using-intellitrace.md)。
---
title: "GPU 活動 (分頁) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 01c61fb193ebc29c6eb76615e339327e71c24002
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="gpu-activity-paging"></a>GPU 活動 (分頁)
[執行緒] 索引標籤上的 [GPU 活動 (分頁)] 區段表示 GPU 處理分頁要求的時間。  區段的長度表示 GPU 處理直接記憶體存取 (DMA) 分頁封包的持續時間。 一般來說，分頁封包與 CPU 和 GPU 之間的記憶體傳輸相關聯。  
  
 當您選取 GPU 分頁區段時，[目前] 索引標籤上的報告會顯示已處理的 DMA 封包的相關資訊。 這包括封包在與 DirectX 引擎相關聯的硬體佇列中等候的時間量、送出 DMA 封包的處理序和處理封包所需的時間。  
  
## <a name="see-also"></a>請參閱  
 [使用率檢視](../profiling/utilization-view.md)
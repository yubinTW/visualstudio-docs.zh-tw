---
title: "關機 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f2e5411a4d5b88340105f71248ca2e5c2410ff12
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="shutdown"></a>關機
[關機] 選項等候任何目前已分析的處理序結束或中斷連接，然後關閉分析工具，結束分析資料檔案。 [關機] 選項必須是分析執行的最後一道命令。  
  
 如未指定逾時參數，[關機] 選項會無限期等候。 如已指定逾時參數，則此選項會在指定的秒數後傳回，不關閉分析工具或結束資料檔。  
  
 [關機] 選項必須是命令列上指定的唯一選項。  
  
## <a name="syntax"></a>語法  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>參數  
 `Timeout`  
 -   (選擇性) 如已指定，則此選項會在指定的秒數後傳回，不關閉分析工具或結束分析資料檔。  
  
## <a name="see-also"></a>請參閱  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [對獨立應用程式進行程式碼剖析](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [對 ASP.NET Web 應用程式進行程式碼剖析](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [對服務進行程式碼剖析](../profiling/command-line-profiling-of-services.md)
---
title: "複製 （程式設計擷取） |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7f8fce1893363ac6df0e6d22320f718833a1114e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="copy-programmatic-capture"></a>複製 (程式設計擷取)
將使用中的圖形記錄 (.vsglog) 檔案的內容複製到新的檔案。  
  
## <a name="syntax"></a>語法  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>參數  
 `szNewVSGLog`  
 新的圖形記錄檔檔案名稱。  
  
## <a name="remarks"></a>備註  
 若要複製到新的檔案的圖形資訊，您必須已經擷取某些圖形資訊;否則，會發生任何事。
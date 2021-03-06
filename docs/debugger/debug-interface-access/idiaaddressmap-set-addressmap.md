---
title: "Idiaaddressmap:: Set_addressmap |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 681e0bae46497d9b581e89340069937370831777
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
提供對應至支援映像配置翻譯的位址。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>參數  
 `cbData`  
 [in]中的項目數`data`參數。  
  
 `data[]`  
 [in]陣列[DiaAddressMapEntry 結構](../../debugger/debug-interface-access/diaaddressmapentry.md)結構會定義轉譯對應。  
  
 `imagetoSymbols`  
 [in]`TRUE`如果`data`參數定義的原始配置新的映像配置對應 （如所述的偵錯符號）。 `FALSE`如果`data`是對應至新的映像配置取自原始的版面配置。  
  
## <a name="return-value"></a>傳回值  
 如果成功，傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 通常，DIA 位址轉譯會從抓取對應程式資料庫 (.pdb) 檔。 如果這些值遺漏， [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)方法呼叫兩次，一次使用`imagetoSymbols`參數設定為`TRUE`和一次使用`imagetoSymbols`參數設定為`FALSE`。 無法使用啟用位址對應翻譯[idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)方法除非兩個轉譯對應所提供。  
  
## <a name="see-also"></a>請參閱  
 [DiaAddressMapEntry 結構](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)
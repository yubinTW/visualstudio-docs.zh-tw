---
title: "Idiasymbol:: Get_thunkordinal |Microsoft 文件"
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
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2ef3c35c1732c4177edfa6d3bc41faacc1371aa5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
擷取函式的 thunk 類型。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT get_thunkOrdinal (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pRetVal`  
 [out]傳回值，從[THUNK_ORDINAL 列舉](../../debugger/debug-interface-access/thunk-ordinal.md)指定 thunk 函式類型的列舉。  
  
## <a name="return-value"></a>傳回值  
 如果成功，傳回`S_OK`; 否則傳回`S_FALSE`或錯誤碼。  
  
> [!NOTE]
>  傳回值為`S_FALSE`表示屬性不適用於符號。  
  
## <a name="remarks"></a>備註  
 這個屬性才有效。 只有當符號當做[SymTagEnum 列舉](../../debugger/debug-interface-access/symtagenum.md)值`SymTagThunk`。  
  
 「 Thunk 」 是一種轉換的 32 位元記憶體位址空間 （也稱為一般的位址空間） 和 （又稱為分段的位址空間） 的 16 位元位址空間的程式碼。  
  
## <a name="see-also"></a>請參閱  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [THUNK_ORDINAL 列舉](../../debugger/debug-interface-access/thunk-ordinal.md)   
 [SymTagEnum 列舉](../../debugger/debug-interface-access/symtagenum.md)
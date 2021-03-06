---
title: "BP_PASSCOUNT_STYLE |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_PASSCOUNT_STYLE
helpviewer_keywords: BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e272c92bbcc7364c967fc37c1e57b915e6cb64ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
指定會引發中斷點的中斷點傳遞計數相關聯的條件。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>成員  
 BP_PASSCOUNT_NONE  
 不指定任何中斷點傳遞計數樣式。  
  
 BP_PASSCOUNT_EQUAL  
 設定為等於中斷點傳遞計數的樣式。 中斷點叫用次數等於傳遞計數時，就會引發中斷點。  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 將中斷點傳遞計數樣式設定為等於或大於。 中斷點叫用次數等於或大於傳遞計數時，就會引發中斷點。  
  
 BP_PASSCOUNT_MOD  
 指定模數通過計數。 例如，如果類型是傳遞計數`BP_PASSCOUNT_MOD`和傳遞計數值為 4，每次叫用的次數是 4 的倍數中斷點引發。  
  
## <a name="remarks"></a>備註  
 用於`stylePassCount`隸屬[BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)結構，這又是隸屬[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)和[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)結構。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 組件： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
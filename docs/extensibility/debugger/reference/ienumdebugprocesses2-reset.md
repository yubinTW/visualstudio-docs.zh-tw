---
title: "IEnumDebugProcesses2::Reset |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugProcesses2::Reset
helpviewer_keywords: IEnumDebugProcesses2::Reset
ms.assetid: 31cbde4f-0bba-497a-9969-d2c342ef4a7b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f9d960e07076fd10ea10f1eb9462736219103db9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprocesses2reset"></a>IEnumDebugProcesses2::Reset
將列舉重設第一個項目。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>傳回值  
 如果成功，傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 呼叫這個方法是下, 一次呼叫之後[下一步](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)方法會傳回第一個元素的列舉型別。  
  
## <a name="see-also"></a>請參閱  
 [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)
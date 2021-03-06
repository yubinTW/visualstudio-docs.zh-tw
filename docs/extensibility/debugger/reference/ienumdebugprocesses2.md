---
title: "IEnumDebugProcesses2 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugProcesses2
helpviewer_keywords: IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 559d95834ccb8c7d0081a95a8412dccf12b1d8fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
這個介面會列舉在偵錯連接埠上執行的處理程序。  
  
## <a name="syntax"></a>語法  
  
```  
IEnumDebugProcesses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者注意事項  
 自訂連接埠供應商實作這個介面來提供連接埠上執行的處理序的清單。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 Visual Studio 呼叫[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)取得此介面。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IEnumDebugProcesses2`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一步](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|擷取指定的數目的列舉順序中的程序。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|略過指定的數目的列舉順序中的程序。|  
|[重設](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|列舉序列重設為開頭。|  
|[複製](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|建立列舉值，包含目前的列舉值的列舉型別狀態相同。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|取得列舉值中的處理序數目。|  
  
## <a name="remarks"></a>備註  
 Visual Studio 會使用此介面來填入**處理程序**視窗。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 組件： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)
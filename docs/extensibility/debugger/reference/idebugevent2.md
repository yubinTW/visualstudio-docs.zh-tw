---
title: "IDebugEvent2 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0d783cb13ee227e317afe9b49abedb6f53e9fa76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="idebugevent2"></a>IDebugEvent2
這個介面用來傳達重要的偵錯資訊，例如停止於中斷點和非關鍵資訊，例如偵錯訊息。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者注意事項  
 偵錯引擎 (DE) 和自訂連接埠供應商實作這個介面上相同的物件，為所有其他事件介面。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 使用介面識別碼 (IID) 引數提供給[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)或[事件](../../../extensibility/debugger/reference/idebugportevents2-event.md)，工作階段的偵錯管理員 (SDM) 呼叫[QueryInterface](/cpp/atl/queryinterface)上`IDebugEvent2`介面，以取得適當的事件介面。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IDebugEvent2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|這個偵錯事件中取得的屬性。|  
  
## <a name="remarks"></a>備註  
 更具體的事件，這類介面[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)，不是衍生自 IDebugEvent2 介面，但會改為實作為個別的介面上相同的物件做為`IDebugEvent2`。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 組件： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [事件](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
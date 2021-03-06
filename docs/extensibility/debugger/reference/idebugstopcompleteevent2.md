---
title: "IDebugStopCompleteEvent2 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa8941decfb4e64906c57b719df711ce8779df9c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2018
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

偵錯引擎 (DE) 可以傳送這個選擇性事件工作階段的偵錯管理員 (SDM) 當程式已停止。

## <a name="syntax"></a>語法

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>實作者注意事項

使用 Visual Studio 2005 中引進這個介面。 先前的版本不支援非同步停止。

[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)SDM 中多處理序或多個程式的情況下呼叫。 當一種程式會將停止事件傳送至 SDM 時，SDM 要求太停止其他程式。

停止用來以非同步方式通知程式已停止 SDM。 通知 SDM 適合用來解譯器偵錯引擎，有時也沒有程式碼執行內偵錯程式，因此[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)不同步完成。 如果偵錯引擎要採用此非同步通知時，它必須傳回`S_ASYNC_STOP`從[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)。

## <a name="requirements"></a>需求

標頭： msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll
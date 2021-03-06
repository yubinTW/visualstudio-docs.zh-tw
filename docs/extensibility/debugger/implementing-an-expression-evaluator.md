---
title: "實作運算式評估工具 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f18e2e131b6baa325bd7e0b65babee4c3679ed8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-an-expression-evaluator"></a>實作運算式評估工具
> [!IMPORTANT]
>  在 Visual Studio 2015 中，這種實作運算式評估工具已被取代。 如需實作 CLR 運算式評估工具的資訊，請參閱[CLR 運算式評估工具](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)和[Managed 運算式評估工具範例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 評估運算式是在偵錯引擎 (DE)、 符號提供者 (SP)、 繫結器物件，以及運算式評估工具 (EE) 本身之間的複雜相互作用。 四個元件會透過介面是由一個元件實作並取用由另一個連接。  
  
 EE 採用運算式從字串的形式 DE 與剖析或評估它。 EE 實作下列介面，以供 DE:  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE 呼叫繫結器物件，提供 DE，若要取得的符號和物件的值。 EE 取用 DE 透過下列介面：  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 實作 EE [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)。 `IDebugProperty2`提供描述結果的運算式評估，例如本機變數、 基本型別或物件，Visual studio，然後顯示中的相關資訊的機制**區域變數**， **監看式**，或**即時運算**視窗。  
  
 預存程序是指定給 EE DE 時，它會要求的資訊。 預存程序會實作說明位址和欄位，例如下列介面和其衍生的介面：  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE 會消耗所有的這些介面。  
  
## <a name="in-this-section"></a>本節內容  
 [運算式評估工具的實作策略](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 定義運算式評估工具 (EE) 實作策略的三個步驟程序。  
  
## <a name="see-also"></a>請參閱  
 [撰寫 CLR 運算式評估工具](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)
---
title: "如何： 原生框架遺失於呼叫堆疊顯示時跳離 Managed 程式碼 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7599c99c9375cda7b5f24432db8c137c5c4357df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>如何：在原生框架遺失於呼叫堆疊顯示時跳離 Managed 程式碼
如果程式碼擁有在中不可見的原生框架**呼叫堆疊**視窗中，跳離 managed 程式碼可能會產生非預期的結果。 因應措施，您可以使用中斷點，而不要**跳離函式**。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](../ide/personalizing-the-visual-studio-ide.md)。  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>若要在原生框架遺失於呼叫堆疊顯示時跳離 Managed 程式碼  
  
1.  在機器碼中，請在呼叫 Managed 程式碼之後設定一個位置中斷點。  
  
2.  在**偵錯**功能表上，選擇**繼續**。  
  
     完成 Managed 呼叫之後，執行將停止於機器碼的中斷點處。  
  
## <a name="see-also"></a>請參閱  
 [如何：使用呼叫堆疊視窗](../debugger/how-to-use-the-call-stack-window.md)
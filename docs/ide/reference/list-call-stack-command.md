---
title: "列出呼叫堆疊命令 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.listcallstack
helpviewer_keywords:
- list call stack command
- Debug.ListCallStack command
ms.assetid: a8b20bf2-81d2-4069-aea8-23e6b15b4347
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 71095bd7ec4b856c5fbee73e13be27dcd9abdaf4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="list-call-stack-command"></a>列出呼叫堆疊命令
顯示目前的呼叫堆疊。  
  
## <a name="syntax"></a>語法  
  
```  
Debug.ListCallStack [/Count:number] [/ShowTypes:yes|no]  
[/ShowNames:yes|no] [/ShowValues:yes|no] [/ShowModule:yes|no]  
[/ShowLineOffset:yes|no] [/ShowByteOffset:yes|no]  
[/ShowLanguage:yes|no] [/IncludeCallsAcrossThreads:yes|no]  
[/ShowExternalCode:yes|no] [Thread:n] [index]  
```  
  
## <a name="arguments"></a>引數  
 `index`  
 選擇性。 設定目前堆疊框架且不顯示任何輸出。  
  
## <a name="switches"></a>參數  
 每個參數都可以使用其完整格式或簡短形式叫用。  
  
 /Count:`number` [or] /C:`number`  
 選擇項。 要顯示的呼叫堆疊最大數目。 預設值無限制。  
  
 /ShowTypes:`yes`&#124;`no` [or] /T:`yes`&#124;`no`  
 選擇性。 指定是否顯示參數類型。 預設值為 `yes`。  
  
 /ShowNames:`yes`&#124;`no` [or] /N:`yes`&#124;`no`  
 選擇性。 指定是否顯示參數名稱。 預設值為 `yes`。  
  
 /ShowValues:`yes`&#124;`no` [or] /V:`yes`&#124;`no`  
 選擇性。 指定是否顯示參數值。 預設值為 `yes`。  
  
 /ShowModule:`yes`&#124;`no` [or] /M:`yes`&#124;`no`  
 選擇性。 指定是否顯示模組名稱。 預設值為 `yes`。  
  
 /ShowLineOffset:`yes`&#124;`no` [or] /#:`yes`&#124;`no`  
 選擇性。 指定是否顯示行位移。 預設值為 `no`。  
  
 /ShowByteOffset:`yes`&#124;`no` [or] /B:`yes`&#124;`no`  
 選擇性。 指定是否顯示位元組位移。 預設值為 `no`。  
  
 /ShowLanguage:`yes`&#124;`no` [or] /L:`yes`&#124;`no`  
 選擇性。 指定是否顯示語言。 預設值為 `no`。  
  
 /IncludeCallsAcrossThreads:`yes`&#124;`no` [or] /I:`yes`&#124;`no`  
 選擇性。 指定是否包含對或來自其他執行緒的呼叫。 預設值為 `no`。  
  
 /ShowExternalCode:`yes`&#124;`no`  
 選擇性。 指定是否顯示呼叫堆疊的 Just My Code。 當 Just My Code 關閉時，會顯示所有的非使用者程式碼。 當 Just My Code 開啟時，非使用者程式碼在呼叫堆疊輸出中會顯示為 `[external]`。  
  
 Thread:`n`  
 選擇項。 顯示執行緒 `n` 的呼叫堆疊。 如果不指定任何執行緒，則顯示目前執行緒的呼叫堆疊。  
  
## <a name="remarks"></a>備註  
 對引數或參數所做的變更適用於未來叫用此命令。 如果您發出 Debug.ListCallStackby 本身，則會顯示整個呼叫堆疊。 如果您指定索引，例如，  
  
```  
Debug.ListCallStack 2  
```  
  
 則目前的堆疊框架會設定為該框架 (本例中為第二個框架)。  
  
 您也可以使用其預先定義的別名 kb，撰寫此命令。 例如，您可以輸入  
  
```  
kb 2  
```  
  
 將目前的堆疊框架設定為第二個框架。  
  
## <a name="example"></a>範例  
  
```  
>Debug.CallStack /Count:4 /ShowTypes:yes  
```  
  
## <a name="see-also"></a>請參閱  
 [列出反組譯碼命令](../../ide/reference/list-disassembly-command.md)   
 [列出執行緒命令](../../ide/reference/list-threads-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [命令視窗](../../ide/reference/command-window.md)   
 [尋找/命令方塊](../../ide/find-command-box.md)   
 [Visual Studio 命令別名](../../ide/reference/visual-studio-command-aliases.md)
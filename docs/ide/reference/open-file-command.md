---
title: "開啟檔案命令 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 59b0c421fa5a62394a32a2b9ad9926df58a40cb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="open-file-command"></a>開啟檔案命令
開啟現有的檔案，並可讓您指定編輯器。  
  
## <a name="syntax"></a>語法  
  
```  
File.OpenFile filename [/e:editorname]  
```  
  
## <a name="arguments"></a>引數  
 `filename`  
 必要。 要開啟之檔案的完整或部分路徑和檔名。 包含空格的路徑必須包含在引號中。  
  
## <a name="switches"></a>參數  
 /e:`editorname`  
 選擇項。 將用來開啟檔案之編輯器的名稱。 如果指定此引數，但未提供編輯器名稱，則會出現 [開啟方式] 對話方塊。  
  
 /e:`editorname` 引數語法會使用出現在 [開啟方式] 對話方塊並使用引號括住的編輯器名稱。  
  
 例如，若要使用原始程式碼編輯器開啟檔案，您將針對 /e:`editorname` 引數輸入下列項目。  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>備註  
 在您輸入路徑時，自動完成會嘗試找出正確的路徑和檔名。  
  
## <a name="example"></a>範例  
 本範例會在原始程式碼編輯器中開啟樣式檔案 "Test1.css"。  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>請參閱  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [命令視窗](../../ide/reference/command-window.md)   
 [即時運算視窗](../../ide/reference/immediate-window.md)   
 [尋找/命令方塊](../../ide/find-command-box.md)   
 [Visual Studio 命令別名](../../ide/reference/visual-studio-command-aliases.md)
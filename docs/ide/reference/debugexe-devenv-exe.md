---
title: -DebugExe (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8f50bfd0fa5b0f9303bc6256078a30da6e1c0575
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
開啟要偵錯的指定可執行檔。  
  
## <a name="syntax"></a>語法  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>引數  
 `ExecutableFile`  
 必要。 .exe 檔案的路徑和檔案名稱。  
  
 如果 .exe 檔案找不到或不存在，則不會顯示任何警告或錯誤，而且 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 會正常啟動。  
  
## <a name="remarks"></a>備註  
 `ExecutableFile` 參數後面的任何字串都會當成引數傳遞給該檔案。  
  
## <a name="example"></a>範例  
 下列範例會開啟 `MyApplication.exe` 檔案以進行偵錯。  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>請參閱  
 [Devenv 命令列參數](../../ide/reference/devenv-command-line-switches.md)
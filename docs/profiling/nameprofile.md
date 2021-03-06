---
title: NameProfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NameProfile
- NameProfileA
ms.assetid: 1bb05441-c4ff-4323-9fef-f3924fba4430
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: be7e6b2e29ed74fe57016bb286b54742b0add632
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="nameprofile"></a>NameProfile
`NameProfile` 函式會將字串指派給指定的處理序或執行緒。  
  
 NameProfile API 僅適用於檢測分析。 不支援 NameProfile API 進行取樣分析。  
  
## <a name="syntax"></a>語法  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI NameProfile(  
                                   LPCTSTR pszName,   
                                   PROFILE_CONTROL_LEVEL Level,  
                                   unsigned int dwId);  
```  
  
#### <a name="parameters"></a>參數  
 `pszName`  
  
 分析項目的名稱。 如果是下列情況，則名稱無效 (導致 NameProfileA 傳回 NAME_ERROR_INVALID_NAME)：  
  
-   傳遞至 NameProfileA 的指標是 NULL 值  
  
-   pszName 的字串資料開頭是數字  
  
-   pszName 的字串資料包含空格  
  
-   pszName 的字串資料包含下列任何字元：,;.`~!@#$%^&*()=[]{}&#124;\\?/<>  
  
 `Level`  
  
 指出可套用效能資料收集的分析層級。 下列 **PROFILE_CONTROL_LEVEL** 值可以用來指出可套用效能資料收集的三種層級的其中一種：  
  
|列舉值|描述|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|全域層級設定會影響分析執行中的所有處理序和執行緒。|  
|PROFILE_PROCESSLEVEL|處理序層級設定會影響屬於所指定處理序的所有執行緒。|  
|PROFILE_THREADLEVEL|執行緒分析層級設定會影響指定的執行緒。|  
  
 `dwId`  
  
 分析層級識別碼。 使用系統所產生的處理序或執行緒識別碼。  
  
## <a name="property-valuereturn-value"></a>屬性值/傳回值  
 此函式會使用 **PROFILE_COMMAND_STATUS** 列舉來指出成功或失敗。 傳回值可以是下列其中一個：  
  
|列舉值|描述|  
|----------------|-----------------|  
|NAME_ERROR_ID_NOEXIST|指定的分析項目不存在。|  
|NAME_ERROR_INVALID_NAME|名稱無效。|  
|NAME_ERROR_LEVEL_NOEXIST|指定的分析層級不存在。|  
|NAME_ERROR_NO_SUPPORT|不支援指定的作業。|  
|NAME_ERROR_OUTOFMEMORY|沒有記憶體可供記錄事件。|  
|NAME_ERROR_REDEFINITION|已指派分析項目的名稱。 會忽略此函式中的名稱。|  
|NAME_ERROR_TEXTTRUNCATED|名稱文字超過 32 個字元 (包含 Null 字元)，因此將予以截斷。|  
|NAME_OK|已成功註冊名稱。|  
  
## <a name="remarks"></a>備註  
 每個處理序或執行緒只能獲指派一個名稱。 命名分析項目之後，會忽略該項目的後續 NameProfile 呼叫。  
  
 如果將相同的名稱指定給不同的執行緒或處理序，則報表會包含具有該名稱之層級中來自所有項目的資料。  
  
 如果您指定目前處理序或執行緒以外的處理序或執行緒，則必須確定它已先初始化並開始執行，再將它命名。 否則，NameProfile 方法會失敗。  
  
> [!IMPORTANT]
>  可以先傳回 CreateProcess() 和 CreateThread() API 函式，再初始化執行緒或處理序。  
  
## <a name="net-framework-equivalent"></a>.NET Framework 同等  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>函式資訊  
  
|||  
|-|-|  
|**標頭**|包含 VSPerf.h|  
|**程式庫**|使用 VSPerf.lib|  
|**Unicode**|實作為 `NameProfileW` (Unicode) 和 `NameProfileA` (ANSI)。|  
  
## <a name="example"></a>範例  
 下列程式碼說明 NameProfile 函式呼叫。 此範例假設使用 Win32 字串巨集以及 ANSI 的編譯器設定，來判斷程式碼是否呼叫啟用 ANSI 功能的函式。  
  
```  
void ExerciseNameProfile()  
{  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Create and initialize variables to pass to   
    // ExerciseNameProfile.  The value of this   
    // parameter is based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variable is assigned an arbitrary value.  
    TCHAR * profileName = TEXT("ExerciseNameProfile");  
  
    // Declare enumeration to hold result of call to   
    // ExerciseNameProfle.  
    PROFILE_COMMAND_STATUS nameResult;  
  
    nameResult =  NameProfile(  
        profileName,  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("NameProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, nameResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>請參閱  
 [Visual Studio 分析工具 API 參考 (原生)](../profiling/visual-studio-profiler-api-reference-native.md)
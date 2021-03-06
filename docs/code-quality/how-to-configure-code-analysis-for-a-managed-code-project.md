---
title: "如何： 設定 Managed 程式碼專案的程式碼分析 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 575b81e9c213e4025cd38921ad467869686d867c
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>如何：設定 Managed 程式碼專案的程式碼分析

在 Visual Studio 中，您可以從清單中選擇程式碼分析*規則集*套用至 managed 程式碼專案。 預設規則集是 Microsoft 最小建議規則。 您可以套用另一個規則集對專案或方案中的所有專案。  
  
> [!NOTE]
> 如需如何設定 ASP.NET Web 應用程式設定的規則資訊，請參閱[How to： 設定 ASP.NET Web 應用程式的程式碼分析](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)。  
  
## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>若要設定的規則集的.NET Framework 專案  
  
1.  在**方案總管 中**，按一下 專案。  
  
2.  在**分析**功能表上，按一下 **設定的程式碼分析** *ProjectName*。  
  
3.  在**組態**和**平台**清單中，按一下 組建組態和目標平台。  
  
4.  若要每次使用選取的組態建置專案時執行程式碼分析，請選取**建置時啟用程式碼分析**核取方塊。 您也可以執行程式碼分析手動開啟**分析**功能表，選擇 * * 上執行程式碼分析 * ProjectName * * *。  
  
5.  根據預設，程式碼分析不會報告從外部工具自動產生的程式碼警告。 若要檢視產生的程式碼的警告，請清除**隱藏來自產生的程式碼的結果**核取方塊。  
  
    > [!NOTE]
    > 這個選項不會在表單和範本中出現錯誤和警告時，抑制來自產生的程式碼的程式碼分析錯誤和警告。 您可以檢視及維護表單或範本的原始程式碼，而不需要覆寫它。
  
6.  在**執行此規則集**清單中，執行下列其中一項：  
  
    -   按一下您想要使用的規則集。  
  
    -   按一下**\<瀏覽 >** ，指定現有的自訂規則集不在清單中。  
  
    -   定義自訂規則集。  
  
         如需詳細資訊，請參閱[建立自訂規則集](../code-quality/creating-custom-code-analysis-rule-sets.md)。  
  
## <a name="see-also"></a>另請參閱

[逐步解說：設定和使用自訂規則集](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)
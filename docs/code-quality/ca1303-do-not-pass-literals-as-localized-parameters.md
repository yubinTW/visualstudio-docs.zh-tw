---
title: "CA1303： 不要將傳遞常值為當地語系化的參數 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 361155e9d46e4f71ddc61775f56105cedb5d18b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303：不要將常值當做已當地語系化的參數傳遞
|||  
|-|-|  
|TypeName|DoNotPassLiteralsAsLocalizedParameters|  
|CheckId|CA1303|  
|分類|Microsoft.Globalization|  
|中斷變更|非中斷|  
  
## <a name="cause"></a>原因  
 方法將字串常值做為參數的建構函式或方法中的[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]類別庫與字串應該可以當地語系化。  
  
 當常值字串做為值傳遞至參數或屬性，並且在一或多個下列情況下，則為 true 時，會引發此警告：  
  
-   <xref:System.ComponentModel.LocalizableAttribute>參數或屬性的屬性設定為 true。  
  
-   參數或屬性名稱包含 「 文字 」、 「 訊息 」，或 「 標題 」。  
  
-   傳遞至 Console.Write 或 Console.WriteLine 方法將字串參數的名稱是"value"format"。  
  
## <a name="rule-description"></a>規則描述  
 內嵌在原始程式碼中的字串常值很難進行當地語系化。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 若要修正此規則的違規情形，取代為字串常值字串的執行個體透過擷取<xref:System.Resources.ResourceManager>類別。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 它可以安全地隱藏此規則的警告，或如果程式碼程式庫不會當地語系化，如果字串不會公開給終端使用者或開發人員使用程式碼程式庫。  
  
 使用者可以排除不應該傳遞當地語系化的字串重新命名的參數或屬性名稱，或標記這些項目，做為條件式方法的干擾。  
  
## <a name="example"></a>範例  
 下列範例示範當任一其兩個引數超出範圍時，會擲回例外狀況的方法。 第一個引數，例外狀況建構函式會違反此規則的常值字串。 第二個引數，建構函式會正確傳遞字串，透過擷取<xref:System.Resources.ResourceManager>。  
  
 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]  
  
## <a name="see-also"></a>請參閱  
 [桌面應用程式中的資源](/dotnet/framework/resources/index)
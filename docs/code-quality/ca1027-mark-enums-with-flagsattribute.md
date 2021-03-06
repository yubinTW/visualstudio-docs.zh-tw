---
title: "： Ca1027 以 flagsattribute 標記列舉 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9c80b90e1b1fe0ba89717a175666a68c3812665c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027：必須以 FlagsAttribute 標記列舉
|||  
|-|-|  
|TypeName|MarkEnumsWithFlags|  
|CheckId|CA1027|  
|分類|Microsoft.Design|  
|中斷變更|非中斷|  
  
## <a name="cause"></a>原因  
 公用列舉型別的值的 2 乘冪或組合列舉中所定義的其他值和<xref:System.FlagsAttribute?displayProperty=fullName>屬性不存在。 若要減少誤判，此規則不會報告的違規有連續值的列舉。  
  
## <a name="rule-description"></a>規則描述  
 列舉類型是一種實值類型 (Value Type)，用以定義一組相關的具名常數。 套用<xref:System.FlagsAttribute>列舉型別時的具名的常數可以有意義地加以結合。 例如，請考慮的一週中的應用程式，會追蹤哪一天的資源可供使用的列舉。 如果每個資源的可用性使用編碼列舉型別具有<xref:System.FlagsAttribute>可以表示存在的天數內的任何組合。 如果沒有屬性，可以表示只有一個的一週天數。  
  
 儲存 combinable 列舉的欄位，個別的列舉值會視為欄位中的位元的群組。 因此，這類欄位有時稱為*位元欄位*。 若要將列舉值的位元欄位中的儲存體，使用布林值的條件式運算子。 若要測試以判斷是否存在特定列舉值的位元欄位，使用布林邏輯運算子。 儲存和擷取組合的列舉值的正確位元欄位，定義列舉中的每個值必須是 2 的乘冪。 除非這是讓布林值的邏輯運算子將無法擷取儲存在欄位中的個別的列舉值。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 若要修正此規則的違規情形，加入<xref:System.FlagsAttribute>至列舉。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 若不想讓列舉值結合，則隱藏此規則的警告。  
  
## <a name="example"></a>範例  
 在下列範例中，`DaysEnumNeedsFlags`是符合的需求使用的列舉<xref:System.FlagsAttribute>，但不是需要它。 `ColorEnumShouldNotHaveFlag`列舉型別沒有值的 2 乘冪，但未正確指定<xref:System.FlagsAttribute>。 這樣會違反規則[CA2217： 不要不以 FlagsAttribute 標記列舉](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)。  
  
 [!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]  
  
## <a name="related-rules"></a>相關的規則  
 [CA2217：不要以 FlagsAttribute 標記列舉](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>請參閱  
 <xref:System.FlagsAttribute?displayProperty=fullName>
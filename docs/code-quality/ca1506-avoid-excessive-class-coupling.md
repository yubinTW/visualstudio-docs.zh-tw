---
title: "CA1506： 應避免使用結合過度的類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d5303e147ae001d887784aa401d456d23485c453
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506：應避免使用結合過度的類別
|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|分類|Microsoft.Maintainability|  
|中斷變更|中斷|  
  
## <a name="cause"></a>原因  
 類型或方法被搭配許多其他類型。  
  
## <a name="rule-description"></a>規則描述  
 這個規則會測量類別的耦合，方法是計算類型或方法包含的唯一類型參考數目。  
  
 型別和方法包含的類別結合程度高，可能難以維護。 最好有型別和表現低耦合和一致性的方法。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 若要修正這種違規，嘗試重新設計的類型或方法，以減少的類型，它會結合的數目。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 當類型或方法仍視為可維護性，儘管其大量的其他類型的相依性，請排除這個警告。  
  
## <a name="see-also"></a>請參閱  
 [維護性警告](../code-quality/maintainability-warnings.md)   
 [測量 Managed 程式碼的複雜度和維護性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
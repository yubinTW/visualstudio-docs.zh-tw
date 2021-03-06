---
title: "CA2142： 透明程式碼不應使用 linkdemand 加以保護 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5d0094d8afa2dcf59efe0aace8514979d73ac921
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142：透明程式碼不可以使用 LinkDemand 加以保護
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2142|  
|分類|Microsoft.Security|  
|中斷變更|中斷|  
  
## <a name="cause"></a>原因  
 透明方法需要<xref:System.Security.Permissions.SecurityAction>] 或 [其他安全性需求。  
  
## <a name="rule-description"></a>規則描述  
 需要 LinkDemand 才能存取的透明方法會引發這個規則。 安全性透明程式碼不應負責驗證作業的安全性，因此不應要求權限。 透明方法應該是中性的安全性，因為它們應該不會進行任何安全性決策。 此外，安全關鍵程式碼，並做出安全性決策，這應該不會依賴先前提出這類決策的透明程式碼。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 若要修正此規則的違規情形，請移除透明方法上的連結要求或標記的方法與<xref:System.Security.SecuritySafeCriticalAttribute>屬性如果它目前在執行安全性檢查，例如安全性要求。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 請勿隱藏此規則的警告。  
  
## <a name="example"></a>範例  
 在下列範例中，此規則就會引發方法上因為方法是透明的而且標示的 linkdemand<xref:System.Security.PermissionSet>包含<xref:System.Security.Permissions.SecurityAction>。  
  
 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]  
  
 請勿隱藏此規則的警告。
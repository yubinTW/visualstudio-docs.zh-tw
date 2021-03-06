---
title: "Ca2120： 必須保護序列化建構函式 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e28d76315b3ef5844bd9b525764e6f5a5111ef56
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120：必須保護序列化建構函式
|||  
|-|-|  
|TypeName|SecureSerializationConstructors|  
|CheckId|CA2120|  
|分類|Microsoft.Security|  
|中斷變更|中斷|  
  
## <a name="cause"></a>原因  
 型別實作<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>介面、 委派或介面，並不允許部分信任呼叫端的組件中宣告。 類型具有的建構函式<xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>物件和<xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>物件 （序列化建構函式的簽章）。 這個建構函式未受到安全性檢查，但一個或多個規則建構函式類型中受到保護。  
  
## <a name="rule-description"></a>規則描述  
 此規則是關於支援自訂序列化的類型。 型別支援自訂序列化，如果它實作<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>介面。 序列化建構函式需要，而用來還原序列化，或重新建立使用序列化的物件<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName>方法。 因為序列化建構函式配置，並初始化物件，也必須存在於上序列化建構函式都存在於規則建構函式的安全性檢查。 如果您違反此規則，否則不可以建立執行個體的呼叫端可以使用序列化建構函式若要這樣做。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 若要修正此規則的違規情形，保護序列化建構函式具有相同的保護其他建構函式的安全性要求。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 請勿隱藏此規則的違規。  
  
## <a name="example"></a>範例  
 下列範例顯示違反規則的類型。  
  
 [!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]  
  
## <a name="related-rules"></a>相關的規則  
 [CA2229：必須實作序列化建構函式](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2237：ISerializable 類型必須標記 SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>請參閱  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>
---
title: "LINQ to XML 動態屬性 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bf92d22b3c27d23fa90b6d9be13cf4fa6604384a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-xml-dynamic-properties"></a>LINQ to XML 動態屬性
本節提供 LINQ to XML 之動態屬性的參考資訊。 特別是，這些屬性會由 <xref:System.Xml.Linq.XAttribute> 命名空間中的 <xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq> 類別公開。  
  
 每個動態屬性都相當於相同類別中的標準公用屬性或方法，如[使用 LINQ to XML 進行 WPF 資料繫結的概觀](../designers/wpf-data-binding-with-linq-to-xml-overview.md)主題中所述。 大部分的用途應該都可以使用這些標準成員；動態屬性是針對 LINQ to XML 資料繫結案例特別提供。 如需有關這些類別之標準成員的詳細資訊，請參閱 <xref:System.Xml.Linq.XAttribute> 和 <xref:System.Xml.Linq.XElement> 參考主題。  
  
 關於其解析的值，本節中的動態屬性分為兩種分類：  
  
-   簡單分類，例如，`Value` 和 <xref:System.Xml.Linq.XAttribute> 類別中的 <xref:System.Xml.Linq.XElement> 屬性，可解析為單一的值。  
  
-   索引值 (例如 <xref:System.Xml.Linq.XElement> 的 [Elements](../designers/elements-xelement-dynamic-property.md) 和 [Descendants](../designers/descendants-xelement-dynamic-property.md) 屬性)，可解析為索引子類型。 對於要解析為所需數值或集合的索引子型別，必須將擴充名稱參數傳遞給它們。  
  
 傳回 <xref:System.Collections.Generic.IEnumerable%601> 型別之索引值的所有動態屬性都使用延緩執行。 如需延後執行的詳細資訊，請參閱 [LINQ 查詢簡介 (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)。  
  
## <a name="in-this-section"></a>本節內容  
  
|主題|描述|  
|-----------|-----------------|  
|[XAttribute 類別動態屬性](../designers/xattribute-class-dynamic-properties.md)|提供由 <xref:System.Xml.Linq.XAttribute> 類別公開之動態屬性的詳細資料。|  
|[XElement 類別動態屬性](../designers/xelement-class-dynamic-properties.md)|提供由 <xref:System.Xml.Linq.XElement> 類別公開之動態屬性的詳細資料。|  
  
## <a name="reference"></a>參考資料  
 <xref:System.Xml.Linq>  
  
 <xref:System.Xml.Linq.XElement?displayProperty=fullName>  
  
 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>  
  
## <a name="see-also"></a>請參閱  
 [使用 LINQ to XML 進行 WPF 資料繫結](../designers/wpf-data-binding-with-linq-to-xml.md)   
 [WPF 資料繫結與 LINQ to XML 概觀](../designers/wpf-data-binding-with-linq-to-xml-overview.md)   
 [LINQ 查詢簡介 (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
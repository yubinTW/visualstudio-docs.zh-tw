---
title: "如何： 以程式設計方式儲存和擷取日期值在 Excel 範圍中的 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], retrieving date values from ranges
- ranges, retrieving data values
- dates, retrieving from Excel ranges
- Excel [Office development in Visual Studio], storing date values in ranges
- date values, storing in Excel ranges
- dates, storing in Excel ranges
- ranges, storing date values
- date values
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 589079a593400549a69940fc42d1cf25fcab8826
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-store-and-retrieve-date-values-in-excel-ranges"></a>如何：以程式設計方式在 Excel 範圍中儲存和擷取日期值
  您可以儲存和擷取中的值<xref:Microsoft.Office.Tools.Excel.NamedRange>控制項或原生 Excel 範圍物件。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 如果您儲存日期值落在或之後的 1/1/1900 在範圍內使用 Visual Studio 中的 Office 程式開發工具時，它會儲存在 OLE Automation (OA) 格式。 您必須使用<xref:System.DateTime.FromOADate%2A>方法，以擷取 OLE Automation (OA) 日期的值。 如果日期為 1900 年 1 月 1 之前，會將它儲存為字串。  
  
> [!NOTE]  
>  Excel 的日期與 1900年前兩個月的 OLE Automation 日期的不同。 也有差異如果**1904年日期系統**核取選項。 下列程式碼範例不會解決這些差異。  
  
## <a name="using-a-namedrange-control"></a>使用 NamedRange 控制項  
  
-   這個範例適用於文件層級自訂。 下列程式碼必須放置在工作表類別中，不在`ThisWorkbook`類別。  
  
#### <a name="to-store-a-date-value-in-a-named-range"></a>將日期值中的具名範圍  
  
1.  建立<xref:Microsoft.Office.Tools.Excel.NamedRange>控制項的儲存格**A1**。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#50)]  
  
2.  將今天的日期設定的值為`NamedRange1`。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#51)]  
  
#### <a name="to-retrieve-a-date-value-from-a-named-range"></a>若要擷取之具名範圍的日期值  
  
1.  擷取日期值從`NamedRange1`。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#52)]  
  
## <a name="using-native-excel-ranges"></a>使用原生 Excel 範圍  
  
#### <a name="to-store-a-date-value-in-a-native-excel-range-object"></a>將日期值中的原生 Excel 範圍物件  
  
1.  建立<xref:Microsoft.Office.Interop.Excel.Range>表示儲存格**A1**。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#25)]  
  
2.  將今天的日期設定的值為`rng`。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#26)]  
  
#### <a name="to-retrieve-a-date-value-from-a-native-excel-range-object"></a>若要從原生的 Excel 範圍擷取日期值  
  
1.  擷取日期值從`rng`。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#27)]  
  
## <a name="see-also"></a>請參閱  
 [使用範圍](../vsto/working-with-ranges.md)   
 [Excel 物件模型概觀](../vsto/excel-object-model-overview.md)   
 [NamedRange 控制項](../vsto/namedrange-control.md)   
 [如何： 以程式設計方式參考程式碼中的工作表範圍](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [如何： 將 NamedRange 控制項加入工作表](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office 方案中的選擇性參數](../vsto/optional-parameters-in-office-solutions.md)  
  
  
---
title: "如何： 以程式設計方式顯示工作表註解 |Microsoft 文件"
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
- worksheets, comments
- comments, worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c43e33030cffc78bc8ee4a0665c9334bc6e8bca7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>如何：以程式設計方式顯示工作表註解
  您可以透過程式設計方式，顯示及隱藏 Microsoft Office Excel 工作表中的註解。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>在文件層級自訂中，顯示工作表上的所有註解  
  
1.  如果您想要顯示註解，請將 <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> 屬性設定為 **true** ；否則設定為 **false**。 這個程式碼必須放置在工作表類別中，而不是 `ThisWorkbook` 類別中。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>在應用程式層級 VSTO 增益集中，顯示工作表上的所有註解  
  
1.  如果您想要顯示註解，請將 <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> 屬性設定為 **true** ；否則設定為 **false**。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]  
  
## <a name="see-also"></a>請參閱  
 [使用工作表](../vsto/working-with-worksheets.md)   
 [如何： 以程式設計方式加入和刪除工作表註解](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)   
 [主項目和主控制項概觀](../vsto/host-items-and-host-controls-overview.md)  
  
  
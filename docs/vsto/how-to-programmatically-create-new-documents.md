---
title: "如何： 以程式設計方式建立新文件 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 09e6f9e0e2bc6a001f6a2b67c733f11bfb725563
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-create-new-documents"></a>如何：以程式設計方式建立新文件
  當您以程式設計方式建立文件時，新的文件就是原生的 <xref:Microsoft.Office.Interop.Word.Document> 物件。 這個物件沒有 <xref:Microsoft.Office.Tools.Word.Document> 主項目的其他事件和資料繫結功能。 如需詳細資訊，請參閱 [主項目和主控制項的程式設計限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 當您開發文件層級專案時，您無法以程式設計方式在專案中加入 <xref:Microsoft.Office.Tools.Word.Document> 主項目。 在 VSTO 增益集專案中，您可以在執行階段將任何 <xref:Microsoft.Office.Interop.Word.Document> 物件轉換成 <xref:Microsoft.Office.Tools.Word.Document> 主項目。 如需詳細資訊，請參閱 [在 VSTO 增益集的執行階段中擴充 Word 文件和 Excel 活頁簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)。  
  
### <a name="to-create-a-new-document-based-on-the-normal-template"></a>根據 Normal 範本建立新文件  
  
-   使用 <xref:Microsoft.Office.Interop.Word.Documents> 集合的 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 方法，根據 Normal 範本建立新文件。 若要使用這個程式碼範例，請從專案的 `ThisDocument` 或 `ThisAddIn` 類別中執行它。  
  
     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]  
  
## <a name="using-custom-templates"></a>使用自訂範本  
 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A>方法有選擇性*範本*引數，建立新的文件根據 Normal 範本以外的範本。 您必須提供範本的檔案名稱和完整路徑。  
  
#### <a name="to-create-a-new-document-based-on-a-custom-template"></a>根據自訂範本建立新文件  
  
-   呼叫 <xref:Microsoft.Office.Interop.Word.Documents> 集合的 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 方法，並指定範本的路徑。 若要使用這個程式碼範例，請從專案的 `ThisDocument` 或 `ThisAddIn` 類別中執行它。  
  
     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]  
  
## <a name="see-also"></a>請參閱  
 [如何： 以程式設計方式開啟現有文件](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [主項目和主控制項的程式設計限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 方案中的選擇性參數](../vsto/optional-parameters-in-office-solutions.md)  
  
  
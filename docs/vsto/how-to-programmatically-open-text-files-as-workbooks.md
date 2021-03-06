---
title: "如何： 以程式設計方式文字檔開啟為活頁簿 |Microsoft 文件"
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 45d2b85ea8c005d56ddc076d0b758a0c9e4a2d67
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>如何：以程式設計方式將文字檔開啟為活頁簿
  您可以開啟文字檔，為活頁簿。 您必須傳遞您想要開啟的文字檔案的名稱。 您可以指定數個選擇性參數的詳細資訊，例如開始剖析和資料行的格式檔案中資料的資料列編號。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>範例  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 這個範例需要下列元件：  
  
-   名為逗號分隔的文字檔案`Test.txt`，其中包含至少三行文字。  
  
-   文字檔案`Test.txt`儲存在磁碟機 c。  
  
## <a name="see-also"></a>請參閱  
 [使用活頁簿](../vsto/working-with-workbooks.md)   
 [如何： 以程式設計方式開啟活頁簿](../vsto/how-to-programmatically-open-workbooks.md)   
 [如何： 以程式設計方式建立新的活頁簿](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [如何： 以程式設計方式儲存活頁簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以程式設計方式關閉活頁簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 方案中的選擇性參數](../vsto/optional-parameters-in-office-solutions.md)  
  
  
---
title: "如何：變更組建輸出目錄 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 14aad8b82a3757fecb1d449a671fc07c2582bb5f
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-change-the-build-output-directory"></a>如何：變更組建輸出目錄
您可以根據組態 (針對偵錯及/或發行) 為專案所產生的輸出指定位置。  
  
> [!NOTE]
>  如果您有 [安裝]  專案，請參閱本文結尾的附註。  
  
## <a name="changing-the-build-output-directory"></a>變更組建輸出目錄  
  
#### <a name="to-change-the-build-output-directory"></a>變更組建輸出目錄  
  
1.  在功能表列上，選擇 [ **專案**]、[ *Appname* **屬性**]。 您也可以在 [ **方案總管** ] 中的專案節點上按一下滑鼠右鍵，並選取 [ **屬性**]。  
  
2.  如果您有 Visual Basic 專案，請選取 [ **編譯** ] 索引標籤。如果您有 C# 專案，請選取 [建置] 索引標籤。如果您的 C++ 專案或 JavaScript 專案，選取 [ **一般** ] 索引標籤。  
  
3.  在頂端的組態下拉式清單中，選擇您想要變更其輸出檔位置的組態 (偵錯、發行或全部)。  
  
     尋找輸出路徑項目 (Visual Basic 中的 [**建置輸出路徑** ]、Visual C++ 中的 [ **輸出目錄** ]、JavaScript 和 C# 中的 [ **輸出路徑** ])。 指定相對於專案目錄的新建置輸出目錄。  
  
> [!NOTE]
>  在安裝專案中，[輸出檔名稱]  方塊只會變更 Setup.exe 檔案的位置，而非專案檔案的位置。 如需詳細資訊，請參閱 **建置、組態屬性、部署專案屬性對話方塊**。  
  
## <a name="see-also"></a>請參閱  
 [專案設計工具、建置頁面 (C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [一般屬性頁面 (專案)](/cpp/ide/general-property-page-project)   
 [編譯和建置](../ide/compiling-and-building-in-visual-studio.md)
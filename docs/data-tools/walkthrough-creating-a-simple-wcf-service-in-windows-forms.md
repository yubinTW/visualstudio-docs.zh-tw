---
title: "逐步解說： 在 Windows Form 中建立簡單的 WCF 服務 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c45ea549f17d71fd524a96e7d019c2b0d86bc628
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>逐步解說： 在 Windows Form 中建立簡單的 WCF 服務
本逐步解說示範如何建立簡單的 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 服務、予以測試，然後從 Windows Form 應用程式加以存取。  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-service"></a>建立服務  
  
#### <a name="to-create-a-wcf-service"></a>建立 WCF 服務  
  
1.  在 [ **檔案** ] 功能表上，指向 [ **新增** ]，然後按一下 [ **專案**]。  
  
2.  在**新專案**對話方塊方塊中，展開  **Visual Basic**或**Visual C#**節點，然後按一下**WCF**，後面接著**WCF服務程式庫**。 按一下**確定**開啟專案。  
  
     ![WCF 服務程式庫專案](../data-tools/media/wcf1.PNG "wcf1")  
  
    > [!NOTE]
    >  這樣會建立一個可進行測試和存取的工作服務。 以下兩個步驟示範如何修改預設方法以使用不同的資料類型。 在實際的應用程式中，您也會將自己的功能加入服務。  
  
3.  ![IService1 檔案](../data-tools/media/wcf2.png "wcf2")  
  
     在**方案總管 中**，按兩下 IService1.vb 或 IService1.cs，並尋找以下的一行：  
  
     [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
     [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]  
  
     變更的類型`value`字串參數：  
  
     [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
     [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]  
  
     請注意上述程式碼中的 `<OperationContract()>` 或 `[OperationContract]` 屬性。 服務所公開的所有方法都需要這些屬性。  
  
4.  ![Service1 檔案](../data-tools/media/wcf3.png "wcf3")  
  
     在**方案總管 中**，按兩下 Service1.vb 或 Service1.cs，並尋找以下的一行：  
  
     [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
     [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]  
  
     將值參數的類型變更為字串：  
  
     [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
     [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]  
  
## <a name="testing-the-service"></a>測試服務  
  
#### <a name="to-test-a-wcf-service"></a>測試 WCF 服務  
  
1.  按**F5**來執行服務。 A **WCF 測試用戶端**將顯示表單並載入服務。  
  
2.  在**WCF 測試用戶端**表單中，按兩下**getdata （)**下的方法**IService1**。 **GetData**索引標籤會顯示。  
  
     ![GetData &#40; &#41;方法](../data-tools/media/wcf4.png "wcf4")  
  
3.  在**要求**方塊中，選取**值**欄位，然後輸入`Hello`。  
  
     ![值欄位](../data-tools/media/wcf5.png "wcf5")  
  
4.  按一下**Invoke**  按鈕。 如果**安全性警告**對話方塊隨即出現，請按一下**確定**。 結果會顯示在**回應**方塊。  
  
     ![[回應] 方塊中的結果](../data-tools/media/wcf6.png "wcf6")  
  
5.  在**檔案**功能表上，按一下 **結束**關閉測試表單。  
  
## <a name="accessing-the-service"></a>存取服務  
  
#### <a name="to-reference-a-wcf-service"></a>參考 WCF 服務  
  
1.  在**檔案**功能表上，指向**新增**，然後按一下 **新專案**。  
  
2.  在**新專案**對話方塊方塊中，展開  **Visual Basic**或**Visual C#**節點，然後選取**Windows**，然後選取  **Windows Forms 應用程式**。 按一下**確定**開啟專案。  
  
     ![Windows Form 應用程式專案](../data-tools/media/wcf7.png "wcf7")  
  
3.  以滑鼠右鍵按一下**WindowsApplication1**按一下**加入服務參考**。 **加入服務參考**對話方塊隨即出現。  
  
4.  在**加入服務參考**對話方塊中，按一下 **探索**。  
  
     ![[加入服務參考] 對話方塊](../data-tools/media/wcf8.png "wcf8")  
  
     **Service1**將顯示在**服務**窗格。  
  
5.  按一下**確定**加入服務參考。  
  
#### <a name="to-build-a-client-application"></a>建置用戶端應用程式  
  
1.  在**方案總管] 中**，連按兩下**Form1.vb**或**Form1.cs** ，開啟 [Windows Form 設計工具，如果它尚未開啟。  
  
2.  從**工具箱**，拖曳`TextBox`控制項，`Label`控制項和`Button`控制項拖曳至表單。  
  
     ![將控制項加入表單](../data-tools/media/wcf9.png "wcf9")  
  
3.  按兩下 [`Button`]，並將下列程式碼加入 `Click` 事件處理常式：  
  
     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]  
  
4.  在**方案總管 中**，以滑鼠右鍵按一下**WindowsApplication1**按一下**設定為啟始專案**。  
  
5.  按**F5**執行專案。 輸入一些文字，然後按一下按鈕。 標籤會顯示「您輸入：」以及您輸入的文字。  
  
     ![結果的顯示格式](../data-tools/media/wcf10.png "wcf10")  
  
## <a name="see-also"></a>請參閱  
 [Visual Studio 中的 Windows Communication Foundation 服務和 WCF 資料服務](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
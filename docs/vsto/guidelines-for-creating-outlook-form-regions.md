---
title: "指導方針建立 Outlook 表單區域 |Microsoft 文件"
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
- form regions [Office development in Visual Studio], guidelines
- icons [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 1e82a4428dde7aa25c7e9a3d7d74017b9f2a874f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="guidelines-for-creating-outlook-form-regions"></a>建立 Outlook 表單區域的方針
  下列資訊可協助您最佳化表單區域及避免發生可能的問題：  
  
-   [使用表單區域名稱](#UsingFormRegions)。  
  
-   [停用表單區域繼承](#DisablingInheritance)。  
  
-   [了解類型和訊息類別名稱](#ClassNames)。  
  
-   [設計讀取窗格的相鄰型表單區域](#ReadingPane)。  
  
-   [使用最佳圖示大小](#UsingOptimal)。  
  
 如需表單區域的詳細資訊，請參閱 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
##  <a name="UsingFormRegions"></a> Using Form Region Names  
 可用來描述表單區域的名稱有好幾個。 請務必了解這些名稱之間的差異，以及這些名稱對表單區域的影響。 下表說明每個名稱。  
  
|表單區域名稱|描述|  
|----------------------|-----------------|  
|表單區域項目名稱|這個名稱是您在 [加入新項目]  對話方塊中為 [Outlook 表單區域]  指定的名稱。 這也是出現在方案總管 中表單區域程式碼檔的名稱。|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> 屬性|您會在 [新的 Outlook 表單區域精靈]  的 [提供描述文字和選取顯示設定]  頁面中指定這個名稱。 這個名稱會顯示為 [屬性]  視窗中的 **FormRegionName** 屬性。<br /><br /> 使用 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> 屬性指定識別 Outlook 使用者介面 (UI) 中表單區域的標籤。 針對獨立型表單區域，這個名稱會顯示為 Outlook 項目之功能區上的按鈕。<br /><br /> 針對相鄰型表單區域，這個名稱會顯示為表單區域上方的標題文字。|  
|Microsoft.Office.Tools.Outlook.FormRegionName 屬性|當您將 [Outlook 表單區域]  項目加入專案時，Visual Studio 會將這個屬性設為表單區域的完整名稱。 預設的完整名稱是 VSTO 增益集名稱，再接一個點，後接表單區域名稱，例如 `OutlookAddIn1.FormRegion1`。<br /><br /> 這個完整名稱也會顯示為表單區域 Factory 類別頂端的屬性。<br /><br /> 使用 Microsoft.Office.Tools.Outlook.FormRegionName 屬性唯一識別所有 Outlook VSTO 增益集的表單區域。您無法變更 Microsoft.Office.Tools.Outlook.FormRegionName 屬性的值，藉由重新命名表單區域項目或變更<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A>屬性。 若要變更此名稱，您必須修改表單區域程式碼檔案中的 Microsoft.Office.Tools.Outlook.FormRegionName 屬性。|  
  
##  <a name="DisablingInheritance"></a> Disabling Form Region Inheritance  
 根據預設，自訂訊息類別會繼承基底訊息類別的所有表單區域關聯。 例如，名為訊息類別`IPM.Task.Contoso`衍生自 IPM。工作。 因此，`IPM.Task.Contoso`繼承 IPM 的表單區域關聯。工作。  
  
 如果您不要表單區域與任何衍生的訊息類別相關聯，請將表單區域的 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> 屬性設為 **true**。 例如，如果您將相鄰型表單區域關聯 IPM。工作並設定<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A>屬性**true**，表單區域將只會附加至標準工作表單底部。 表單區域將不會附加至任何自訂的標準工作表單版本底部。  
  
##  <a name="ClassNames"></a> 了解類型和訊息類別名稱  
 Outlook 項目的類型與 Outlook 項目的訊息類別名稱不同。 例如，RSS 項目的型別名稱是 Microsoft.Office.Interop.Outlook.PostItem。 RSS 項目的訊息類別名稱是 IPM。Post.RSS。  
  
 請使用類型名稱在程式碼中參考 Outlook 項目。 如需類型名稱的清單，請參閱 [讓表單區域與 Outlook 訊息類別產生關聯](../vsto/associating-a-form-region-with-an-outlook-message-class.md)。  
  
 使用 [新的 Outlook 表單區域精靈]  中 Outlook 項目的訊息類別名稱，可產生項目與表單區域的關聯。 如需有效訊息類別名稱的清單，請參閱 [讓表單區域與 Outlook 訊息類別產生關聯](../vsto/associating-a-form-region-with-an-outlook-message-class.md)。  
  
##  <a name="ReadingPane"></a> Designing Adjoining Form Regions for the Reading Pane  
 您可以使用 Outlook [讀取窗格] 預覽 Outlook 項目，而不需開啟該項目。 [讀取窗格] 的設計僅為用於讀取。 因此，當項目和表單區域在 [讀取窗格] 中開啟時，加入相鄰型表單區域的輸入控制項 (例如文字方塊) 可能不會如預期般運作。  
  
 例如，如果在 [讀取窗格] 中開啟含有相鄰型表單區域的項目，則可能發生下列情況：  
  
1.  選取文字方塊中位於表單區域上的部分文字。  
  
2.  按下 DELETE 鍵。  
  
3.  整個郵件項目都會被刪除，而不只是文字方塊中的文字。  
  
 如果您要設計包含輸入控制項的相鄰型表單區域，請測試 [讀取窗格] 中的控制項，確認這些控制項可正常運作。 請考慮加入自訂程式碼，以停用未如預期般運作的控制項。  
  
 或者，您可以將表單區域的 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ShowInspectorRead%2A> 屬性設為 **False**。 這樣就無法在 [讀取窗格] 中使用表單區域。  
  
##  <a name="UsingOptimal"></a> Using Optimal Icon Sizes  
 您可以在 [屬性]  視窗的 **Icons** 屬性群組中設定圖示屬性，藉此指定表單區域要顯示的圖示。 使用下列方針可達成最佳視覺品質：  
  
-   針對 [頁面]  圖示，使用可攜式網路圖形 (PNG) 檔。  
  
-   **視窗** 圖示應該是 32 x 32 像素。  
  
-   所有其他圖示應該是 16 x 16 像素。  
  
 **頁面** 圖示會出現在擁有獨立型、取代型或全部取代型表單區域之項目的偵測器功能區上。  
  
 **視窗** 圖示會出現在顯示取代型或全部取代型表單區域之開啟項目的通知區域和 ALT+TAB 對話方塊中。  
  
## <a name="see-also"></a>請參閱  
 [在執行階段存取表單區域](../vsto/accessing-a-form-region-at-run-time.md)   
 [建立 Outlook 表單區域](../vsto/creating-outlook-form-regions.md)   
 [逐步解說： 設計 Outlook 表單區域](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [如何： 在 Outlook 增益集專案中加入表單區域](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [讓表單區域與 Outlook 訊息類別產生關聯](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  
---
title: "如何： 將內容控制項加入 Word 文件 |Microsoft 文件"
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
- restricted permissions [Office development in Visual Studio]
- DropDownListContentControl, adding to documents
- BuildingBlockGalleryContentControl, adding to documents
- partial document protection [Office development in Visual Studio]
- RichTextContentControl, adding to documents
- Word [Office development in Visual Studio], partial document protection
- content controls [Office development in Visual Studio], protecting
- PictureContentControl, adding to documents
- GroupContentControl, adding to documents
- document protection [Office development in Visual Studio]
- PlainTextContentControl, adding to documents
- content controls [Office development in Visual Studio], adding
- ComboBoxContentControl, adding to documents
- DatePickerContentControl, adding to documents
- Word [Office development in Visual Studio], restricted permissions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: b1dd59fc777c012f92baaf96302f7cf031ad151c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-content-controls-to-word-documents"></a>如何：將內容控制項加入至 Word 文件
  在文件層級的 Word 專案中，您可以於設計階段或執行階段，將內容控制項加入專案中的文件。 在 Word VSTO 增益集專案中，您可以在執行階段將內容控制項加入任何開啟的文件。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 本主題說明下列工作：  
  
-   [在設計階段加入內容控制項](#designtime)  
  
-   [在文件層級專案中的執行階段加入內容控制項](#runtimedoclevel)  
  
-   [在 VSTO 增益集專案中的執行階段加入內容控制項](#runtimeaddin)  
  
 如需內容控制項的相關資訊，請參閱 [Content Controls](../vsto/content-controls.md)。  
  
##  <a name="designtime"></a> Adding Content Controls at Design Time  
 在文件層級專案中，有數個方式可於設計階段將內容控制項加入文件：  
  
-   從 [工具箱]  的 [Word 控制項] 索引標籤加入內容控制項。  
  
-   使用與在 Word 中加入原生內容控制項相同的方式，將內容控制項加入文件。  
  
-   從 [資料來源]  視窗將內容控制項拖曳至文件。 若您要於控制項建立的同時將控制項繫結至資料，這麼做非常實用。 如需詳細資訊，請參閱[How to： 從物件的資料填入文件](../vsto/how-to-populate-documents-with-data-from-objects.md)和[如何： 從資料庫的資料填入文件](../vsto/how-to-populate-documents-with-data-from-a-database.md)。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-content-control-to-a-document-by-using-the-toolbox"></a>若要使用工具箱將內容控制項加入文件  
  
1.  在裝載於 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 設計工具的文件中，將游標放在您要加入內容控制項的位置，或選取您要以內容控制項取代的文字。  
  
2.  開啟 [工具箱]  ，然後按一下 [Word 控制項]  索引標籤。  
  
3.  以下列其中一種方式，加入控制項：  
  
    -   按兩下 [工具箱] 中的內容控制項。  
  
         或  
  
    -   按一下 [工具箱]  中的內容控制項，然後按下 ENTER 鍵。  
  
         或  
  
    -   將內容控制項從 [工具箱]  拖曳至文件。 內容控制項會加入至文件中目前選取的位置，而不是滑鼠指標的位置。  
  
> [!NOTE]  
>  您無法使用 [工具箱] <xref:Microsoft.Office.Tools.Word.GroupContentControl>**加入**。 您只能在 Word 中或在執行階段時加入 <xref:Microsoft.Office.Tools.Word.GroupContentControl> 。  
  
> [!NOTE]  
>  Visual Studio 並未提供 [工具箱] 的核取方塊內容控制項。 若要將核取方塊內容控制項加入至文件，您必須以程式設計方式建立 <xref:Microsoft.Office.Tools.Word.ContentControl> 物件。 如需詳細資訊，請參閱 [Content Controls](../vsto/content-controls.md)。  
  
#### <a name="to-add-a-content-control-to-a-document-in-word"></a>若要在 Word 中將內容控制項加入至文件  
  
1.  在裝載於 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 設計工具的文件中，將游標放在您要加入內容控制項的位置，或選取您要以內容控制項取代的文字。  
  
2.  按一下 [功能區] 上的 [開發人員]  索引標籤。  
  
    > [!NOTE]  
    >  如果 [開發人員]  索引標籤沒有顯示，您必須先使其顯示。 如需詳細資訊，請參閱 [如何：在功能區顯示開發人員索引標籤](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)。  
  
3.  按一下 [控制項]  群組中代表所要加入內容控制項的圖示。  
  
##  <a name="runtimedoclevel"></a> Adding Content Controls at Run Time in a Document-Level Project  
 您可以在專案中使用 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 類別之 `ThisDocument` 屬性的方法，在執行階段以程式設計的方式將內容控制項加入文件。 每個方法都有三個多載，可供您以下列方式加入內容控制項：  
  
-   在目前選取位置加入控制項。  
  
-   在指定的範圍加入控制項。  
  
-   加入以文件中的原生內容控制項為基礎的控制項。  
  
 關閉文件時，動態建立的內容控制項不會持續保存在文件中。 不過，原生內容控制項會保留在文件中。 下次文件開啟時，您可以重新建立以原生內容控制項為基礎的內容控制項。 如需詳細資訊，請參閱 [在執行階段將控制項加入至 Office 文件](../vsto/adding-controls-to-office-documents-at-run-time.md)。  
  
> [!NOTE]  
>  若要將核取方塊內容控制項加入至 Word 2010 專案中的文件，您必須建立 <xref:Microsoft.Office.Tools.Word.ContentControl> 物件。 如需詳細資訊，請參閱 [Content Controls](../vsto/content-controls.md)。  
  
#### <a name="to-add-a-content-control-at-the-current-selection"></a>若要在目前選取位置加入內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有單一參數來代表新控制項的名稱。  
  
     下列程式碼範例會使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法，將新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 加入文件的開頭。 若要執行這個程式碼，請將程式碼加入專案的 `ThisDocument` 類別中，並從 `AddRichTextControlAtSelection` 事件處理常式呼叫 `ThisDocument_Startup` 方法。  
  
     [!code-csharp[Trin_ContentControlReference#700](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#700)]
     [!code-vb[Trin_ContentControlReference#700](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#700)]  
  
#### <a name="to-add-a-content-control-at-a-specified-range"></a>若要在指定的範圍加入內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有<xref:Microsoft.Office.Interop.Word.Range>參數。  
  
     下列程式碼範例會使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法，將新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 加入文件的開頭。 若要執行這個程式碼，請將程式碼加入專案的 `ThisDocument` 類別中，並從 `AddRichTextControlAtRange` 事件處理常式呼叫 `ThisDocument_Startup` 方法。  
  
     [!code-csharp[Trin_ContentControlReference#701](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#701)]
     [!code-vb[Trin_ContentControlReference#701](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#701)]  
  
#### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>若要加入以原生內容控制項為基礎的內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有 Microsoft.Office.Interop.Word.ContentControl 參數。  
  
     下列程式碼範例會針對文件中的每個原生 Rich Text 控制項，使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法建立新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 。 若要執行這個程式碼，請將程式碼加入專案的 `ThisDocument` 類別中，並從 `CreateRichTextControlsFromNativeControls` 事件處理常式呼叫 `ThisDocument_Startup` 方法。  
  
     [!code-csharp[Trin_ContentControlReference#702](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#702)]
     [!code-vb[Trin_ContentControlReference#702](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#702)]  
  
##  <a name="runtimeaddin"></a> 在 VSTO 增益集專案中的執行階段加入內容控制項  
 您可以使用 VSTO 增益集，透過程式設計的方式，在執行階段將內容控制項加入至任何開啟的文件。 若要這麼做，請產生以開啟文件為基礎的 <xref:Microsoft.Office.Tools.Word.Document> 主項目，然後使用這個主項目之 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 屬性的方法。 每個方法都有三個多載，可供您以下列方式加入內容控制項：  
  
-   在目前選取位置加入控制項。  
  
-   在指定的範圍加入控制項。  
  
-   加入以文件中的原生內容控制項為基礎的控制項。  
  
 關閉文件時，動態建立的內容控制項不會持續保存在文件中。 不過，原生內容控制項會保留在文件中。 下次文件開啟時，您可以重新建立以原生內容控制項為基礎的內容控制項。 如需詳細資訊，請參閱 [Persisting Dynamic Controls in Office Documents](../vsto/persisting-dynamic-controls-in-office-documents.md)。  
  
 如需在 VSTO 增益集專案中產生主項目的詳細資訊，請參閱[擴充 Word 文件和 Excel 活頁簿，在 VSTO 增益集在執行階段](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)。  
  
> [!NOTE]  
>  若要將核取方塊內容控制項加入文件，您必須建立 <xref:Microsoft.Office.Tools.Word.ContentControl> 物件。 如需詳細資訊，請參閱 [Content Controls](../vsto/content-controls.md)。  
  
#### <a name="to-add-a-content-control-at-the-current-selection"></a>若要在目前選取位置加入內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有單一參數來代表新控制項的名稱。  
  
     下列程式碼範例會使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法，將新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 加入使用中文件的開頭。 若要執行這個程式碼，請將程式碼加入專案的 `ThisAddIn` 類別中，並從 `AddRichTextControlAtSelection` 事件處理常式呼叫 `ThisAddIn_Startup` 方法。  
  
     [!code-vb[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#1)]  
  
#### <a name="to-add-a-content-control-at-a-specified-range"></a>若要在指定的範圍加入內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有<xref:Microsoft.Office.Interop.Word.Range>參數。  
  
     下列程式碼範例會使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法，將新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 加入使用中文件的開頭。 若要執行這個程式碼，請將程式碼加入專案的 `ThisAddIn` 類別中，並從 `AddRichTextControlAtRange` 事件處理常式呼叫 `ThisAddIn_Startup` 方法。  
  
     [!code-vb[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#2)]  
  
#### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>若要加入以原生內容控制項為基礎的內容控制項  
  
1.  使用<xref:Microsoft.Office.Tools.Word.ControlCollection>方法具有名稱`Add` \<*控制項類別*> (其中*控制項類別*是您想要加入，例如的內容控制項類別名稱<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>)，且具有 Microsoft.Office.Interop.Word.ContentControl 參數。  
  
     下列範例程式碼會使用 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 方法，在文件開啟之後，對文件中每一個原生 Rich Text 控制項建立新的 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 。 若要使用這個程式碼，請將程式碼加入專案中的 `ThisAddIn` 類別。  
  
     [!code-vb[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#3)]  
  
     若為 C#，您還必須將 `Application_DocumentOpen` 事件處理常式附加至 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> 事件。  
  
     [!code-csharp[Trin_WordAddInDynamicControls#6](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#6)]  
  
## <a name="see-also"></a>請參閱  
 [使用擴充物件自動化 Word](../vsto/automating-word-by-using-extended-objects.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [在執行階段將控制項加入 Office 文件](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)  
  
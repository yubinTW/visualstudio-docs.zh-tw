---
title: "從程式碼中建立相依性圖表 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 18477479255ff7af8216d093830c6c0d60fa50dc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="create-dependency-diagrams-from-your-code"></a>從程式碼中建立相依性圖表

若要以視覺化方式檢視您的軟體系統高層級的邏輯架構，建立*相依性圖表*Visual Studio 中。 若要確定您的程式碼保持一致與這個設計中，以驗證程式碼相依性圖表。 您可以建立 Visual C# 和 Visual Basic 專案的相依性圖表。 若要查看哪些 Visual Studio 版本支援這項功能，請參閱 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。

![建立相依性圖表](../modeling/media/layerdiagramvisualizecode.png "LayerDiagramVisualizeCode")

相依性圖表，可讓您將 Visual Studio 方案項目組織成邏輯的抽象群組稱為*層*。 您可以使用圖層來說明這些成品所執行的工作，或系統的主要元件。 每個圖層都可以包含其他圖層以描述更詳細的工作。 您也可以指定預定或現有*相依性*圖層之間。 這些表示為箭號的相依性，顯示哪些圖層可以使用或目前使用其他圖層代表的功能。 若要維持程式碼的架構控制，請在圖表上顯示預期的相依性，然後根據圖表驗證程式碼。

[影片： 驗證您的架構相依性，即時](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4) 

##  <a name="CreateDiagram"></a>建立相依性圖表

建立相依性圖表之前，請確定您的方案具有模型專案。

> [!IMPORTANT]
> 不要加入、 拖曳，或從模型專案複製現有的相依性圖表，另一個模型專案或方案中的另一個位置。 即使您變更圖表，此方式仍會保存原始圖表的參考。 這樣也會導致圖層驗證無法正確執行，同時可能會造成其他問題，例如項目遺失或嘗試開啟圖表時發生其他錯誤。
>
> 相反地，將新的相依性圖表加入至模型專案。 將來源圖表中的項目複製到新圖表。 儲存模型專案和新的相依性圖表。

#### <a name="to-add-a-new-dependency-diagram-to-a-modeling-project"></a>若要將新的相依性圖表加入至模型專案  
  
1.  在**架構**功能表上，選擇**新的相依性圖表**。  
  
2.  在下**範本**，選擇**相依性圖表**。  
  
3.  命名圖表。  
  
4.  在**加入至模型專案**、 瀏覽至並選取方案中的現有模型專案。  
  
     -或-  
  
     選擇**建立新的模型專案**將新的模型專案加入至方案。  
  
    > [!NOTE]
    >  相依性圖表必須存在於模型專案之內。 但是，您可以將它連結到方案中任何位置的項目。  
  
5.  請務必儲存模型專案和相依性圖表。  

## <a name="drag-and-drop-or-copy-and-paste-from-a-code-map"></a>拖曳和卸除，或複製並貼上，從程式碼對應

1. 產生 Code Map，用於在方案中使用**架構**功能表。 

2. 請考慮套用程式碼對應篩選來移除方案資料夾和 「 測試資產 」，如果您只想要強制執行產品程式碼中的相依性。

3. 在產生的 Code Map，移除 「 外部 」 節點中，或其展開以顯示 外部組件，根據您要強制執行命名空間相依性，並刪除非必要的組件 Code Map。 

4. 建立新的相依性圖表的方案使用**架構**功能表

5. 選取 在 Code Map 上的所有節點 (使用_Ctrl_ + _A_，或使用拖放矩形選取範圍，藉由按下_Shift_金鑰之前按一下、 拖曳和版本。

6. 拖曳和卸除或複製和貼上，選取的項目到新的相依性驗證圖表。 

7. 這會顯示目前的應用程式架構。 決定您想要的架構並據此修改相依性圖表。

![產生程式碼對應的相依性圖表](media/dependency-validation-01.png)
  
##  <a name="CreateLayers"></a>從成品建立圖層  
 您可以從 Visual Studio 方案項目 (例如，專案、程式碼檔、命名空間、類別和方法) 建立圖層。 這樣會自動建立這些圖層和項目之間的連結，將這些項目納入圖層驗證程序中。  
  
 您也可以將圖層連結至不支援驗證的項目，例如 Word 文件或 PowerPoint 簡報，使您可以將圖層與規格或計劃連結。 您也可以將圖層連結至多個應用程式所共用的專案檔案，但驗證程序不會包含這些以泛型名稱顯示的圖層，例如「Layer 1」和「Layer 2」。  
  
 若要查看連結的項目是否支援驗證，請開啟**圖層總管**並檢查**支援驗證**項目的屬性。 請參閱[管理成品的連結](#Managing)。  
  
|**若要**|**請遵循下列步驟**|  
|------------|----------------------------|  
|建立單一成品的圖層|<ol><li>拖曳到相依性圖表的項目，從下列來源：<br /><br /> <ul><li>**方案總管**<br /><br />         例如，您可以拖曳檔案或專案。</li><li>Code Map<br /><br />         請參閱[對應方案之間的相依性](../modeling/map-dependencies-across-your-solutions.md)和[使用 code map 偵錯應用程式](../modeling/use-code-maps-to-debug-your-applications.md)。</li><li>**類別檢視**或**物件瀏覽器**</li></ul><br />     圖層會出現在圖表上，並且連結到成品。</li><li>重新命名圖層以反映相關程式碼或成品的責任。</li></ol> **重要事項：**將二進位檔案拖曳到相依性圖表中，不會自動將其模型專案的參考。 您必須手動加入您要驗證模型專案的二進位檔案。 **若要將二進位檔案加入至模型專案** <ol><li>在**方案總管 中**，開啟模型專案的捷徑功能表，然後選擇**加入現有項目**。</li><li>在**加入現有項目**對話方塊中，瀏覽至二進位檔案、 選取它們，然後選擇**確定**。     二進位檔案會出現在模型專案中。</li><li>在**方案總管 中**，選擇您加入，，然後按下的二進位檔案**F4**開啟**屬性**視窗。</li><li>在每一個二進位檔案，設定**建置動作**屬性**驗證**。</li></ol>|  
|為所有選取的成品建立單一圖層|將所有成品都拖曳至相依性圖表中，在相同的時間。<br /><br /> 圖層隨即出現在圖表上，並且連結到所有成品。|  
|為每個選取的成品建立圖層|按住不放**SHIFT**索引鍵時拖曳的所有成品到相依性圖表中，在相同的時間。 **注意：**如果您使用**SHIFT**鍵來選取某個範圍的項目，請在選取成品之後放開該鍵。 將成品至拖曳圖表時，再次按住該鍵不放。 <br /><br /> 每個成品的圖層隨即出現在圖表上，並且連結到個別成品。|  
|將成品加入至圖層|將成品拖曳至圖層。|  
|建立新的未連結圖層|在**工具箱**，依序展開**相依性圖表**區段，然後再拖曳**層**相依性圖表。<br /><br /> 若要加入多個圖層，請按兩下 [圖層] 工具。 當您完成時，選擇 **指標**工具或按**ESC**索引鍵。<br /><br /> -或-<br /><br /> 開啟相依性圖表的捷徑功能表，選擇 **新增**，然後選擇 **層**。|  
|建立巢狀圖層|將現有的圖層拖曳至另一個圖層上。<br /><br /> -或-<br /><br /> 開啟 圖層的捷徑功能表，選擇 **新增**，然後選擇 **層**。|  
|建立包含兩個或多個現有圖層的新圖層|選取的圖層，開啟您的選擇捷徑功能表，再選擇**群組**。|  
|變更圖層的色彩|設定其**色彩**屬性，以您想要的色彩。|  
|指定與圖層關聯的成品不可屬於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品不可相依於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespace Dependencies**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品必須屬於其中一個指定的命名空間|輸入命名空間中的圖層**Required Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
  
 圖層上的數字表示圖層連結的成品數目。 然而，當您閱讀這個數字時，請記住下列各項：  
  
-   如果圖層連結的成品有包含其他成品，但圖層未直接連結這些其他成品，則數字將只包含連結的成品。 然而，在圖層驗證期間會加入其他成品以進行分析。  
  
     例如，如果圖層連結到單一命名空間，即使命名空間包含類別，連結的成品數目仍為 1。 如果圖層也有命名空間中每個類別的連結，則數字將包含這些已連結的類別。  
  
-   如果圖層包含已連結到成品的其他圖層，即使此容器圖層上的數字未包含那些成品，容器圖層也會連結到那些成品。  
  
##  <a name="Managing"></a>管理圖層與成品之間的連結  
  
1.  相依性圖表中，開啟圖層的捷徑功能表，然後選擇 **檢視連結**。  
  
     **圖層總管**顯示所選取圖層的成品連結。  
  
2.  使用下列工作來管理這些連結：  
  
|**若要**|**在 [圖層總管]**|  
|------------|---------------------------|  
|刪除圖層與成品之間的連結|開啟成品連結的捷徑功能表，然後選擇**刪除**。|  
|將連結從某個圖層移到另一個圖層|將成品連結拖曳至圖表上的現有圖層。<br /><br /> -或-<br /><br /> 1.開啟成品連結的捷徑功能表，然後選擇**剪下**。<br />2.相依性圖表中，開啟圖層的捷徑功能表，然後選擇 **貼上**。|  
|將連結從某個圖層複製到另一個圖層|1.開啟成品連結的捷徑功能表，然後選擇**複製**。<br />2.相依性圖表中，開啟圖層的捷徑功能表，然後選擇 **貼上**。|  
|從現有的成品連結建立新的圖層|將成品連結拖曳至圖表上的空白區域。|  
|確認連結的成品支援針對相依性圖表進行驗證。|查看**支援驗證**成品連結的資料行。|  
  
##  <a name="Discovering"></a>現有相依性反向工程  
 只要與某個圖層關聯的成品參考到與另一個圖層關聯的成品，相依性便會存在。 例如，某個圖層中的類別會宣告在另一個圖層中具有類別的變數。 對於連結到圖表上之圖層的成品，您可以就其現有相依性進行反向工程。  
  
> [!NOTE]
>  您無法針對特定種類的成品進行其相依性的反向工程。 例如，對連結到文字檔的圖層進行反向工程時，無法找出與該圖層之間的任何相依性。 若要查看哪些成品具有可以進行反向工程的相依性，開啟一或多個圖層的捷徑功能表，然後選擇 **檢視連結**。 在**圖層總管**，檢查**支援驗證**資料行。 相依性不會顯示這個資料行的成品進行反向工程**False**。  
  
-   選取一或多個圖層，開啟 選取的圖層的捷徑功能表，然後選擇**產生相依性**。  
  
 通常，您會看到一些不應該存在的相依性。 您可以編輯這些相依性，以便與預期的設計保持一致。  
  
##  <a name="EditDependencies"></a>編輯圖層與相依性以顯示預定的設計  
 若要描述您打算對您的系統或預期的架構進行的變更，編輯 相依性圖表：  
  
|**若要**|**執行這些步驟**|  
|------------|-----------------------------|  
|變更或限制相依性的方向|設定其**方向**屬性。|  
|建立新的相依性|使用**相依性**和**雙向相依性**工具。<br /><br /> 若要繪製多個相依性，請按兩下工具。 當您完成時，選擇 **指標**工具或按**ESC**索引鍵。|  
|指定與圖層關聯的成品不可相依於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespace Dependencies**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品不可屬於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品必須屬於其中一個指定的命名空間|輸入命名空間中的圖層**Required Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
  
##  <a name="EditLayout"></a>變更項目出現在圖表上的方式  
 您可以藉由編輯屬性的方式，變更圖層的大小、圖形、色彩和位置，或相依性的色彩。  
  
##  <a name="Codemaps"></a>探索模式和 code map 上的相依性  
 在建立相依性圖表，您也可以建立**code map**。 這些圖表可協助您在瀏覽程式碼時探索模式和相依性。 使用 [方案總管]、[類別檢視] 或 [物件瀏覽器] 瀏覽組件、命名空間和類別 (這通常會正確對應至現有的圖層)。 如需 Code Map 的詳細資訊，請參閱：  
  
-   [對應方案之間的相依性](../modeling/map-dependencies-across-your-solutions.md)  
  
-   [使用 Code Map 偵錯您的應用程式](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [使用 Code Map 分析器尋找潛在問題](../modeling/find-potential-problems-using-code-map-analyzers.md)  
  
## <a name="see-also"></a>請參閱  
 [影片： 驗證您的架構相依性，即時](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)   
 [相依性圖表： 參考](../modeling/layer-diagrams-reference.md)   
 [相依性圖表： 指導方針](../modeling/layer-diagrams-guidelines.md)   
 [使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)   
 [視覺化程式碼](../modeling/visualize-code.md)

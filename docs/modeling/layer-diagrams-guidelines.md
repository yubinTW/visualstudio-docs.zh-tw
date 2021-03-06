---
title: "相依性圖表： 指導方針 |Microsoft 文件"
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
ms.openlocfilehash: 840758b0b370c452ac4428c6bfdad525662ed420
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="dependency-diagrams-guidelines"></a>相依性圖表： 指導方針
藉由建立描述您的應用程式架構以高層級*相依性圖表*Visual Studio 中。 確定您的程式碼保持一致與這個設計來驗證您的程式碼相依性圖表。 您也可以在建置流程中包含圖層驗證。 請參閱[Channel 9 影片： 設計和驗證架構使用相依性圖表](http://go.microsoft.com/fwlink/?LinkID=252073)。  
  
 若要查看哪些 Visual Studio 版本支援這項功能，請參閱 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。  
  
## <a name="what-is-a-dependency-diagram"></a>什麼是相依性圖表？  
 傳統架構圖表，例如相依性圖表識別主要元件或功能的設計和其相依性的單位。 在圖表上的每個節點稱為*層*，表示命名空間、 專案或其他成品的邏輯群組。 您可以繪製應該存在於您設計中的相依性。 與傳統架構圖表不同的是，您可以在原始程式碼中驗證實際的相依性是否符合所指定的預期相依性。 在 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 上製作正常組建的驗證部分，就可以確保程式碼即使日後變更仍然會繼續依照系統架構。 請參閱[相依性圖表： 參考](../modeling/layer-diagrams-reference.md)。  
  
##  <a name="Update"></a>如何設計使用或更新您的應用程式相依性圖表  
 下列步驟提供如何使用在開發程序內的相依性圖表的概觀。 本主題稍後的章節會描述每個步驟的更多相關詳細資料。 如果您正在開發新的設計，請略過參考現有程式碼的步驟。  
  
> [!NOTE]
>  這些步驟會按大致順序出現。 您可能會想要重疊工作、重新排序以符合自己的情況，以及從專案中每個反覆項目的開頭重新瀏覽。  
  
1.  [建立相依性圖表](#Create)，整個應用程式或其內的圖層。  
  
2.  [定義圖層以代表主要功能區域或元件](#CreateLayers)應用程式。 根據這些圖層的功能，例如「簡報」或「服務」來為圖層命名。 如果您有[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]方案，您可將每個圖層關聯的集合*成品*，例如專案、 命名空間、 檔案等等。  
  
3.  [探索現有相依性](#Generate)圖層之間。  
  
4.  [編輯圖層與相依性](#EditArchitecture)以顯示已更新您想要以反映程式碼設計。  
  
5.  [設計您的應用程式的新區域](#NewAreas)建立圖層以代表主體架構區塊或元件並定義相依性以顯示每個圖層如何使用其他人。  
  
6.  [編輯圖表的外觀和版面配置](#EditLayout)可協助您與同事討論。  
  
7.  [根據相依性圖表驗證程式碼](#Validate)來反白顯示程式碼所需的架構之間的衝突。  
  
8.  [更新程式碼以符合新的架構](#UpdateCode)。 反覆開發和重構程式碼直到驗證顯示沒有衝突。  
  
9. [在建置流程中包含圖層驗證](#BuildValidation)以確保程式碼繼續依照您的設計。  
  
##  <a name="Create"></a>建立相依性圖表  
 必須在模型專案內建立相依性圖表。 您可以將新的相依性圖表加入至現有的模型專案、 建立新模型專案相依性圖表，或複製在相同的模型專案中現有的相依性圖表。  
  
> [!IMPORTANT]
>  不要加入、 拖曳，或從模型專案複製現有的相依性圖表，另一個模型專案或方案中的另一個位置。 以這種方式複製相依性圖表必須與原始圖表中，相同的參考，即使您修改圖表。 這樣會導致圖層驗證無法正確執行，同時可能會造成其他問題，例如項目遺失或嘗試開啟圖表時發生其他錯誤。  
  
 請參閱[從程式碼中建立相依性圖表](../modeling/create-layer-diagrams-from-your-code.md)。  
  
##  <a name="CreateLayers"></a>定義圖層以代表功能區域或元件  
 圖層代表的邏輯群組*成品*，例如專案、 程式碼檔案、 命名空間、 類別和方法。 您可以從 Visual C# 和 Visual Basic 專案的成品建立圖層，或您可以附加規格或計劃至圖層連結文件，例如 Word 檔案或 PowerPoint 簡報。 每個圖層都會顯示為圖表上的矩形，並顯示連結到圖層的成品數目。 圖層可以包含巢狀圖層以描述更特定的工作。  
  
 一般來說，會根據圖層的函式 (例如，「簡報」或「服務」) 來為圖層命名。 如果成品具有密切相依性，請將它們放在同一圖層。 如果成品可以個別更新或用於個別應用程式，請將它們放在不同的圖層中。 若要深入了解圖層模式，請造訪 「 模式和實務 」 網站[http://go.microsoft.com/fwlink/?LinkId=145794](http://go.microsoft.com/fwlink/?LinkId=145794)。  
  
> [!TIP]
>  某些類型的成品可以連結至圖層，但不是支援針對相依性圖表進行驗證。 若要查看成品是否支援驗證，請開啟**圖層總管**檢查**支援驗證**成品連結的屬性。 請參閱[探索現有圖層之間的相依性](#Generate)。  
  
 更新不熟悉的應用程式時，您可能也會建立 Code Map。 這些圖表可協助您在瀏覽程式碼時探索模式和相依性。 使用 [方案總管] 探索命名空間和類別，這通常會正確對應至現有的圖層。 從 [方案總管] 拖曳到相依性圖表，將這些程式碼成品指派給層級。 您接著可以使用相依性圖表可協助您更新的程式碼，並將它保存在與設計一致。  
  
 請參閱：  
  
-   [從您的程式碼建立相依性圖表](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [使用 Code Map 偵錯您的應用程式](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [對應方案之間的相依性](../modeling/map-dependencies-across-your-solutions.md)  
  
##  <a name="Generate"></a>探索現有圖層之間的相依性  
 只要與某個圖層關聯的成品參考到與另一個圖層關聯的成品，相依性便會存在。 例如，某個圖層中的類別會宣告在另一個圖層中具有類別的變數。 您可以讓相依性進行反向工程以找出現有的相依性。  
  
> [!NOTE]
>  您無法針對特定種類的成品進行其相依性的反向工程。 例如，對連結到文字檔的圖層進行反向工程時，無法找出與該圖層之間的任何相依性。 若要查看哪些成品具有可以進行反向工程的相依性，以滑鼠右鍵按一下一個或多個圖層，然後**檢視連結**。 在**圖層總管**，檢查**支援驗證**資料行。 相依性不會顯示這個資料行的成品進行反向工程**False**。  
  
#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>在圖層之間對現有相依性進行反向工程  
  
-   選取某個圖層或多個圖層，以滑鼠右鍵按一下選取的圖層，然後按一下**產生相依性**。  
  
 通常，您會看到一些不應該存在的相依性。 您可以編輯這些相依性，以便與預期的設計保持一致。  
  
##  <a name="EditArchitecture"></a>編輯圖層與相依性以顯示預定的設計  
 若要描述您打算對您的系統或預期的架構進行的變更，請使用下列步驟編輯相依性圖表。 您也可以考慮先進行一些重構變更來改善程式碼結構，然後再擴充。 請參閱[改善程式碼結構](#Improving)。  
  
|**若要**|**執行這些步驟**|  
|------------|-----------------------------|  
|刪除不應該存在的相依性|按一下 相依性，然後再按**刪除**。|  
|變更或限制相依性的方向|設定其**方向**屬性。|  
|建立新的相依性|使用**相依性**和**雙向相依性**工具。<br /><br /> 若要繪製多個相依性，請按兩下工具。 當您完成時，按一下**指標**工具或按**ESC**索引鍵。|  
|指定與圖層關聯的成品不可相依於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespace Dependencies**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品不可屬於指定的命名空間|輸入命名空間中的圖層**Forbidden Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
|指定與圖層關聯的成品必須屬於其中一個指定的命名空間|輸入命名空間中的圖層**Required Namespaces**屬性。 請使用分號 (**;**) 來分隔命名空間。|  
  
###  <a name="Improving"></a>改善程式碼的結構  
 重構變更屬於改良功能，不會影響應用程式的行為，但是可協助讓程式碼變得更容易變更和在日後進行擴充。 結構完善的程式碼具有易於抽象至相依性圖表的設計。  
  
 例如，如果您為程式碼中每個命名空間建立圖層，然後對相依性進行反向工程，則圖層之間應該會有最小一組的單向相依性。 如果您使用類別或方法做為圖層來建立更詳細的圖表，則結果應該也會有相同的特性。  
  
 如果這不是大小寫，程式碼將會更難在其生命變更，且將較不適合使用相依性圖表進行驗證。  
  
##  <a name="NewAreas"></a>設計您的應用程式的新區域  
 當您著手開發新專案或新專案的新區域時，可以繪製圖層與相依性，以便有助您先識別主要元件，再著手開發程式碼。  
  
-   **顯示可識別的架構模式**相依性圖表，盡可能中。 例如，描述桌面應用程式的相依性圖表可能包括簡報、 網域邏輯和資料存放區等圖層。 涵蓋應用程式內單一功能的相依性圖表可能具有例如模型、 檢視和控制器等的圖層。 如需這類模式的詳細資訊，請參閱[模式和實務： 應用程式架構](http://go.microsoft.com/fwlink/?LinkId=145794)。  
  
-   **建立每個圖層的程式碼成品**例如命名空間、 類別或元件。 這可讓您更容易地遵循程式碼，並將程式碼成品連結至圖層。 一旦建立每個成品後，請將它連結至適當的圖層。  
  
-   **您不必將大部分的類別和其他成品連結至圖層**因為他們落在較大的成品，例如您已連結至圖層的命名空間。  
  
-   **建立新圖表的新功能**。 一般而言，會有一或多個描述整個應用程式的相依性圖表。 如果您要在應用程式內設計新功能，請勿加入或變更現有的圖表。 相反地，請建立自己圖表，以反映程式碼的新組件。 新圖表中的圖層可能包括簡報、網域邏輯和新功能的資料庫層。  
  
     在建置應用程式時，會針對整體圖表和更詳細的功能圖表來驗證您的程式碼。  
  
##  <a name="EditLayout"></a>編輯版面配置以便展示和討論  
 若要協助您識別圖層與相依性，或與小組成員進行討論，請以下列方式編輯圖表的外觀和版面配置：  
  
-   變更圖層的大小、圖形和位置。  
  
-   變更圖層和相依性的色彩。  
  
    -   選取一或多個圖層或相依性、 按一下滑鼠右鍵，然後按一下**屬性**。 在**屬性**視窗中，編輯**色彩**屬性。  
  
##  <a name="Validate"></a>根據圖表驗證程式碼  
 若已編輯圖表，您可以隨時手動針對程式碼驗證圖表，或在每次執行本機組建或 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] 時自動驗證。  
  
 請參閱：  
  
-   [使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)  
  
-   [在建置流程中包含圖層驗證](#BuildValidation)  
  
##  <a name="UpdateCode"></a>更新程式碼以符合新的架構  
 通常，錯誤會出現您驗證針對更新的相依性圖表的程式碼的第一次。 這些錯誤可以有數個原因：  
  
-   成品指派給錯誤的圖層。 在此情況下，請移動成品。  
  
-   類別之類的成品以與架構發生衝突的方式使用另一個類別。 在此情況下，請重構程式碼以移除相依性。  
  
 若要解決這些錯誤，請更新程式碼直到驗證時不再出現錯誤為止。 這通常是反覆的程序。 如需有關這些錯誤的詳細資訊，請參閱[使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)。  
  
> [!NOTE]
>  隨著您開發或重構程式碼，您可能會有新成品来連結至相依性圖表。 不過，這可能不是必要的，比方說在您有代表現有命名空間的圖層，而新的程式碼只會將更詳細的資料加入至這些命名空間時。  
  
 在開發過程中，您可以隱藏驗證期間已報告過的某些衝突。 例如，您可能會想要隱藏已經處理的錯誤，或是與特定情節無關的錯誤。 當您隱藏錯誤時，最好在 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] 中記錄工作項目。 若要執行這項工作，請參閱[使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)。  
  
##  <a name="BuildValidation"></a>在建置流程中包含圖層驗證  
 若要確保在程式碼的日後變更符合相依性圖表，包含您的方案標準建置流程的圖層驗證。 其他小組成員會建置此方案，只要任何程式碼中的相依性和相依性圖表的差異將會報告為建置錯誤。 如需在建置程序中包含圖層驗證的詳細資訊，請參閱[使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)。  
  
## <a name="see-also"></a>請參閱  
 [相依性圖表： 參考](../modeling/layer-diagrams-reference.md)   
 [從您的程式碼建立相依性圖表](../modeling/create-layer-diagrams-from-your-code.md)

---
title: "巡覽及更新程式碼中的圖層模型 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- layer models, navigating in program code
- layer models, updating in program code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e79479e97efd953c1366348454eee70773faf07a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="navigate-and-update-layer-models-in-program-code"></a>巡覽及更新程式碼中的圖層模型
本主題描述圖層模型中的項目和關聯性，而您可以使用程式碼巡覽和更新它們。 如需從使用者的觀點來看的相依性圖表的詳細資訊，請參閱[相依性圖表： 參考](../modeling/layer-diagrams-reference.md)和[相依性圖表： 指導方針](../modeling/layer-diagrams-guidelines.md)。  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer>本主題中所述的模型是在多個一般外觀<xref:Microsoft.VisualStudio.GraphModel>模型。 如果您要撰寫[功能表命令或軌跡擴充功能](../modeling/add-commands-and-gestures-to-layer-diagrams.md)，使用`Layer`模型。 如果您要撰寫[圖層驗證擴充功能](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)，更輕鬆地使用`GraphModel`。  
  
## <a name="transactions"></a>異動  
 當您更新模型時，請考慮將變更納入 `ILinkedUndoTransaction` 中。 這會將您的變更群組為一個交易。 如果任何變更失敗，則會復原整個交易。 如果使用者復原某項變更，則也會一併復原所有變更。  
  
```  
using (ILinkedUndoTransaction t =  
        LinkedUndoContext.BeginTransaction("a name"))  
{   
    // Make changes here ....  
    t.Commit(); // Don't forget this!  
}  
```  
  
## <a name="containment"></a>內含項目  
 ![ILayer 和 ILayerModel 都可以包含 ILayers。] (../modeling/media/layerapi_containment.png "LayerApi_Containment")  
  
 圖層 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayer>) 和圖層模型 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>) 可以包含「註解」和「圖層」。  
  
 圖層 (`ILayer`) 可以包含在圖層模型 (`ILayerModel`) 中，也可以巢狀於另一個 `ILayer` 內。  
  
 若要建立註解或圖層，請在適當的容器上使用建立方法。  
  
## <a name="dependency-links"></a>相依性連結  
 相依性連結是以物件代表。 而且可以使用任一方向進行巡覽：  
  
 ![ILayerDependencyLink 會連接兩個 ILayers。] (../modeling/media/layerapi_dependency.png "LayerApi_Dependency")  
  
 若要建立相依性連結，請呼叫 `source.CreateDependencyLink(target)`。  
  
## <a name="comments"></a>註解  
 註解可以包含在圖層或圖層模型內，也可以連結至任何圖層項目：  
  
 ![註解可以附加至任何圖層項目。] (../modeling/media/layerapi_comments.png "LayerApi_Comments")  
  
 註解可以連結至任何數目的項目 (包含零個項目)。  
  
 若要取得連結至圖層項目的註解，請使用：  
  
```csharp  
ILayerModel model = diagram.GetLayerModel();   
IEnumerable<ILayerComment> comments =   
   model.Comments.Where(comment =>   
      comment.Links.Any(link => link.Target == layerElement));  
  
```  
  
> [!CAUTION]
>  `Comments` 的 `ILayer` 屬性會取得包含在 `ILayer` 內的註解。 但不會取得與它連結的註解。  
  
 在適當的容器上叫用 `CreateComment()`，以建立註解。  
  
 在註解上使用 `CreateLink()`，以建立連結。  
  
## <a name="layer-elements"></a>圖層項目  
 可以包含在模型中的所有類型的項目都是圖層項目：  
  
 ![相依性圖表內容為 ILayerElements。] (../modeling/media/layerapi_layerelements.png "LayerApi_LayerElements")  
  
## <a name="properties"></a>屬性  
 每個 `ILayerElement` 都有名稱為 `Properties` 的字串字典。 您可以使用此字典，將任意資訊連結至任何圖層項目。  
  
## <a name="artifact-references"></a>成品參考  
 成品參考 (<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>) 代表圖層與專案項目 (如檔案、類別或資料夾) 之間的連結。 使用者建立成品建立圖層或從方案總管、 類別檢視或物件瀏覽器拖曳項目拖曳到相依性圖表中加入時。 您可以將任意數目的成品參考連結至圖層。  
  
 [圖層總管] 中的每個資料列都會顯示成品參考。 如需詳細資訊，請參閱[從程式碼中建立相依性圖表](../modeling/create-layer-diagrams-from-your-code.md)。  
  
 專注於成品參考的主體類型和方法如下：  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>. Categories 屬性指出參考哪一種類型的成品 (如類別、可執行檔或組件)。 Categories 決定 Identifier 如何識別目標成品。  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ArtifactReferenceExtensions.CreateArtifactReferenceAsync%2A> 會透過 <xref:EnvDTE.Project> 或 <xref:EnvDTE.ProjectItem> 建立成品參考。 這是一個非同步作業。 因此，您通常會提供在建立完成時呼叫的回呼。  
  
 「圖層成品參考」不應該與使用案例圖中的「成品」混淆。  
  
## <a name="shapes-and-diagrams"></a>圖案和圖表  
 兩個物件都是用來代表圖層模型中的每個項目：<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 和 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape>。 `IShape` 代表圖案在圖表上的位置和大小。 在圖層模型中，每個`ILayerElement`有一個`IShape`，和每`IShape`相依性圖表有一個`ILayerElement`。 `IShape` 也用於 UML 模型。 因此，不是每個 `IShape` 都有圖層項目。  
  
 同樣地，<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel> 會顯示在一個 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> 上。  
  
 在自訂命令或手勢處理常式的程式碼中，您可以透過 `DiagramContext` 匯入，取得目前圖表以及目前圖案選取範圍：  
  
```  
public class ... {  
[Import]  
    public IDiagramContext DiagramContext { get; set; }  
...  
public void ... (...)   
{ IDiagram diagram = this.DiagramContext.CurrentDiagram;  
  ILayerModel model = diagram.GetLayerModel();  
  if (model != null)  
  { foreach (ILayer layer in model.Layers) { ... }}  
  foreach (IShape selected in diagram.SelectedShapes)  
  { ILayerElement element = selected.GetLayerElement();  
    if (element != null) ... }}  
```  
  
 ![每個 ilayerelement 都是由 IShape 呈現。] (../modeling/media/layerapi_shapes.png "LayerApi_Shapes")  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape> 和 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> 也用來顯示 UML 模型。 
  
## <a name="see-also"></a>請參閱  
 [將命令和軌跡加入至相依性圖表](../modeling/add-commands-and-gestures-to-layer-diagrams.md)   
 [相依性圖表中加入自訂架構驗證](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)   
 [將自訂屬性加入至相依性圖表](../modeling/add-custom-properties-to-layer-diagrams.md)   
 [相依性圖表： 參考](../modeling/layer-diagrams-reference.md)   
 [相依性圖表︰方針](../modeling/layer-diagrams-guidelines.md)   

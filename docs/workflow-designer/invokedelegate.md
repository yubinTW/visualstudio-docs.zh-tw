---
title: "InvokeDelegate |Microsoft 文件"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 717e9bec58c1eed248c868144ad72aae55948636
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2018
---
# <a name="invokedelegate"></a>InvokeDelegate
**InvokeDelegate**設計工具會用來建立及設定<xref:System.Activities.Statements.InvokeDelegate>活動。

## <a name="the-invokedelegate-activity"></a>InvokeDelegate 活動
 <xref:System.Activities.Statements.InvokeDelegate> 會呼叫公用委派。

### <a name="using-the-invokedelegate-activity-designer"></a>使用 InvokeDelegate 活動設計工具
 **InvokeDelegate**活動設計工具位於**基本型別**分類**工具箱**，即可存取的哪一個**工具箱**  索引標籤[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)](或者，選取**工具列**從**檢視**功能表或 CRTL + ALT + X。)

 **InvokeDelegate**活動設計工具可以從拖曳**工具箱**，置放到上[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]介面通常用來放置活動，例如內部<xref:System.Activities.Statements.Sequence>。 這會建立一個 <xref:System.Activities.Statements.InvokeDelegate> 活動，具有 InvokeDelegate 的預設 <xref:System.Activities.Activity.DisplayName%2A>。 <xref:System.Activities.Activity.DisplayName%2A>可編輯的標頭中**InvokeDelegate**活動設計工具或在**DisplayName**屬性方格的方塊。

### <a name="the-invokedelegate-properties"></a>InvokeDelegate 屬性
 下表顯示 <xref:System.Activities.Statements.InvokeDelegate> 屬性，並且描述屬性在設計工具中的使用方式。 這些屬性可以在屬性方格中進行編輯，其中有一些可以在 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 設計工具介面上編輯。

|屬性名稱|必要項|使用方式|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> 活動的易記名稱。 預設值為 InvokeDelegate。<br /><br /> 雖然 <xref:System.Activities.Activity.DisplayName%2A> 並非絕對必要，但建議您盡量使用。|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|活動執行時要呼叫之 <xref:System.Activities.ActivityDelegate> 的名稱。 此屬性也可以在設計工具介面上編輯。 這是必要的屬性。|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|被呼叫之委派的引數集合。 索引鍵位於參數物件的名稱<xref:System.Activities.ActivityDelegate>且值為引數的運算式會評估並指派給對應的參數物件。 在屬性方格中，按一下省略符號按鈕，在**DelegateArguments**欄位，它會顯示**DelegateArguments**對話方塊，供您設定此屬性。 按一下**建立引數**欄位來加入引數。|

## <a name="see-also"></a>另請參閱

- [如何：定義並取用工作流程設計工具中的活動委派](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)
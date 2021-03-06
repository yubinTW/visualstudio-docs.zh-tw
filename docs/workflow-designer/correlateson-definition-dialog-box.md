---
title: "CorrelatesOn 定義對話方塊 |Microsoft 文件"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 386d27e96ad1b3a04b9cdb8f76f96ee5e2ad6a46
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2018
---
# <a name="correlateson-definition-dialog-box"></a>CorrelatesOn 定義對話方塊
**CorrelatesOn**對話方塊用於在 Windows 工作流程設計工具編輯<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>屬性<xref:System.ServiceModel.Activities.Receive>活動。 如需詳細資訊，請參閱[接收](../workflow-designer/receive-activity-designer.md)主題。

 <xref:System.ServiceModel.Activities.Receive> 活動之間的相互關聯，會指定某個工作流程中不同服務作業彼此之間的關係。

 下表描述的使用者介面 (UI) 項目**CorrelatesOn**  對話方塊。

|UI 項目|描述|
|----------------|-----------------|
|**CorrelatesWith**|用來路由訊息到適當工作流程執行個體的 <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|**XPath 查詢**|配對的索引鍵/值，其中包含用來從傳入訊息擷取相互關聯資料的查詢。 這會對應至 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 屬性。 XPath 查詢會包含在 <xref:System.ServiceModel.MessageQuerySet> 物件中。|

## <a name="to-launch-the-correlateson-dialog-box"></a>若要啟動 CorrelatesOn 對話方塊
 **接收**活動設計工具可以從拖曳**工具箱**，置放到上[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]介面任一處活動通常放置。 這會建立一個 <xref:System.ServiceModel.Activities.Receive> 活動，具有 Receive 的預設 <xref:System.Activities.Activity.DisplayName%2A>。 選取**接收**活動設計工具，然後按一下省略符號按鈕 （集合） 文字旁邊**CorrelatesOn**屬性方格中的**CorrelatesOn 定義**對話方塊出現。

## <a name="see-also"></a>另請參閱

- <xref:System.ServiceModel.Activities.Receive>
- [新增相互關聯初始設定式對話方塊](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [加入相互關聯對話方塊](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [初始化相互關聯對話方塊](../workflow-designer/initialize-correlation-dialog-box.md)
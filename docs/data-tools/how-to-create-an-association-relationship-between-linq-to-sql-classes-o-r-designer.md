---
title: "如何建立 LINQ to SQL 類別使用 O/R 設計工具之間的關聯性 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 5c86eff5c25dbabb368d7d90ed46be718b8db8e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>如何： 建立 LINQ to SQL 類別 （O/R 設計工具） 之間的關聯
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 中實體類別 (Class) 之間的關聯，與資料庫中資料表之間的關聯性 (Relationship) 類似。 您可以建立使用的實體類別之間的關聯**關聯編輯器** 對話方塊。  
  
您使用時必須選取父類別和子類別**關聯編輯器**對話方塊來建立關聯。 父類別是包含主索引鍵的實體類別，而子類別是包含外部索引鍵的實體類別。 例如，如果要建立與 Northwind 的 Customers 和 Orders 資料表對應的實體類別，則 Customer 類別會是父類別，而 Order 類別會是子類別。  
  
> [!NOTE]
>  當您將資料表從**伺服器總管**/**資料庫總管**到[!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)])，會自動建立根據現有的關聯在資料庫中的外部索引鍵關聯性。  

## <a name="association-properties"></a>關聯屬性
當您在 O/R 設計工具中選取該關聯時，建立關聯之後，有一些可設定的屬性中**屬性**視窗。 (關聯就是相關類別之間的線條)。下表提供關聯屬性的說明。  
  
|屬性|描述|  
|--------------|-----------------|  
|**基數**|控制關聯是一對多還是一對一。|  
|**子屬性**|指定是否要在父代 (Parent) 上建立屬性，這個屬性是位於關聯的外部索引鍵端上之子記錄的集合或參考。 例如，在 Customer 與 Order，之間的關聯如果**子屬性**設**True**，父類別上會建立名為 Orders 的屬性。|  
|**父屬性**|子類別上參考相關父類別的屬性。 例如，在 Customer 與 Order 之間的關聯中，Order 類別上會建立名為 Customer 的屬性，以參考與訂單關聯的客戶。|  
|**參與屬性**|顯示關聯屬性，並提供**省略**按鈕 （…） 來重新開啟**關聯編輯器** 對話方塊。|  
|**唯一**|指定外部目標資料行是否具有唯一性條件約束 (Constraint)。|  
  
## <a name="to-create-an-association-between-entity-classes"></a>若要在實體類別之間建立關聯
  
1.  以滑鼠右鍵按一下代表關聯中的之父類別的實體類別，並指向**新增**，然後按一下 **關聯**。  
  
2.  確認正確**父類別**中選取**關聯編輯器** 對話方塊。  
  
3.  選取**子類別**下拉式方塊中。  
  
4.  選取**關聯屬性**相關的類別。 通常，這會對應至資料庫中定義的外部索引鍵關聯性。 例如，在 Customers 與 Orders 的關聯，**關聯屬性**會針對每個類別的 CustomerID。  
  
5.  按一下**確定**建立關聯。  
  
## <a name="see-also"></a>另請參閱
[LINQ to SQL 工具，Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[逐步解說： 建立 LINQ to SQL 類別](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[DataContext 方法 （O/R 設計工具）](../data-tools/datacontext-methods-o-r-designer.md)   
[如何：表示主索引鍵](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)
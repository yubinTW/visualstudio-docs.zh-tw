---
title: "如何： 以 Office 多語系使用者介面為目標 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 39ee8b6bdcb4ad647164ec555cfa37ee9cfe8f50
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>如何：以 Office 多語系使用者介面為目標
  多語系使用者介面 (MUI) 是可讓使用者變更的使用者介面 (UI) 語言的 Microsoft Office 功能。 比方說，使用英文的 UI 終端使用者可以變更的 ui 語言為西班牙文。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 如果您的應用程式將在使用多個語言的 Office 的人員，您可以加入程式碼，自動變更的 UI 字串符合 Office 所使用的使用者的電腦上 （若使用者已安裝正確的資源） 語言的語言。  
  
### <a name="to-check-the-current-office-ui-setting"></a>若要檢查目前 Office 使用者介面設定  
  
1.  使用<xref:System.Threading.Thread.CurrentUICulture%2A>目前執行緒的屬性。 將 UI 字串以符合所使用的目前使用者的電腦上執行的 Office 版本的語言的語言設定。  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>請參閱  
 [How to: Target Office Applications Through Primary Interop Assemblies](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Office 方案中的晚期繫結](../vsto/late-binding-in-office-solutions.md)  
  
  
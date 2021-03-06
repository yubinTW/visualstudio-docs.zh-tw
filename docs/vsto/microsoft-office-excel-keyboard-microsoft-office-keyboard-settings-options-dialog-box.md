---
title: "選項對話方塊、 Microsoft Office Excel 鍵盤，Microsoft Office 鍵盤設定、 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ExcelOptions.KeyboardMappingScheme
- VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Excel_Keyboard
- VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Excel.Keyboard
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- keyboard shortcuts, Office development in Visual Studio
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: d52b7baf1283f986ee378c800114836da606eca8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box"></a>選項對話方塊、Microsoft Office 鍵盤設定、Microsoft Office Excel 鍵盤
  Microsoft Office Excel 和 Visual Studio 同時處理快顯的索引鍵。 針對不同的命令，在 Excel 中，然後在 Visual Studio 中，可以獨立相同快速鍵組合。 在 Visual Studio 中的文件層級專案中開啟 Excel 時，一次只有一個應用程式接收快顯命令。 根據預設，Visual Studio 會收到所有捷徑命令，但您可以建立 Excel 文件選取具有焦點時，接收這些**動態鍵盤配置**。  
  
 如果您使用未指派給目前正在處理的快速鍵的應用程式中命令的快速鍵，攠摝坫會傳遞給其他應用程式。  
  
 您選取的選項會保持作用中的 Excel 專案直到變更為止。 選取項目不會影響 Microsoft Office Word 專案的專案。您必須進行任何變更 word 使用 Microsoft Office Word 鍵盤選項。  
  
## <a name="uielement-list"></a>UIElement 清單  
 **Visual Studio 鍵盤配置**  
 Visual Studio 會收到所有捷徑命令，即使 Excel 具有焦點。 例如，如果您在 Excel 焦點時按 F5 功能鍵，Visual Studio 會啟動偵錯您的方案。  
  
 **動態鍵盤配置**  
 Visual Studio 會在有焦點時，才收到快顯命令。 當 Excel 具有焦點時，Excel 就會收到所有的捷徑命令。 例如，如果您在 Excel 焦點時按 F5 功能鍵，Excel 會開啟**移至** 對話方塊。 如果您按下 F5，Visual Studio 焦點時，Visual Studio 會啟動偵錯您的方案。  
  
## <a name="see-also"></a>請參閱  
 [選項對話方塊、Microsoft Office 鍵盤設定、Microsoft Office Word 鍵盤](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)  
  
  
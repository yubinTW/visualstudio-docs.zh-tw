---
title: "如何在 Visual Studio 中將 app.config 檔案新增到專案 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: d77e86599670ef04b813381da84a03ab1f238af3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>如何：將應用程式組態檔加入至 C# 專案

您可以將應用程式組態檔 (app.config 檔案) 加入 C# 專案，以自訂通用語言執行平台尋找及載入組件檔的方式。 如需應用程式組態檔的詳細資訊，請參閱[執行階段如何找出組件 (.NET Framework)](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)。

> [!NOTE]
> UWP 應用程式不包含 app.config 檔案。

當您建置專案時，開發環境會自動複製您的 app.config 檔案，並將複本的檔案名稱變更為符合可執行檔的名稱，然後移動到 **bin** 目錄。

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>將應用程式組態檔加入 C# 專案

1. 在功能表列中，選擇 [專案] > [加入新項目]。

     [新增項目] 對話方塊隨即出現。

1. 展開 [已安裝] > [Visual C# 項目]，然後選擇 [應用程式組態檔] 範本。

3.在 [名稱] 文字方塊中，輸入名稱，然後選擇 [新增] 按鈕。

     A file named app.config is added to your project.

## <a name="see-also"></a>另請參閱

[管理應用程式設定 (.NET)](../ide/managing-application-settings-dotnet.md)  
[組態檔結構描述 (.NET Framework)](/dotnet/framework/configure-apps/file-schema/index)  
[設定應用程式 (.NET Framework)](/dotnet/framework/configure-apps/index)
---
title: "管理應用程式資源 (.NET) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2006f565edbca8a859cd2c155645e47e083b5528
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2018
---
# <a name="managing-application-resources-net"></a>管理應用程式資源 (.NET)

資源檔案是屬於應用程式的一部分，但不會經過編譯的檔案，例如圖示檔案或音訊檔案。 由於這些檔案不屬於編譯處理程序的一部分，您可以變更它們而無需重新編譯二進位檔。 如果您打算將應用程式當地語系化，您應該針對所有字串和其他在將應用程式當地語系化時需要變更的資源使用資源檔。

如需 .NET 桌面應用程式中的資源的詳細資訊，請參閱 [Resources in Desktop Apps](/dotnet/framework/resources/index)。

## <a name="working-with-resources"></a>使用資源

在 受控碼專案中，開啟 [專案屬性] 視窗。 您可以透過下列方式開啟 [屬性] 視窗：

- 在方案總管中，以滑鼠右鍵按一下專案節點，並選取 [屬性]
- 在 [快速啟動] 視窗中，鍵入「專案屬性」
- 在**方案總管**視窗中選擇 **Alt**+**Enter**

選取 **資源**  索引標籤。您可以在專案尚未包含 .resx 檔案的情況下加入 .resx 檔案、加入和刪除不同種類的資源，以及修改現有的資源。

## <a name="resources-in-other-project-types"></a>其他專案類型中的資源

.NET 專案管理資源的方式和其他專案類型不同。 如需下列資源的詳細資訊：

- 通用 Windows 平台 (UWP) 應用程式，請參閱[應用程式資源和資源管理系統](/windows/uwp/app-resources/)
- C++ 專案，請參閱[使用資源檔](/cpp/windows/working-with-resource-files)和[如何：建立資源](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>另請參閱

[桌面應用程式中的資源 (.NET Framework)](/dotnet/framework/resources/index)
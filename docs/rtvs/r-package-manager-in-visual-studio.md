---
title: "Visual Studio R 工具中的套件管理員 | Microsoft Docs"
description: "如何在 Visual Studio 中使用 R 套件管理員來安裝和管理 R 套件。"
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 14948b0680e570e9045d724ae00adb67bd6b19cd
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="package-manager"></a>套件管理員

Visual Studio R 工具 (RTVS) 套件管理員是用來管理 R 套件的 UI。 若要開啟它，請選取 [R 工具] > [Windows] > [套件]，或按 Ctrl+7。

套件管理員有三個索引標籤。 每個索引標籤都會在左側顯示相關套件清單，並在右側顯示所選取套件的特定詳細資料，包括套件的版本、描述、授權、安裝位置以及其他相關資訊的連結。 右上方的搜尋方塊可讓您篩選清單。

> [!Tip]
> 切換索引標籤時，搜尋方塊中的詞彙仍然會作用。

- [可用的] 可讓您瀏覽要安裝的套件。 如果已經安裝套件，則右側的 [安裝] 按鈕會變更為 [解除安裝]。

    ![Visual Studio R 工具套件管理員中的 [可用的套件] 索引標籤](media/package-manager-available.png)

- [已安裝的] 會顯示所有已安裝和已載入的套件。 套件旁邊的綠點指出已將它載入至 R 工作階段。 左側清單中的紅色 X 圖示或左側的 [解除安裝] 按鈕，可以用來解除安裝套件。 如果已安裝的套件有更新的版本，則套件右側的藍色向上箭號可執行套件。

    ![Visual Studio R 工具套件管理員中的 [已安裝的套件] 索引標籤](media/package-manager-installed.png)

- [已載入] 只會顯示載入至 R 工作階段的套件，而這些套件在出現時全部都會加上一個綠點。 您也可以在這裡解除安裝和更新套件。

    ![Visual Studio R 工具套件管理員中的 [已載入的套件] 索引標籤](media/package-manager-loaded.png)

## <a name="package-locations"></a>套件位置

套件會安裝到下列位置：

- RTVS 隨附的核心套件會安裝在 `C:\Program Files\Microsoft\R Client\R_SERVER\library`
- 其他套件會安裝到 `%userprofile%\Documents\R\win-library\3.3`

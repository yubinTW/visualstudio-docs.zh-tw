---
title: "如何： 從 XML 文件建立 XML 結構描述 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0541e89e72670905172129ffbb141ae8ae9e727f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>HOW TO：從 XML 文件建立 XML 結構描述
XML 編輯器允許您從 XML 文件，建立 XML 結構描述定義語言 (XSD) 結構描述。 XML 執行個體文件會決定如何以下列方式產生結構描述：  
  
-   如果 XML 文件沒有結構描述或與其相關聯的「文件類型定義 (DTD)」，則會使用 XML 文件中的資料來推斷新的 XML 結構描述。  
  
-   如果 XML 文件包含相關聯的 DTD，則外部 DTD 及內部子集將轉換成相對應的 XML 結構描述。  
  
-   如果 XML 文件包含內嵌 XML 資料精簡 (XDR) 結構描述，則 XDR 結構描述會轉換成相對應的 XML 結構描述。  
  
接著，會使用所建立的結構描述來為 XML 文件提供 IntelliSense。  
  
如需結構描述推斷引擎的詳細資訊，請參閱[推斷 XML 結構描述](/dotnet/standard/data/xml/inferring-an-xml-schema)。  
  
### <a name="to-create-an-xml-schema"></a>建立 XML 結構描述  
  
1.  將 XML 執行個體文件載入 XML 編輯器。  
  
2.  按一下**Create Schema**按鈕**工具列**。  
  
     在 XML 執行個體文件中，為每個找到的命名空間，建立 XML 結構描述文件並予以開啟。 每個結構描述會當作暫時的其他檔案開啟。  
  
     結構描述可儲存至磁碟、加入至專案或捨棄。  
  
    > [!NOTE]
    >  **Create Schema**命令也會提供從 XML 編輯器的然後在捷徑功能表**XML**功能表。  
  
## <a name="see-also"></a>請參閱  
 [XML 編輯器](../xml-tools/xml-editor.md)
---
title: "擴充自動程式化 UI 測試和動作記錄以支援 Microsoft Excel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0133db8e1060da48e5938a08ded187fa900b4d30
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2018
---
# <a name="extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel"></a>擴充自動程式化 UI 測試和動作記錄以支援 Microsoft Excel
自動程式化 UI 測試的測試架構和動作記錄並不支援所有可能的使用者介面。 它可能不支援您要測試的特定 UI。 例如，您無法立即為 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 試算表建立自動程式碼 UI 測試或動作記錄。 不過，您可以利用自動程式碼 UI 測試架構的擴充性，在自動程式碼 UI 測試架構中自行建立可以支援特定 UI 的擴充功能。 以下主題會透過範例說明如何擴充架構，以支援 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 的自動程式碼 UI 測試和動作記錄建立作業。 如需支援平台的詳細資訊，請參閱[自動程式化 UI 測試和動作記錄的支援組態和平台](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)。  
  
 **需求**  
  
-   Visual Studio 企業版  
  
 本節介紹可記錄及播放 Excel 工作表測試的自動程式碼 UI 測試擴充功能。 本節將說明該擴充功能的每個部分，想要建立此類擴充功能的開發人員可搭配程式碼註解依序操作。  
  
 ![UI 測試架構](../test/media/ui_testarch.png "UI_TestArch")  
架構概觀  
  
## <a name="download-the-sample"></a>下載範例  
 此範例包含 `CodedUIExtensibilitySample.sln` 解決方案中的四個專案：  
  
-   CodedUIextensibilitySample  
  
-   ExcelCodedUIAddInHelper  
  
-   ExcelUICommunicationHelper  
  
-   SampleTestProject  
  
 從這篇[部落格文章 (英文)](http://go.microsoft.com/fwlink/?LinkID=185592) 取得範例。  
  
> [!NOTE]
>  此範例主要搭配 Microsoft Excel 2010 使用。 此範例可搭配其他版本的 Microsoft Excel 使用，但目前不支援。  
  
## <a name="details-about-the-sample"></a>有關範例的詳細資料  
 下列各節將提供範例與其結構的相關資訊。  
  
### <a name="microsoft-excel-add-in-excelcodeduiaddinhelper"></a>Microsoft Excel 增益集：ExcelCodedUIAddinHelper  
 此專案包含在 Excel 處理序中執行的增益集。 請參閱[自動程式化 UI 測試的範例 Excel 增益集](../test/sample-excel-add-in-for-coded-ui-testing.md)，以概略認識增益集專案。  
  
 如需詳細資訊，請參閱[逐步解說：建立您的第一個 Excel VSTO 增益集](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)。  
  
### <a name="excel-ui-communication-exceluicommunicationhelper"></a>Excel UI 通訊：ExcelUIcommunicationHelper  
 此專案包含用來在自動程式碼 UI 測試架構和 Excel 之間傳遞資料的 `IExcelUICommunication` 介面和資訊類別。 如需詳細資訊，請參閱[範例 Excel Communicator 介面](../test/sample-excel-communicator-interface.md)。  
  
### <a name="coded-ui-test-extension-codeduiexentsibilitysample"></a>自動程式化 UI 測試擴充功能：CodedUIExentsibilitySample  
 此專案包含測試 Excel 工作表時所使用的自訂類別。 每個類別的程式碼均相當容易理解。 不過，我們仍會提供每個自訂類別的簡短說明。 如需詳細資訊，請參閱 [Excel 的範例自動程式化 UI 測試擴充功能](../test/sample-coded-ui-test-extension-for-excel.md)。  
  
### <a name="deploying-your-add-in-and-extension"></a>部署您的增益集和擴充功能  
 建立所有專案和物件後，請以管理員的身分執行提供的 `CopyDrop.bat` 檔案。 該檔案會將 `ExcelCodedUIAddinHelper` DLL 和 PDB 檔案複製到：  
  
 根據 Visual Studio 版本而定，「`%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\<version number>\UITestExtensionPackages\*.*`」可能會是 11.0 和 12.0 等版本號碼。  
  
 `ExcelUICommunicationHelper` DLL 和 PDB 檔案已複製到 `"%ProgramFiles(x86)%\Microsoft Visual Studio <version number>\Common7\IDE\PrivateAssemblies"`。  
  
 您可能必須調整該複本的確實路徑，但不需執行其他安裝作業。 在 64 位元電腦上，使用 32 位元的 Visual Studio Enterprise 命令提示字元以執行 `CopyDrop.bat` 檔案。  
  
### <a name="testing-excel-with-the-sampletestproject"></a>使用 SampleTestProject 測試 Excel

您可以在提供的測試專案中執行測試 (該專案可能會使用您沒有的特定版本 Excel)，或是自行建立測試專案並自行記錄測試。 如需詳細資訊，請參閱[建立自動程式化 UI 測試](../test/use-ui-automation-to-test-your-code.md)。

## <a name="see-also"></a>另請參閱

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
<xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
<xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
[使用使用者介面自動化來測試您的程式碼](../test/use-ui-automation-to-test-your-code.md)   
[自動程式化 UI 測試的最佳做法](../test/best-practices-for-coded-ui-tests.md)   
[自動程式化 UI 測試和動作記錄的支援組態和平台](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)

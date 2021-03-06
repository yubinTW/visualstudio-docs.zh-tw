---
title: "專案設計工具 （Visual Studio 中的 Office 程式開發）、 發行頁 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectProperties.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio]
- publishing, Office solutions
- Property Pages dialog box, Publish [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: d9cc3fa102c0552893c6f7859a256b7df26e3af5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="publish-page-project-designer-office-development-in-visual-studio"></a>專案設計工具、發行頁 (Visual Studio 中的 Office 程式開發)
  [專案設計工具]  的 [發行]  頁面，可用以設定部署的屬性。  
  
 若要存取此頁面，選取的專案中**方案總管 中**，然後在**專案**功能表上，選擇*Projectname* **屬性**. 如果未顯示 [發行]  頁面，請選擇 [發行]  索引標籤。  
  
> [!NOTE]  
>  您也可以在 [發行精靈] 中設定發行位置。 如需詳細資訊，請參閱 [如何：使用 ClickOnce 發行 Office 方案](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)。  
  
## <a name="uielement-list"></a>UIElement 清單  
 **發行資料夾位置 (網站、FTP 伺服器或檔案路徑)**  
 必要。  
  
 發行資料夾位置是 Visual Studio 從組建複製資訊清單、組件及其他檔案等方案檔的目的地目錄。 您必須具有這個目錄的寫入權限。  
  
 選項包括本機電腦、UNC 檔案共用或 HTTP/HTTPS 網站。 這個路徑可以是本機 (*c:\foldername\publishfolder*)、 相對 (*發行\\*)，或完整的位置 (*\\\servername\foldername*或 http://*servername/foldername*)。  
  
 根據預設，如果您已安裝 IIS，發行位置為 *http://localhost/projectname/* ；如果未安裝 IIS，則為 publish\ 目錄。  
  
 **安裝資料夾 URL**  
 選擇性。  
  
 安裝資料夾 URL 是使用者將從中安裝自訂的目錄。 它也是方案將會用來檢查更新的路徑。 路徑可以與發行資料夾位置相同，但這並非必要條件。  
  
 選項包括本機電腦、UNC 檔案共用或 HTTP/HTTPS 網站。 這個路徑可以是本機 (*c:\foldername\publishfolder*)、 相對 (*發行\\*)，或完整的位置 (*\\\servername\foldername*或 http://*servername/foldername*)。 所有的 HTTP/HTTPS 位置都必須以 US-ASCII 字元建立。 不支援 Unicode 字元。  
  
 如果已設定安裝路徑，自訂檔案必須位於該位置，使用者才能安裝自訂。 只有在知道最終部署位置時，才應該設定位置。  
  
 如果安裝檔案位於相對於文件或安裝程式的位置，例如使用 CD 選項，請將這個方塊保留空白。  
  
 系統管理員稍後可以指派這個值。 如需詳細資訊，請參閱 [如何：變更 Office 方案的安裝路徑](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)。  
  
 **必要條件**  
 必要條件可包含在安裝程式中，或視需要於安裝期間下載。  
  
-   **從元件廠商的網站下載必要條件**：使用這個選項可從 Microsoft 下載這些必要條件。  
  
-   **從應用程式的相同位置下載必要條件**：使用這個選項可將必要條件封裝在安裝程式中。 將必要條件檔案包含在安裝程式中會增加方案的大小。  
  
-   **從下列位置下載必要條件**：使用這個選項可透過網頁或網路共用上的另一個安裝程式，將必要條件另外提供給使用者。  
  
 **更新**  
 更新間隔決定方案檢查更新的頻率。 預設值為每七天檢查一次。  
  
 每次載入文件層級自訂或 VSTO 增益集時便檢查更新，雖然可以保持在最新狀態，但也會影響啟動效能。  
  
 如果您要使用 CD 或卸除式磁碟機進行部署，請將這個選項設定為 [永遠不檢查更新] 。  
  
 **選項 (描述)**  
 您可以設定下列屬性的發行選項：  
  
-   發行語言：Office 方案的地區設定。  
  
-   發行者名稱：出現在 [新增/移除程式]  或 [程式和功能] 中的公司或開發人員名稱。  
  
-   產品名稱：出現在 [新增/移除程式]  或 [程式和功能] 中的 Office 方案名稱。  
  
-   支援 URL：使用者連絡 Office 方案技術支援的位置。  
  
 **選項 (Office 設定)**  
 您可以設定下列屬性的發行選項：  
  
-   方案名稱：出現在 Office 應用程式中的 Office 方案名稱。  
  
-   描述：出現在 Office 應用程式中的 Office 方案描述。  
  
-   VSTO 增益集載入行為。  
  
    -   啟動時載入：指定在 Office 應用程式啟動時載入 VSTO 增益集。  
  
    -   視需要載入：指定只有在應用程式需要時才載入 VSTO 增益集，例如當使用者按一下使用 VSTO 增益集功能的 UI 項目時。  
  
 **發行語言**  
 這個選項會設定 Microsoft 軟體授權條款的語言，並將語言套件包含在必要條件清單中。 它不會影響自訂的語言。 安裝程式中的語言取決於 Visual Studio 已安裝的語言。  
  
 如需如何變更 **發行語言**的詳細資訊，請參閱 [How to: Change the Publish Language for a ClickOnce Application](/visualstudio/deployment/how-to-change-the-publish-language-for-a-clickonce-application)。  
  
 **發行版本**  
 設定自訂的版本號碼。 當版本號碼變更時，應用程式會以更新的形式發行。 在建置程序期間，會針對每個版本建立新的資料夾，以避免覆寫先前發行的版本。 發行版本的每個部分 (**主要**、 **次要**、 **組建**、 **修訂**) 最多可包含 5 個數字。  
  
 **隨著每次發行自動遞增修訂**  
 選擇性。 選取時 (預設)，每次發行一次自訂，版本號碼的 **修訂** 部分都會加一。 這會使得自訂以更新的形式發行。  
  
 **立即發行**  
 使用目前的設定發行應用程式。 這相當於 [發行精靈]  中的 [完成] 按鈕。  
  
## <a name="see-also"></a>請參閱  
 [部署 Office 方案](../vsto/deploying-an-office-solution.md)   
 [使用 ClickOnce 部署 Office 方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office 方案的部署必要條件](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)  
  
  
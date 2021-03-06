---
title: "註冊專案和項目範本 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding items
- registry, Add New Item dialog box
- Add New Item dialog box
- Add New Project dialog box
- registry, Add New Project dialog box
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c064a6632741eba69a553be87fb8f829063b266b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="registering-project-and-item-templates"></a>註冊專案和項目範本
專案類型必須登錄其專案和專案項目範本目錄。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]使用您的專案類型相關聯的登錄資訊來決定要顯示在**加入新的專案**和**加入新項目**對話方塊。  
  
 如需範本的詳細資訊，請參閱[加入專案和專案項目範本](../../extensibility/internals/adding-project-and-project-item-templates.md)。  
  
## <a name="registry-entries-for-projects"></a>專案的登錄項目  
 下列範例會顯示登錄項目底下 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<*版本*>。 隨附的表格會說明用於範例中的項目。  
  
```  
[Projects\{ProjectGUID}]  
@="MyProjectType"  
"DisplayName"="#2"  
"Package"="{VSPackageGUID}"  
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"  
```  
  
|名稱|類型|描述|  
|----------|----------|-----------------|  
|@|REG_SZ|這類專案的預設名稱。|  
|DisplayName|REG_SZ|要從附屬 DLL 擷取的資源識別碼名稱的登錄的封裝底下。|  
|Package|REG_SZ|封裝註冊的封裝底下的類別 ID。|  
|ProjectTemplatesDir|REG_SZ|專案範本檔案的預設路徑。 專案範本檔案會顯示**新專案**範本。|  
  
### <a name="registering-item-templates"></a>登錄項目範本  
 您必須註冊您用來儲存項目範本的目錄。  
  
```  
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]  
@="#7"  
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "  
"TemplatesLocalizedSubDir"="#10"  
"SortPriority"=dword:00000064  
```  
  
|名稱|類型|描述|  
|----------|----------|-----------------|  
|@|REG_SZ|加入項目範本的資源識別碼。|  
|TemplatesDir|REG_SZ|在對話方塊中顯示的專案項目路徑**加入新項目**精靈。|  
|TemplatesLocalizedSubDir|REG_SZ|資源識別碼的名稱的子目錄 TemplatesDir 字串保存當地語系化的範本。 因為[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]載入字串資源的附屬 Dll 如果有的話，每個附屬 DLL 可以包含不同當地語系化的子目錄名稱。|  
|SortPriority|REG_DWORD|設定來管理範本中的顯示的順序 SortPriority**加入新項目** 對話方塊。 較大的 SortPriority 值稍早出現在 [範本] 清單。|  
  
### <a name="registering-file-filters"></a>註冊檔案篩選器  
 （選擇性） 您可以註冊的篩選器，[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]時就會提示需要的檔案名稱使用。 例如，[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]篩選**開啟檔案**對話方塊：  
  
 **Visual C# 檔案 (\*.cs\*.resx\*.settings，\*.xsd，\*.wsdl);\*。cs、\*.resx\*.settings，\*.xsd，\*.wsdl)**  
  
 為支援多個篩選器的登錄，每個篩選條件會註冊自己的子機碼下 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio 中\\<*版本*> \Projects\\{\< *ProjectGUID*>} \Filters\\<*子機碼*>。 子機碼名稱是任意的。[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]會忽略子機碼的名稱，並使用只將其值。  
  
 您可以控制在其中使用篩選器的設定旗標下, 表顯示的內容。 如果篩選並沒有設定任何旗標，它會列出中的一般篩選器之後**加入現有項目**對話方塊和**開啟檔案**對話方塊中，但它不會使用在**檔案中尋找**  對話方塊。  
  
```  
[Projects\{ProjectGUID}\Filters\MyLanguageFilter]  
@="#3"  
"CommonOpenFilesFilter"=dword:00000000  
"CommonFindFilesFilter"=dword:00000000  
"FindInFilesFilter"=dword:00000000  
"NotOpenFileFilter"=dword:00000000  
"NotAddExistingItemFilter"=dword:00000000  
"SortPriority"=dword:00000064  
```  
  
|名稱|類型|描述|  
|----------|----------|-----------------|  
|CommonFindFilesFilter|REG_DWORD|可在其中一個常見的篩選器篩選**檔案中尋找** 對話方塊。 一般篩選器會列出未標記為常見的篩選條件之前篩選清單中。|  
|CommonOpenFilesFilter|REG_DWORD|可在其中一個常見的篩選器篩選**開啟檔案** 對話方塊。 一般篩選器會列出未標記為常見的篩選條件之前篩選清單中。|  
|FindInFilesFilter|REG_DWORD|列出篩選器中的一般篩選器之後**檔案中尋找** 對話方塊。|  
|NotOpenFileFilter|REG_DWORD|表示篩選條件中不使用**開啟檔案** 對話方塊。|  
|NotAddExistingItemFilter|REG_DWORD|表示篩選條件中不使用**加入現有項目** 對話方塊。|  
|SortPriority|REG_DWORD|設定 SortPriority 來管理篩選器會顯示的順序。 較大的 SortPriority 值稍早出現在篩選器清單。|  
  
## <a name="directory-structure"></a>目錄結構  
 Vspackage 可以將範本檔案和資料夾任何位置在本機或遠端磁碟上，只要透過整合式的開發環境 (IDE) 登錄位置。 不過，為了方便組織中，我們建議產品的安裝路徑下的下列目錄結構。  
  
 \Templates  
  
 \Projects （包含的專案範本）  
  
 \Applications  
  
 \Components  
  
 \ ...  
  
 \ProjectItems （包含專案項目）  
  
 \Class  
  
 \Form  
  
 \Web 頁面  
  
 \HelperFiles （包含多個檔案的專案項目中使用的檔案）  
  
 \WizardFiles  
  
## <a name="see-also"></a>請參閱  
 [加入專案和專案項目範本](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [精靈](../../extensibility/internals/wizards.md)   
 [當地語系化應用程式](../../ide/localizing-applications.md)   
 [通常用來擴充專案的物件 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)
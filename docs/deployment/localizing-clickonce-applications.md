---
title: "當地語系化 ClickOnce 應用程式 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, ClickOnce applications
- ClickOnce deployment, globalization
- deploying applications [ClickOnce], localizing ClickOnce applications
- localization, ClickOnce deployment
- ClickOnce deployment, download on-demand
- ClickOnce deployment, localization
- Windows Forms, ClickOnce applications
- console applications, ClickOnce applications
ms.assetid: c92b193b-054d-4923-834b-d4226a4c7a1a
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: e1b5b9697445b2d8cc35a73841526db0bd69b5f8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="localizing-clickonce-applications"></a>當地語系化 ClickOnce 應用程式
當地語系化是讓應用程式適合特定文化特性的程序， 這個程序包括將使用者介面 (UI) 文字翻譯成特定地區的語言、使用正確的日期和貨幣格式、調整表單上控制項的大小，以及視需要將控制項左右反轉。  
  
 將應用程式當地語系化時，會為應用程式建立一個或多個附屬組件， 每個組件都包含指定之文化特性特有的 UI 字串、影像和其他資源  (應用程式的主要可執行檔包含應用程式預設的文化特性字串)。  
  
 本主題將說明三種針對其他文化特性部署 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 應用程式的方法：  
  
-   在單一部署內包含所有附屬組件。  
  
-   為每種文化特性產生一個部署，每個部署內都包含單一附屬組件。  
  
-   視需要下載附屬組件。  
  
## <a name="including-all-satellite-assemblies-in-a-deployment"></a>在部署中包含所有附屬組件  
 若不想發行多個 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 部署，您可以發行單一 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 部署，其中包含所有的附屬組件。  
  
 這個方法是 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中的預設值。 您不需要執行任何額外的工作，即可在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中使用這個方法。  
  
 若要搭配 MageUI.exe 使用這個方法，您必須為您的應用程式設定的文化特性**中性**MageUI.exe 中。 接著，您必須手動加入部署中所有附屬組件。 在 MageUI.exe 中，您可以加入附屬組件使用**填入**按鈕**檔案**] 索引標籤的 [應用程式資訊清單。  
  
 這種方法的優點是會建立單一部署，並簡化了當地語系化部署的過程。 在執行階段，將會根據使用者 Windows 作業系統之預設文化特性而使用適當的附屬組件。 這種方法的缺點是不管應用程式要在用戶端電腦上安裝或更新，都會下載所有的附屬組件。 如果您的應用程式包含大量的字串，或是您的客戶使用慢速的網路連接，這種處理序可能會在應用程式更新期間影響效能。  
  
> [!NOTE]
>  這個方法假設您的應用程式會自動調整控制項的高度、寬度和位置，使其符合不同文化特性中的不同文字字串大小。 Windows Form 包含各種控制項和技術，讓您可用來設計方便進行當地語系化的表單，包括 <xref:System.Windows.Forms.FlowLayoutPanel> 和 <xref:System.Windows.Forms.TableLayoutPanel> 控制項以及 <xref:System.Windows.Forms.Control.AutoSize%2A> 屬性。  另請參閱[How to： 在 Windows Form 使用 AutoSize 和 TableLayoutPanel 控制項支援當地語系化](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))。  
  
## <a name="generate-one-deployment-for-each-culture"></a>為每種文化特性產生一個部署  
 在這種部署策略中，您會產生多個部署。 在每個部署內，您只會加入特定文化特性所需的附屬組件，並且將部署標記為具有於該種文化特性。  
  
 若要使用此方法中的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，將**發行語言**屬性**發行**索引標籤，以所需的區域。 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 將會自動包含選定地區所需的附屬組件，並且從部署中排除所有其他的附屬組件。  
  
 您可以使用 Microsoft [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)] 內的 MageUI.exe 工具執行相同的工作。 使用**填入**按鈕**檔案** 索引標籤，來排除所有其他附屬組件從應用程式目錄，然後再將您的應用程式資訊清單的**文化特性**欄位**名稱**MageUI.exe 中部署資訊清單索引標籤。 這些步驟不只會包含正確的附屬組件，也會將部署資訊清單內 `assemblyIdentity` 項目上的 `language` 屬性設定為對應的文化特性。  
  
 在發行應用程式後，您必須針對應用程式支援的每一個其他文化特性重複這個步驟。 您必須先確定您發行到不同的 Web 伺服器目錄或檔案共用目錄每次，因為每個應用程式資訊清單都會參考不同的附屬組件，而且每個部署資訊清單會有不同的值為`language`屬性。  
  
## <a name="downloading-satellite-assemblies-on-demand"></a>視需要下載附屬組件  
 如果您決定要在單一部署中包含所有的附屬組件，則可以使用視需要下載的方式改善效能，這種方式可讓您將組件標記為選擇項， 標記的組件在應用程式安裝或更新期間將不會下載。 您可以在需要時呼叫 <xref:System.Deployment.Application.ApplicationDeployment> 類別上的 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> 方法來安裝這些組件。  
  
 視需要下載附屬組件與視需要下載其他類型的組件有些許的不同。 如需如何啟用此案例中使用的詳細資訊和程式碼範例[!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]工具[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]，請參閱[逐步解說： 依 ClickOnce 部署 API 的要求下載附屬組件](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)。  
  
 您也可以在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 內啟用這種案例。  另請參閱 [逐步解說：使用設計工具依 ClickOnce 部署 API 的要求下載附屬組件](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) 或 [逐步解說：使用設計工具依 ClickOnce 部署 API 的要求下載附屬組件](http://msdn.microsoft.com/library/ms366788\(v=vs.120\))。  
  
## <a name="testing-localized-clickonce-applications-before-deployment"></a>在部署之前測試當地語系化的 ClickOnce 應用程式  
 只有當 Windows Form 應用程式之主執行緒的 <xref:System.Threading.Thread.CurrentUICulture%2A> 屬性設定為附屬組件的文化特性時，才會將附屬組件用於此應用程式。 當地市場的客戶可能已經在執行文化特性設定為適當預設值的當地語系化 Windows 版本。  
  
 在將應用程式提供給客戶使用之前，您有三種選擇可測試當地語系化的部署：  
  
-   您可以在適合的當地語系化 Windows 版本上執行 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 應用程式。  
  
-   您可以透過程式設計方式在應用程式內設定 <xref:System.Threading.Thread.CurrentUICulture%2A> 屬性  (這個屬性必須在呼叫 <xref:System.Windows.Forms.Application.Run%2A> 方法之前設定)。  
  
## <a name="see-also"></a>請參閱  
 [\<assemblyIdentity > 項目](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [ClickOnce 安全性和部署](../deployment/clickonce-security-and-deployment.md)   
 [全球化 Windows Forms](/dotnet/framework/winforms/advanced/globalizing-windows-forms)
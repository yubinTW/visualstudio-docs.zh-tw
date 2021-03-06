---
title: "部署 ClickOnce 應用程式進行測試和實際執行伺服器，而不重新簽章 |Microsoft 文件"
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
- ClickOnce applications, deploying without resigning
- ClickOnce deployment, without resigning
- application updates, ClickOnce
- update location [ClickOnce]
- deploymentProvider tag
- manifests [ClickOnce]
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: ec7265f91d5c202d5885b7f1994aa6f037d6d2ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>針對測試和實際執行伺服器部署 ClickOnce 應用程式但不重新簽章
本主題討論 ClickOnce 引進.NET Framework 3.5 版可讓部署 ClickOnce 應用程式，從多個網路位置，而不需要重新簽署，或變更 ClickOnce 資訊清單中的新功能。  
  
> [!NOTE]
>  不重新簽章仍然是部署新版本的應用程式的慣用的方法。 可能的話，請使用重新簽章的方法。 如需詳細資訊，請參閱 [Mage.exe (資訊清單產生和編輯工具)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)。  
  
 協力廠商開發人員和 Isv 可以選擇加入以這項功能，讓他們的客戶更新其應用程式更容易。 這項功能可用於下列情況：  
  
-   當正在更新應用程式，而不應用程式的第一個安裝。  
  
-   只能在一個設定的電腦上的應用程式時。 例如，如果應用程式設定為指向兩個不同的資料庫，您無法使用這項功能。  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>從部署資訊清單中排除 deploymentProvider  
 任何離線可用性的系統安裝的 ClickOnce 應用程式必須在.NET Framework 2.0 和.NET Framework 3.0 中，指定`deploymentProvider`部署資訊清單中。 `deploymentProvider`通常稱為更新位置; 它是應用程式更新會檢查 ClickOnce 的位置。 這項需求，再加上應用程式發行者來簽署其部署，需要困難更新 ClickOnce 應用程式廠商或其他第三方公司。 它也更難部署相同的應用程式，從相同網路上的多個位置。  
  
 ClickOnce 在.NET Framework 3.5 中所做的變更，它可能會提供 ClickOnce 應用程式，然後將它自己的網路上的應用程式部署中的另一個組織的第三方。  
  
 若要利用這項功能，ClickOnce 應用程式的開發人員必須排除`deploymentProvider`從其部署資訊清單。 這表示不含`-providerUrl`引數，當您建立部署資訊清單與 Mage.exe，或確定**啟動位置**上的文字方塊**應用程式資訊清單** 索引標籤保留空白如果您產生使用 MageUI.exe 的部署資訊清單。  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider 和應用程式更新  
 從.NET Framework 3.5 開始，您不再需要指定`deploymentProvider`部署 ClickOnce 應用程式供線上及離線使用部署資訊清單中。 這可支援您要封裝和簽署部署，但是可讓他們的網路上部署應用程式的其他公司的情況。  
  
 要記得的重點是，排除的應用程式`deploymentProvider`無法在更新期間變更其安裝位置，直到它們寄送包含的更新`deploymentProvider`標記一次。  
  
 以下是兩個範例說明此點。 在第一個範例中，您可以發行 ClickOnce 應用程式沒有`deploymentProvider`標記，而且您要求使用者從 http://www.adatum.com/MyApplication/ 進行安裝。 如果您決定您想要發佈下一個 http://subdomain.adatum.com/MyApplication/ 從應用程式的更新，您必須表示這位於 http://www.adatum.com/MyApplication/ 部署資訊清單中的任何方法。 您可以執行下列任一步驟：  
  
-   告知使用者解除安裝先前的版本，並安裝新版本從新位置。  
  
-   包含在包含 http://www.adatum.com/MyApplication/ 更新`deploymentProvider`指向 http://www.adatum.com/MyApplication/。 然後，發行與更新版本的另一個更新`deploymentProvider`指向 http://subdomain.adatum.com/MyApplication/。  
  
 在第二個範例中，您可以發行 ClickOnce 應用程式，指定`deploymentProvider`，和您決定將它移除。 一次新的版本不含`deploymentProvider`已下載至用戶端，您將無法用於更新，直到您發行的版本具有應用程式的路徑重新導向`deploymentProvider`還原。 如同第一個範例中，`deploymentProvider`一開始必須指向目前的更新位置不是您新的位置。 在此情況下，如果您嘗試插入`deploymentProvider`參考 http://subdomain.adatum.com/MyApplication/，則下次的更新將會失敗。  
  
## <a name="creating-a-deployment"></a>建立部署  
 如需建立可從不同的網路位置部署的部署的逐步指引，請參閱[逐步解說： 手動部署 ClickOnce 應用程式，並不需要重新簽署，並會保留商標資訊](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
## <a name="see-also"></a>請參閱  
 [Mage.exe (資訊清單產生和編輯工具)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (資訊清單產生和編輯工具、圖形用戶端)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)
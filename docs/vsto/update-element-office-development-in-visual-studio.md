---
title: "&lt;更新&gt;元素 （在 Visual Studio 中的 Office 程式開發） |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 72caa5e93b311430f4416946b6ec0bdc9fda5031
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;更新&gt;元素 （在 Visual Studio 中的 Office 程式開發）
  `update`項目會指定的方案會檢查更新的間隔。  
  
## <a name="syntax"></a>語法  
  
```  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>項目和屬性  
 `update` 為必要元素，位於 `vstav3` 命名空間。  
  
 `update`元素都具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`enabled`|必要。 將 enabled 設定為下列值之一：<br /><br /> -   **true**檢查更新。<br />-   **false**以防止 檢查更新。|  
  
 `update`項目具有下列子元素。  
  
### <a name="expiration"></a>到期日  
 `expiration` 為必要元素，位於 `vstav3` 命名空間。 這個項目指定的方案檢查更新的間隔。  
  
 `expiration`元素都具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`maximumAge`|-必要。 將其設定為整數。|  
|`unit`|必要。 設定`unit`至下列值之一：<br /><br /> -   **小時**<br />-   **天**<br />-   **週**|  
  
## <a name="example-of-always-checking-for-updates"></a>一律檢查更新的範例  
  
### <a name="description"></a>描述  
 下列程式碼範例說明`update`設為一律檢查更新，在 Office 方案中的項目。  
  
### <a name="code"></a>程式碼  
  
```  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>設定預設的更新間隔的範例  
  
### <a name="description"></a>描述  
 下列程式碼範例說明`update`Office 方案的應用程式資訊清單中的項目。 這個程式碼範例是 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中所提供之較大範例的一部分。  
  
### <a name="code"></a>程式碼  
  
```  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>請參閱  
 [使用 ClickOnce 部署 Office 方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 方案的部署資訊清單](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 應用程式資訊清單](/visualstudio/deployment/clickonce-application-manifest)  
  
  
---
title: "FeatureProperty 項目 |Microsoft 文件"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperty element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 9dcb2cd375a9c725eea6609edbaeda041922a283
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="featureproperty-element"></a>FeatureProperty 項目
  代表將它部署至 SharePoint 時，會包含與功能的自訂屬性。 將功能部署之後，您可以在程式碼中存取屬性。  
  
## <a name="syntax"></a>語法  
  
```  
<FeatureProperty Key = "Key of the property value"  
    Value = "Property value" />  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|**Key**|需要**xs: string**屬性。<br /><br /> 用來儲存及擷取屬性值的索引鍵。 每個屬性必須有此功能內是唯一的索引鍵。|  
|**值**|需要**xs: string**屬性。<br /><br /> 屬性值。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|表示將它部署至 SharePoint 時，會包含與功能的屬性值的集合。|  
  
## <a name="remarks"></a>備註  
 如需功能屬性的詳細資訊，請參閱[提供封裝和專案項目中的部署資訊](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)。  
  
## <a name="element-information"></a>項目資訊  
  
|||  
|-|-|  
|**命名空間**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**結構描述名稱**|SharePoint 專案項目結構描述|  
|**驗證檔**|ProjectItemModelSchema.xsd|  
|**可以是空的**|否|  
  
## <a name="see-also"></a>請參閱  
 [SharePoint 專案項目結構描述參考](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [提供專案項目中的封裝和部署資訊](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  
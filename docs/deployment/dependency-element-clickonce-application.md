---
title: "&lt;相依性&gt;元素 （ClickOnce 應用程式） |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#osVersionInfo
- urn:schemas-microsoft-com:asm.v2#os
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#dependency
- http://www.w3.org/2000/09/xmldsig#DigestValue
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
- urn:schemas-microsoft-com:asm.v2#dependentAssembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- manifests [ClickOnce], dependency element
- <dependency> element [ClickOnce application manifest]
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
caps.latest.revision: "34"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 7c3319661a4c0df298cd844c4d71c6855cad818c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ltdependencygt-element-clickonce-application"></a>&lt;相依性&gt;元素 （ClickOnce 應用程式）
識別平台或組件的相依性所需的應用程式。  
  
## <a name="syntax"></a>語法  
  
```  
  
      <dependency>  
   <dependentOS  
      supportURL  
      description  
   >  
      <osVersionInfo>  
         <os  
            majorVersion  
            minorVersion  
            buildNumber  
            servicePackMajor  
            servicePackMinor  
            productType  
            suiteType  
         />   
      </osVersionInfo>  
   </dependentOS>  
   <dependentAssembly  
      dependencyType  
      allowDelayedBinding  
      group  
      codeBase  
      size  
   >  
      <assemblyIdentity  
         name  
         version  
         processorArchitecture  
         language  
      >  
         <hash>  
            <dsig:Transforms>  
               <dsig:Transform  
                  Algorithm  
            />  
            </dsig:Transforms>  
            <dsig:DigestMethod />  
            <dsig:DigestValue>  
            </dsig:DigestValue>  
    </hash>  
  
      </assemblyIdentity>  
   </dependentAssembly>  
</dependency>  
```  
  
## <a name="elements-and-attributes"></a>項目和屬性  
 `dependency`項目為必要。 可能有多個執行個體`dependency`相同的應用程式資訊清單中。  
  
 `dependency`項目沒有屬性，並包含下列子元素。  
  
### <a name="dependentos"></a>dependentOS  
 選擇性。 包含`osVersionInfo`項目。 `dependentOS`和`dependentAssembly`元素互斥： 其中一個必須存在`dependency`項目，但非兩者。  
  
 `dependentOS`支援下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`supportUrl`|選擇性。 指定的相依平台的支援 URL。 如果找不到必要的平台是，會向使用者顯示此 URL。|  
|`description`|選擇性。 人類看得懂的格式，描述所描述的作業系統`dependentOS`項目。|  
  
### <a name="osversioninfo"></a>osVersionInfo  
 必要。 這個元素是 `dependentOS` 元素的子項，並包含 `os` 元素。 這個元素沒有屬性。  
  
### <a name="os"></a>作業系統  
 必要。 這個元素是 `osVersionInfo` 元素的子項。 這個項目具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`majorVersion`|必要。 指定的作業系統的主要版本號碼。|  
|`minorVersion`|必要。 指定的 os 的次要版本號碼。|  
|`buildNumber`|必要。 指定的作業系統組建編號。|  
|`servicePackMajor`|必要。 指定作業系統 service pack 主要版本號碼。|  
|`servicePackMinor`|選擇性。 指定作業系統 service pack 次要版本號碼。|  
|`productType`|選擇性。 識別產品類型值。 有效值為 `server`、`workstation` 及 `domainController`。 例如，為 Windows 2000 Professional，這個屬性值是`workstation`。|  
|`suiteType`|選擇性。 識別系統或系統的組態類型上提供的產品套件。 有效值為`backoffice`， `blade`， `datacenter`， `enterprise`， `home`， `professional`， `smallbusiness`， `smallbusinessRestricted`，和`terminal`。 例如，為 Windows 2000 Professional，這個屬性值是`professional`。|  
  
### <a name="dependentassembly"></a>dependentAssembly  
 選擇性。 包含`assemblyIdentity`項目。 `dependentOS`和`dependentAssembly`元素互斥： 其中一個必須存在`dependency`項目，但非兩者。  
  
 `dependentAssembly`具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`dependencyType`|必要。 指定相依性類型。 有效值為 `preprequisite` 和 `install`。 `install`組件已安裝的一部分[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]應用程式。 A`prerequisite`組件必須存在於全域組件快取 (GAC)，才能[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]可以安裝應用程式。|  
|`allowDelayedBinding`|必要。 指定是否可以在執行階段以程式設計方式載入組件。|  
|`group`|選擇性。 如果`dependencyType`屬性設為`install`，視該只有安裝指定的組件的具名的群組。 如需詳細資訊，請參閱[逐步解說：下載組件隨選與 ClickOnce 部署應用程式開發介面使用設計工具](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)。<br /><br /> 如果設定為`framework`和`dependencyType`屬性設為`prerequisite`，將組件指定為.NET Framework 的一部分。 在安裝時，這個組件不檢查全域組件快取 (GAC)[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]和更新版本。|  
|`codeBase`|當`dependencyType`屬性設為`install`。 相依組件的路徑。 可能是絕對路徑或在資訊清單的程式碼的相對路徑的基底。 此路徑必須是有效的 URI 中的組件資訊清單的順序有效。|  
|`size`|當`dependencyType`屬性設為`install`。 相依的組件，以位元組為單位的大小。|  
  
### <a name="assemblyidentity"></a>assemblyIdentity  
 必要。 這個元素是 `dependentAssembly` 元素的子項，並具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`name`|必要。 識別應用程式的名稱。|  
|`version`|必要。 指定應用程式的版本號碼，格式如下：`major.minor.build.revision`|  
|`publicKeyToken`|選擇性。 指定 16 個字元的十六進位字串，表示最後 8 個位元組`SHA-1`簽署的應用程式或組件之公開金鑰的雜湊值。 用來簽署類別目錄的公開金鑰必須是 2048 位元或更多。|  
|`processorArchitecture`|選擇性。 指定處理器。 有效值為`x86`適用於 32 位元 Windows 和`I64`適用於 64 位元 Windows。|  
|`language`|選擇性。 識別兩部分的語言代碼，例如 EN-US，組件。|  
  
### <a name="hash"></a>雜湊  
 `hash`項目是選擇性的子系`assemblyIdentity`項目。 `hash`項目沒有任何屬性。  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]安全性檢查時，使用應用程式中的所有檔案的演算式雜湊，以確保沒有任何檔案已在部署後變更。 如果`hash`就不會包含項目，將不會執行這項檢查。 因此，省略`hash`不建議項目。  
  
### <a name="dsigtransforms"></a>dsig:Transforms  
 `dsig:Transforms`項目是必要的子系`hash`項目。 `dsig:Transforms`項目沒有任何屬性。  
  
### <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform`項目是必要的子系`dsig:Transforms`項目。 `dsig:Transform`元素都具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`Algorithm`|用來計算此檔案的摘要的演算法。 目前所使用的唯一值[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]是`urn:schemas-microsoft-com:HashTransforms.Identity`。|  
  
### <a name="dsigdigestmethod"></a>dsig:DigestMethod  
 `dsig:DigestMethod`項目是必要的子系`hash`項目。 `dsig:DigestMethod`元素都具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`Algorithm`|用來計算此檔案的摘要的演算法。 目前所使用的唯一值[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]是`http://www.w3.org/2000/09/xmldsig#sha1`。|  
  
### <a name="dsigdigestvalue"></a>dsig:DigestValue  
 `dsig:DigestValue`項目是必要的子系`hash`項目。 `dsig:DigestValue`項目沒有任何屬性。 它的值是計算的雜湊，為指定的檔案。  
  
## <a name="remarks"></a>備註  
 您的應用程式所使用的所有組件必須有對應`dependency`項目。 相依組件不包含組件，則必須預先安裝在全域組件快取中做為平台組件。  
  
## <a name="example"></a>範例  
 下列程式碼範例說明`dependency`中的項目[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]應用程式資訊清單。 這個程式碼範例是針對所提供之較大範例的一部分[ClickOnce 應用程式資訊清單](../deployment/clickonce-application-manifest.md)主題。  
  
```  
<dependency>  
  <dependentOS>  
    <osVersionInfo>  
      <os   
        majorVersion="4"   
        minorVersion="10"   
        buildNumber="0"   
        servicePackMajor="0" />  
    </osVersionInfo>  
  </dependentOS>  
</dependency>  
<dependency>  
  <dependentAssembly  
    dependencyType="preRequisite"  
    allowDelayedBinding="true">  
    <assemblyIdentity  
      name="Microsoft.Windows.CommonLanguageRuntime"  
      version="4.0.20506.0" />  
  </dependentAssembly>  
</dependency>  
  
<dependency>  
  <dependentAssembly  
    dependencyType="install"  
    allowDelayedBinding="true"  
    codebase="MyApplication.exe"  
    size="4096">  
    <assemblyIdentity  
      name="MyApplication"  
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="see-also"></a>請參閱  
 [ClickOnce 應用程式資訊清單](../deployment/clickonce-application-manifest.md)   
 [\<相依性 > 項目](../deployment/dependency-element-clickonce-deployment.md)
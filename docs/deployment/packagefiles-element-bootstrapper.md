---
title: "&lt;請為 PackageFiles&gt;元素 （啟動載入器） |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords: <PackageFiles> element [bootstrapper]
ms.assetid: 3ea252d7-18a3-47d8-af83-47feebcfe82b
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 25ba72b511782c450b882826a3e3af94a14f6e20
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="ltpackagefilesgt-element-bootstrapper"></a>&lt;請為 PackageFiles&gt;元素 （啟動載入器）
`PackageFiles`元素包含`PackageFile`項目，可定義執行的安裝封裝`Command`項目。  
  
## <a name="syntax"></a>語法  
  
```  
<PackageFiles  
    CopyAllPackageFiles  
>  
    <PackageFile   
        Name  
        HomeSite  
        CopyOnBuild  
        PublicKey  
        Hash  
    />  
</PackageFiles>  
```  
  
## <a name="elements-and-attributes"></a>項目和屬性  
 `PackageFiles`項目具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`CopyAllPackageFiles`|選擇性。 如果設定為`false`，安裝程式只會下載檔案，從參考`Command`項目。 如果設定為`true`，將下載的所有檔案。<br /><br /> 如果設為`IfNotHomesite`，安裝程式將有相同的行為如同`False`如果`ComponentsLocation`設為`HomeSite`，否則的行為相同，如同`True`。 此設定可讓封裝自行只要 HomeSite 案例中執行本身的行為。<br /><br /> 預設值為 `true`。|  
  
## <a name="packagefile"></a>PackageFile  
 `PackageFile`元素是子系`PackageFiles`項目。 A`PackageFiles`元素必須至少一個`PackageFile`項目。  
  
 `PackageFile`具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`Name`|必要。 封裝檔案的名稱。 這是名稱，`Command`時它會定義用以安裝封裝的條件，將會參考項目。 此值也會用做為索引鍵到`Strings`資料表，以擷取之類的工具的當地語系化的名稱[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]用來描述封裝。|  
|`HomeSite`|選擇性。 在遠端伺服器上，如果不是隨附於安裝程式封裝的位置。|  
|`CopyOnBuild`|選擇性。 指定啟動載入器是否應該在建置階段複製封裝檔案在磁碟上。 預設值為 true。|  
|`PublicKey`|加密的封裝的憑證簽署人公開金鑰。 若`HomeSite`使用; 否則為選擇性。|  
|`Hash`|選擇性。 封裝檔案的 SHA1 雜湊。 這用來在安裝期間確認檔案的完整性。 如果無法計算相同的雜湊，從套件檔案，將不會安裝封裝。|  
  
## <a name="example"></a>範例  
 下列程式碼範例會定義封裝[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]可轉散發套件及其相依性，例如 Windows Installer。  
  
```  
<PackageFiles>  
    <PackageFile Name="instmsia.exe" HomeSite="InstMsiAExe" PublicKey="3082010A0282010100AA99BD39A81827F42B3D0B4C3F7C772EA7CBB5D18C0DC23A74D793B5E0A04B3F595ECE454F9A7929F149CC1A47EE55C2083E1220F855F2EE5FD3E0CA96BC30DEFE58C82732D08554E8F09110BBF32BBE19E5039B0B861DF3B0398CB8FD0B1D3C7326AC572BCA29A215908215E277A34052038B9DC270BA1FE934F6F335924E5583F8DA30B620DE5706B55A4206DE59CBF2DFA6BD154771192523D2CB6F9B1979DF6A5BF176057929FCC356CA8F440885558ACBC80F464B55CB8C96774A87E8A94106C7FF0DE968576372C36957B443CF323A30DC1BE9D543262A79FE95DB226724C92FD034E3E6FB514986B83CD0255FD6EC9E036187A96840C7F8E203E6CF050203010001"/>  
    <PackageFile Name="WindowsInstaller-KB884016-v2-x86.exe" HomeSite="Msi30Exe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetfx.exe" HomeSite="DotNetFXExe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetchk.exe"/>  
</PackageFiles>  
```  
  
## <a name="see-also"></a>請參閱  
 [\<產品 > 項目](../deployment/product-element-bootstrapper.md)   
 [\<封裝 > 項目](../deployment/package-element-bootstrapper.md)   
 [產品和封裝結構描述參考](../deployment/product-and-package-schema-reference.md)
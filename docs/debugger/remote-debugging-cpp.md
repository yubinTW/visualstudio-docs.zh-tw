---
title: "遠端偵錯 Visual c + + 專案 |Microsoft 文件"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9fb8230c2a70cf98a20993db930ddc1d494e989d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2018
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>遠端偵錯 Visual Studio 中的 Visual c + + 專案
若要偵錯在不同電腦上的 Visual Studio 應用程式，請安裝，您將在其中部署應用程式的電腦上執行遠端工具，設定您的專案從 Visual Studio 中，連接到遠端電腦，然後部署並執行應用程式。

![遠端偵錯工具元件](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

遠端偵錯通用 Windows 應用程式 (UWP) 的相關資訊，請參閱[偵錯已安裝的應用程式套件](debug-installed-app-package.md)。

## <a name="requirements"></a>需求

遠端偵錯工具會支援 Windows 7 及更新版本 (不 phone) 和版本的 Windows Server 與 Windows Server 2008 Service Pack 2 開始。 如需需求的完整清單，請參閱[需求](../debugger/remote-debugging.md#requirements_msvsmon)。

> [!NOTE]
> 不支援透過 proxy 連線的兩部電腦之間的偵錯。 透過高延遲或低頻寬連線，例如撥號網際網路，或透過網際網路偵錯跨國家/地區不建議使用和可能會失敗或實在。
  
## <a name="download-and-install-the-remote-tools"></a>下載並安裝遠端工具

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
> [!TIP]
> 在某些情況下，它可以是最有效率的檔案共用從執行遠端偵錯工具。 如需詳細資訊，請參閱[從檔案共用執行遠端偵錯工具](../debugger/remote-debugging.md#fileshare_msvsmon)。
  
## <a name="BKMK_setup"></a>設定遠端偵錯工具

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 如果您需要新增其他的使用者權限變更驗證模式或遠端偵錯工具連接埠號碼，請參閱[設定遠端偵錯工具](../debugger/remote-debugging.md#configure_msvsmon)。

## <a name="remote_cplusplus"></a>遠端偵錯 Visual c + + 專案  
 在下列程序中，名稱和專案路徑是 C:\remotetemp\MyMfc，而遠端電腦的名稱是**MJO DL**。  
  
1.  建立 MFC 應用程式名為**mymfc。**  
  
2.  某處設定容易達到，例如在應用程式中的中斷點**MainFrm.cpp**，在開始`CMainFrame::OnCreate`。  
  
3.  在 [方案總管] 中，以滑鼠右鍵按一下專案，然後選取**屬性**。 開啟**偵錯** 索引標籤。  
  
4.  設定**偵錯工具啟動**至**遠端 Windows 偵錯工具**。  
  
     ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")  
  
5.  對屬性進行下列變更：  
  
    |設定|值|
    |-|-|  
    |遠端命令|C:\remotetemp\mymfc.exe|  
    |工作目錄|C:\remotetemp|  
    |遠端伺服器名稱|MJO DL:*通訊埠編號*|  
    |連線|遠端使用 Windows 驗證|  
    |偵錯工具類型|僅限原生|  
    |部署目錄|C:\remotetemp.|  
    |其他要部署的檔案|C:\data\mymfcdata.txt.|  
  
     如果您部署其他檔案 （選擇性） 時，資料夾必須存在兩台電腦上。  
  
6.  在 方案總管 中，以滑鼠右鍵按一下方案，然後選擇  **Configuration Manager**。  
  
7.  如**偵錯**組態中，選取**部署**核取方塊。  
  
     ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")  
  
8.  開始偵錯 (**偵錯 > 開始偵錯**，或**F5**)。  
  
9. 可執行檔會自動部署到遠端電腦。  
  
10. 如果出現提示，請輸入連接到遠端電腦的網路認證。  
  
     所需的認證專屬於您的網路安全性設定。 比方說，網域的電腦上，您可能會選擇安全性憑證，或輸入您的網域名稱和密碼。 在非網域的電腦，您可以輸入電腦名稱，有效的使用者帳戶名稱，例如 **MJO-DL\name@something.com** ，以及正確的密碼。  
  
11. 在 Visual Studio 的電腦上，您應該會看到執行過程在中斷點停止。  
  
    > [!TIP]
    >  或者，您可以另外執行一個步驟來部署檔案。 在**方案總管] 中，**以滑鼠右鍵按一下**mymfc**節點，然後選擇 [**部署**。  
  
 如果您有應用程式所使用的非程式碼檔案，您需要將它們包含在 Visual Studio 專案。 建立其他檔案的專案資料夾 (在**方案總管] 中**，按一下 [**新增 > 新的資料夾**。)然後將檔案加入資料夾 (在**方案總管] 中**，按一下 [**新增 > 現有項目**，然後選取的檔案)。 在**屬性**頁面上的每個檔案，將**複製到輸出目錄**至**永遠複製**。
  
## <a name="set-up-debugging-with-remote-symbols"></a>設定遠端符號偵錯 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)] 
  
## <a name="see-also"></a>請參閱  
 [Visual Studio 偵錯](../debugger/index.md)  
 [偵錯工具功能導覽](../debugger/debugger-feature-tour.md)   
 [設定 Windows 防火牆進行遠端偵錯](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [遠端偵錯工具連接埠指派](../debugger/remote-debugger-port-assignments.md)   
 [在執行 IIS 的遠端電腦上對 ASP.NET 進行遠端偵錯](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [遠端偵錯錯誤和疑難排解](../debugger/remote-debugging-errors-and-troubleshooting.md)